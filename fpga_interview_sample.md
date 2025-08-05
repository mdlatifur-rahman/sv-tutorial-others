### Question 1
**What is the main benefit of using synchronous resets in FPGA designs?**
- [x] Predictable timing and easier synthesis
- [ ] Reduced power consumption
- [ ] Faster signal propagation
- [ ] Simpler PCB routing

---

### Question 2
**Given the following Verilog snippet, what value does `cnt` reach before the error signal is set?**
```verilog
always @(posedge clk) begin
    if (rst) begin
        cnt <= 0;
    end else begin
        cnt <= cnt + 1;
        if (cnt == 255)
            error <= 1;
    end
end
```
- [ ] 127
- [ ] 128
- [x] 255
- [ ] 256

---

### Question 3
**Which type of encoding minimizes state transitions in a state machine?**
- [ ] binary
- [x] gray
- [ ] one-hot
- [ ] thermometer

---

### Question 4
**How many flip-flops are required to encode 8 states using one-hot encoding?**
- [x] 8
- [ ] 3
- [ ] 4
- [ ] 7

---

### Question 5
**Select the boolean equation matching this truth table:**
| A | B | O |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |
- [x] (A xnor B)
- [ ] (A xor B)
- [ ] (A and B)
- [ ] (A or B)

---

### Question 6
**How many levels of logic are there between DataIn and DataOut in this module?**
```verilog
assign DataOut = ~DataIn;
```
- [x] 1
- [ ] 0
- [ ] 2
- [ ] 8

---

### Question 7
**Which statement has the highest logic utilization?**
```
1. Z1 <= X - Y;
2. Z2 <= X + 1;
3. Z3 <= X / 128;
4. Z4 <= X * 8;
```
- [x] 1
- [ ] 2
- [ ] 3
- [ ] 4

---

### Question 8
**How many lookup tables are needed for an 8-bit AND operation (each output bit is AND of two inputs)?**
- [x] 8
- [ ] 1
- [ ] 4
- [ ] 16

---

### Question 9
**What is the minimum number of gates for the equation `(A xor B) and C` using 2-input gates?**
- [ ] 0
- [ ] 1
- [x] 2
- [ ] 3

---

### Question 10
**How do you avoid metastability in clock domain crossing?**
- [x] Use synchronizer flip-flops
- [ ] Add pull-up resistors
- [ ] Increase clock frequency
- [ ] Use combinational logic

---

### Question 11
**What is the main advantage of gray code in state machines?**
- [x] Only one bit changes at a time
- [ ] Faster transitions
- [ ] Lower power usage
- [ ] Easier synthesis

---

### Question 12
**What type of assignment is recommended in sequential always blocks in Verilog?**
- [x] Non-blocking (`<=`)
- [ ] Blocking (`=`)
- [ ] Continuous (`assign`)
- [ ] Procedural (`=>`)

---

### Question 13
**Which module implements a bit reversal for an 8-bit input?**
```verilog
assign DataOut[7:0] = {DataIn[0], DataIn[1], DataIn[2], DataIn[3], DataIn[4], DataIn[5], DataIn[6], DataIn[7]};
```
- [ ] No bit reversal
- [x] Bit reversal
- [ ] Bitwise AND
- [ ] Bitwise OR

---

### Question 14
**For the following gates, select the correct output for A=1, B=0, C=1**
- [x] F=1
- [ ] F=0

---

### Question 15
**Which signal assignment creates a register in FPGA?**
- [x] Inside a clocked always block
- [ ] Inside a combinational always block
- [ ] Using assign
- [ ] Using initial

---

### Question 16
**How many bits are needed to encode 5 states using binary encoding?**
- [ ] 2
- [x] 3
- [ ] 5
- [ ] 4

---

### Question 17
**Which is NOT a benefit of pipelining?**
- [ ] Higher throughput
- [x] Lower latency
- [ ] Easier timing closure
- [ ] Increased clock frequency

---

### Question 18
**What is the main purpose of constraint files (XDC, SDC)?**
- [x] Define timing and pin assignments
- [ ] Implement logic functions
- [ ] Simulate design behavior
- [ ] Set synthesis options

---

### Question 19
**Which statement describes functional verification?**
- [x] Testing design logic using simulation
- [ ] Measuring timing using static analysis
- [ ] Synthesizing design for FPGA
- [ ] Assigning pins to signals

---

### Question 20
**What does a FIFO help manage in FPGA design?**
- [x] Data rate mismatches
- [ ] Power consumption
- [ ] Design complexity
- [ ] Pin assignments

---

### Question 21
**Which signal below is most susceptible to metastability?**
- [x] Clock domain crossing signal
- [ ] Synchronous reset
- [ ] Data bus
- [ ] Power supply

---

### Question 22
**What is the largest value a 4-bit counter can store?**
- [x] 15
- [ ] 16
- [ ] 14
- [ ] 8

---

### Question 23
**Which encoding technique produces the least logic for a state output signal?**
- [ ] binary
- [ ] gray
- [x] one-hot
- [ ] thermometer

