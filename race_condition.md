In SystemVerilog, when you use a non-blocking assignment (<=), the value on the left side does not change immediately. Instead, it gets updated at the end of the current simulation time step, after all statements in that time step have run.

Simple Language:

Non-blocking assignments (<=) "wait" until everything else scheduled for the current moment is done, then update the variable.
Timing Example:

SystemVerilog
reg a = 0, b = 0;

always @* begin
  a <= 1;
  b <= a;
end
What happens?

At time 0: a = 0, b = 0.
When always @* runs, a <= 1; schedules a to become 1 at the end of the time step.
b <= a; schedules b to get the current value of a (which is 0) at the end of the time step.
End of time step: a becomes 1, b becomes 0.
So, both assignments are scheduled, but the variables are updated together after all statements finish for that time step.

Key point:
Non-blocking assignments let you write code where updates happen "together" at the end of the time step, not instantly as the code runs. This is important for modeling real hardware where signals update in parallel.
