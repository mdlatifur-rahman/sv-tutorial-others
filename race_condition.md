
# Race Conditions in SystemVerilog

## What is a Race Condition?

A **race condition** is a situation in digital design (and software) where the final outcome depends on the order or timing of events. In SystemVerilog, this often happens when two or more always blocks try to update the same signal at the same simulation time step. The order in which these blocks execute is not guaranteed, so the final value of the signal can change depending on how the simulator schedules them. This can lead to unpredictable or unexpected results.

**Key point:**  
Race conditions make your design unreliable because the behavior can change depending on timing or simulator scheduling. Using non-blocking assignments (`<=`) in sequential logic can help avoid race conditions.

---

## Example: Race Condition with Blocking Assignments

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

---






#Another Example:






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