---

### Question 24
**Which tool is used for placing and routing FPGA designs?**
- [x] Vivado
- [ ] ModelSim
- [ ] Quartus
- [ ] ISE

---

### Question 25
**Which signal assignment in VHDL creates a latch?**
- [x] Incomplete sensitivity list in process
- [ ] Complete sensitivity list
- [ ] Using variable assignment
- [ ] Using signal assignment

---

### Question 26
**What is the minimum number of gates for `((A and B and C) or ((A or B) and C))`?**
- [ ] 0
- [x] 2
- [ ] 3
- [ ] 4

---

### Question 27
**Which design element is most likely implemented using Block RAM?**
- [x] Large memory buffers
- [ ] Flip-flops
- [ ] LUTs
- [ ] IO pads

---

### Question 28
**How many registers are needed for a 16-bit shift register?**
- [x] 16
- [ ] 8
- [ ] 4
- [ ] 32

---

### Question 29
**Which is NOT typically a part of a testbench?**
- [ ] Stimulus generator
- [ ] DUT (Device Under Test)
- [x] Synthesis constraints
- [ ] Output checker

---

### Question 30
**What is the first step in FPGA synthesis?**
- [x] Translate HDL to netlist
- [ ] Place and route
- [ ] Timing analysis
- [ ] Bitstream generation

---

### Question 31
**Which assignment is combinational in Verilog?**
- [x] assign DataOut = DataIn;
- [ ] DataOut <= DataIn;
- [ ] DataOut = DataIn;
- [ ] DataOut => DataIn;

---

### Question 32
**Which is a benefit of using IP cores?**
- [x] Faster design implementation
- [ ] Higher power consumption
- [ ] Reduced flexibility
- [ ] More manual coding

---

### Question 33
**How many bits are needed for a 256-state machine with binary encoding?**
- [ ] 7
- [x] 8
- [ ] 256
- [ ] 16

---

### Question 34
**Which is the most power-efficient clock gating technique?**
- [x] Integrated clock gate cell
- [ ] Combinational logic
- [ ] Flip-flop enable
- [ ] Register-based gating

---

### Question 35
**What is the main use of AXI interfaces in FPGA?**
- [x] High-speed data transfer
- [ ] Power management
- [ ] Pin mapping
- [ ] Clock synchronization

---

### Question 36
**Which tool verifies FPGA timing constraints?**
- [x] Static Timing Analyzer
- [ ] Logic Simulator
- [ ] Synthesis Tool
- [ ] RTL Viewer

---

### Question 37
**Which HDL supports both behavioral and structural modeling?**
- [x] VHDL
- [ ] C
- [ ] SystemVerilog
- [ ] Python

---

### Question 38
**Which Verilog construct is used for simulation-only code?**
- [x] initial
- [ ] always
- [ ] assign
- [ ] case

---

### Question 39
**Which is best for implementing a register file in FPGA?**
- [x] Block RAM
- [ ] LUTs
- [ ] Flip-flops
- [ ] IO pads

---

### Question 40
**What is the minimum number of gates for `((A or B) and C) and (A and not C)`?**
- [x] 0
- [ ] 1
- [ ] 2
- [ ] 4

---

### Question 41
**Which is NOT a valid VHDL process sensitivity list item?**
- [ ] clk
- [ ] rst
- [ ] data_in
- [x] wire

---

### Question 42
**Which signal assignment creates combinational logic in VHDL?**
- [x] signal assignment outside process
- [ ] inside clocked process
- [ ] variable assignment
- [ ] in process with incomplete sensitivity list

---

### Question 43
**Which FPGA architecture element stores configuration data?**
- [x] SRAM cells
- [ ] Flip-flops
- [ ] LUTs
- [ ] Block RAM

---

### Question 44
**Which Verilog keyword is used for continuous assignment?**
- [x] assign
- [ ] always
- [ ] initial
- [ ] case

---

### Question 45
**What is the main difference between synchronous and asynchronous reset?**
- [x] Synchronous reset occurs with clock edge
- [ ] Asynchronous reset is always active
- [ ] Synchronous reset is always active
- [ ] Asynchronous reset occurs with clock edge

---

### Question 46
**What is the maximum value a 3-bit signal can hold?**
- [ ] 6
- [x] 7
- [ ] 8
- [ ] 3

---

### Question 47
**Which technique reduces FPGA power?**
- [x] Clock gating
- [ ] Adding flip-flops
- [ ] Using more LUTs
- [ ] Increasing IO count

---

### Question 48
**What is the function of a multiplexer?**
- [x] Selects one of several inputs
- [ ] Stores data
- [ ] Generates clock
- [ ] Inverts signal

---

### Question 49
**Which module generates a pulse-width modulated output?**
- [x] PWM
- [ ] UART
- [ ] ADC
- [ ] FIFO

---

### Question 50
**What is the purpose of a testbench in FPGA design?**
- [x] Simulate and verify logic
- [ ] Synthesize design
- [ ] Assign pins
- [ ] Place and route

---
