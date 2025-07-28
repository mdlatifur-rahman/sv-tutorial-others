
# Race Conditions in SystemVerilog

## What is a Race Condition?

A **race condition** is a situation in digital design (and software) where the final outcome depends on the order or timing of events. In SystemVerilog, this often happens when two or more always blocks try to update the same signal at the same simulation time step. The order in which these blocks execute is not guaranteed, so the final value of the signal can change depending on how the simulator schedules them. This can lead to unpredictable or unexpected results.

**Key point:**  
Race conditions make your design unreliable because the behavior can change depending on timing or simulator scheduling. Using non-blocking assignments (`<=`) in sequential logic can help avoid race conditions.

---

## Example: Race Condition with Blocking(=) Assignments

Suppose you have the following code (similar to what might be found in `race.sv`):

```systemverilog
// Example of potential race condition
reg a = 0, b = 0;

always @* begin
  a = 1;
end

always @* begin
  b = a;
end

```
**What happens here?**
There are two always @* blocks, both sensitive to changes in any signals they read/write.
The first block sets a to 1 every time it is triggered.
The second block sets b to the value of a.
Where's the race?
In simulation, the order in which always blocks execute is not defined. This means that for any change in signals, the simulator can choose to execute either always block first.
Two possible execution orders:
Order 1:
```

always @* begin a = 1; end runs first:
a becomes 1.
always @* begin b = a; end runs second:
b gets the updated value of a (which is 1).
Result: b = 1

```

Order 2:
```
always @* begin b = a; end runs first:
b gets the old value of a (could be 0 if it hasn't updated yet).
always @* begin a = 1; end runs second:
a becomes 1.
Result: b = 0

```
## The problem:
The value of b can be either 0 or 1 depending on which block the simulator executes first.
This is a race condition: the output depends on something unpredictable (scheduler order), not on your design intent.


## Why does this happen?
- Blocking assignments (=) execute immediately, so changes are visible right away to other blocks that run later in the same simulation step.
- But the order of always block execution is not guaranteed.
- Combinational logic should not use blocking assignments to share and update variables across always blocks—this causes unpredictable and non-synthesizable behavior.
## How to fix it?
- Avoid sharing variables written in more than one always block.
- Use non-blocking assignments (<=) in sequential (clocked) blocks.
- For combinational logic, either use a single always block or make sure each variable is written by only one always block.

## Example: Race Condition with non-Blocking(<=) Assignments


In SystemVerilog, when you use a non-blocking assignment (<=), the value on the left side does not change immediately. Instead, it gets updated at the end of the current simulation time step, after everything else scheduled for that time step.

Simple Language:

Non-blocking assignments (<=) "wait" until everything else scheduled for the current moment is done, then update the variable.

Timing Example:

```systemverilog
reg a = 0, b = 0;

always @* begin
  a <= 1;
  b <= a;
end

```
What happens?

At time 0: a = 0, b = 0.
When always @* runs, a <= 1; schedules a to become 1 at the end of the time step.
b <= a; schedules b to get the current value of a (which is 0) at the end of the time step.
End of time step: a becomes 1, b becomes 0.
So, both assignments are scheduled, but the variables are updated together after all statements finish for that time step.

Key point:
Non-blocking assignments let you write code where updates happen "together" at the end of the time step, not instantly as the code runs. This is important for modeling real hardware where signals update in parallel.









To help you understand the difference between blocking (=) and non-blocking (<=) assignments in SystemVerilog simulations, here’s a simple time step simulation example. This will illustrate how variables update differently in a clocked process.

Let's say you have the following code in an always block:

### Blocking Assignment Example
```systemverilog
reg a, b, c;

always @(posedge clk) begin
    a = b;
    b = c;
end
```

### Non-Blocking Assignment Example
```systemverilog
reg a, b, c;

always @(posedge clk) begin
    a <= b;
    b <= c;
end
```

Suppose at the positive edge of clk, the values before the assignments are:
- a = 0
- b = 1
- c = 0

#### Time Step Simulation

| Time | Statement         | Blocking (=) Result | Non-blocking (<=) Result |
|------|------------------|---------------------|--------------------------|
| t0   | Initial values   | a=0, b=1, c=0       | a=0, b=1, c=0            |
| t1   | a = b;           | a=1, b=1, c=0       | (no change yet)          |
| t2   | b = c;           | a=1, b=0, c=0       | (no change yet)          |
| t3   | End of block     | a=1, b=0, c=0       | a=1, b=0, c=0            |

**With blocking (=):**
- a is assigned b’s old value (1).
- b is then assigned c’s old value (0).
- So after the always block, a=1, b=0.

**With non-blocking (<=):**
- All right-hand sides are evaluated at the start.
- a will get b’s old value (1) and b will get c’s old value (0), but the assignments happen together at the end of the block.
- So at the end, a=1, b=0.

**The difference is more evident with chained assignments or when a variable is updated and then used again in the same block.**

### Chained Example

```systemverilog
// Initial: a=0, b=1
always @(posedge clk) begin
    a = b;
    b = a;
end
```
- **Blocking:** a=1, then b=a (which is now 1), so b=1 (both end up as 1).
- **Non-blocking:** Both sides use old values. a <= 1; b <= 0; (a=1, b=0 at end).

### Summary Table

| Assignment | Step 1         | Step 2         | At block end      |
|------------|----------------|----------------|-------------------|
| Blocking   | a=b (a=1)      | b=a (b=1)      | a=1, b=1          |
| Non-block  | schedule a=1   | schedule b=0   | a=1, b=0          |

---

**Key takeaway:**  
- Blocking (`=`) executes immediately, possibly affecting subsequent statements.
- Non-blocking (`<=`) schedules assignments for the end of the time step, so all right-hand sides use values from before the block.



## Blocking Assignment (=)
- Name Reason: The assignment "blocks" the execution of the next statement until it is complete.
- Circuit Analogy: Think of this like a wire connection or combinational logic: the assignment happens immediately, and any subsequent logic uses this new value right away. In simulation, each step must wait for the previous one to finish, just as a signal in hardware must propagate before the next stage can use it.
Example:
```SystemVerilog
a = b; // a gets b's value immediately
b = c; // b gets c's value, after a has already changed
```
## Non-blocking Assignment (<=)
- Name Reason: The assignment does not "block" the execution; all right-hand sides are evaluated at the start, and the updates to the left-hand sides are scheduled to be applied together at the end of the time step.
- Circuit Analogy: This models how flip-flops (registers) work in hardware: all inputs to flip-flops are sampled simultaneously at the clock edge, and all outputs change together after the clock edge, regardless of assignment order in code. The assignments are "non-blocking" because the code can keep executing without waiting for the assignment to take effect immediately.
Example:
```
SystemVerilog
a <= b; // a will get b's value at the end of the time step
b <= c; // b will get c's value at the end of the time step
```
















