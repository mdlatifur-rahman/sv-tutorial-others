
### Question 1
**Which VHDL statement is used for concurrent signal assignment?**
- [x] <=
- [ ] :=
- [ ] =
- [ ] :<=

---

### Question 2
**What does the following Verilog code implement?**
```verilog
assign out = in1 & in2;
```
- [x] AND gate
- [ ] OR gate
- [ ] XOR gate
- [ ] NAND gate

---

### Question 3
**How many inputs does a 4-to-1 multiplexer have?**
- [x] 4
- [ ] 1
- [ ] 2
- [ ] 8

---

### Question 4
**Which module is commonly used for serial communication?**
- [x] UART
- [ ] PWM
- [ ] FIFO
- [ ] PLL

---

### Question 5
**Which language is NOT used for FPGA development?**
- [ ] VHDL
- [ ] Verilog
- [x] Python
- [ ] SystemVerilog

---

### Question 6
**What is the primary function of a LUT in FPGA?**
- [x] Implement logic functions
- [ ] Store data permanently
- [ ] Generate clock signals
- [ ] Manage I/O pins

---

### Question 7
**Which signal width is required for a modulo-64 counter?**
- [x] 6 bits
- [ ] 8 bits
- [ ] 4 bits
- [ ] 5 bits

---

### Question 8
**Which process is used to convert HDL code to a gate-level representation?**
- [x] Synthesis
- [ ] Simulation
- [ ] Placement
- [ ] Routing

---

### Question 9
**Which Verilog construct is used to describe hardware behavior over time?**
- [x] always
- [ ] initial
- [ ] assign
- [ ] wire

---

### Question 10
**What is the default value of a signal in VHDL if not initialized?**
- [x] 'U' (undefined)
- [ ] '0'
- [ ] '1'
- [ ] 'Z'

---

### Question 11
**How is a rising edge detected in VHDL?**
- [x] rising_edge(clk)
- [ ] clk = '1'
- [ ] clk'event
- [ ] clk > '0'

---

### Question 12
**Which coding style helps avoid latches in VHDL?**
- [x] Full sensitivity list in process
- [ ] Incomplete sensitivity list
- [ ] Variable assignment
- [ ] Nested processes

---

### Question 13
**What is required for proper clock domain crossing?**
- [x] Synchronizer
- [ ] Direct wire connection
- [ ] Combinational logic
- [ ] Buffer

---

### Question 14
**Which memory type is volatile in FPGAs?**
- [x] SRAM
- [ ] Flash
- [ ] PROM
- [ ] EPROM

---

### Question 15
**How many output bits does a 3-to-8 decoder have?**
- [x] 8
- [ ] 3
- [ ] 6
- [ ] 4

---

### Question 16
**What is the main use of a PLL in FPGAs?**
- [x] Clock management
- [ ] Data buffering
- [ ] Signal amplification
- [ ] Power regulation

---

### Question 17
**Which of the following is NOT a synchronous element?**
- [ ] Register
- [ ] Counter
- [x] Combinational gate
- [ ] Shift register

---

### Question 18
**How many states can be encoded with 5 flip-flops using one-hot encoding?**
- [x] 5
- [ ] 16
- [ ] 32
- [ ] 8

---

### Question 19
**Which is the correct way to instantiate a module in Verilog?**
- [x] module_name instance_name(...);
- [ ] instantiate module_name(...);
- [ ] module module_name(...);
- [ ] module_name(...);

---

### Question 20
**Which is a non-blocking assignment in Verilog?**
- [x] <=
- [ ] =
- [ ] :=
- [ ] <-

---

### Question 21
**Which signal type is commonly used for bidirectional data in VHDL?**
- [x] inout
- [ ] buffer
- [ ] out
- [ ] in

---

### Question 22
**Which tool is used for RTL simulation?**
- [x] ModelSim
- [ ] Vivado
- [ ] Quartus
- [ ] Libero

---

### Question 23
**Which of the following is a sequential circuit?**
- [x] Flip-flop
- [ ] AND gate
- [ ] OR gate
- [ ] Multiplexer

---

### Question 24
**What is the output of a 2-to-4 decoder when input is '10'?**
- [x] 0100
- [ ] 0010
- [ ] 1000
- [ ] 0001

---

### Question 25
**Which clock edge is typically used for positive edge-triggered flip-flops?**
- [x] rising
- [ ] falling
- [ ] both
- [ ] none

---

### Question 26
**Which HDL statement is used for conditional assignment in VHDL?**
- [x] when ... else
- [ ] if ... then
- [ ] case
- [ ] with ... select

---

### Question 27
**What does the following VHDL code describe?**
```vhdl
process(clk)
begin
  if rising_edge(clk) then
    q <= d;
  end if;
end process;
```
- [x] D flip-flop
- [ ] T flip-flop
- [ ] JK flip-flop
- [ ] SR latch

---

### Question 28
**Which encoding minimizes hardware for state output signals?**
- [x] One-hot
- [ ] Binary
- [ ] Gray
- [ ] BCD

---

### Question 29
**What is the main benefit of using FPGAs over ASICs?**
- [x] Reconfigurability
- [ ] Lower power
- [ ] Higher speed
- [ ] Smaller size

---

### Question 30
**What is the purpose of a testbench in HDL design?**
- [x] Verify logic functionality
- [ ] Synthesize design
- [ ] Place and route
- [ ] Assign pins

---

### Question 31
**How many address lines are needed for a 1K x 8 RAM?**
- [x] 10
- [ ] 8
- [ ] 16
- [ ] 12

---

### Question 32
**Which module is ideal for storing large data buffers?**
- [x] Block RAM
- [ ] LUT
- [ ] Flip-flop
- [ ] IO pad

---

### Question 33
**What is a common use of shift registers in digital design?**
- [x] Serial-to-parallel conversion
- [ ] Frequency division
- [ ] Oscillator
- [ ] Multiplexing

---

### Question 34
**How many unique values can a 7-bit signal represent?**
- [x] 128
- [ ] 64
- [ ] 256
- [ ] 32

---

### Question 35
**Which Verilog keyword is used for procedural blocks?**
- [x] always
- [ ] assign
- [ ] initial
- [ ] wire

---

### Question 36
**Which of the following is NOT a storage element?**
- [ ] Flip-flop
- [ ] Latch
- [x] Gate
- [ ] Register

---

### Question 37
**Which Verilog operator is used for bitwise OR?**
- [x] |
- [ ] &
- [ ] ~
- [ ] ^

---

### Question 38
**What is the main purpose of synthesis constraints?**
- [x] Guide optimization and timing
- [ ] Set signal values
- [ ] Test logic
- [ ] Create registers

---

### Question 39
**Which signal assignment in Verilog is valid only in always blocks?**
- [x] =
- [ ] <=
- [ ] assign
- [ ] initial

---

### Question 40
**What is the function of a demultiplexer?**
- [x] Routes one input to multiple outputs
- [ ] Combines multiple inputs
- [ ] Stores data
- [ ] Generates clock signals

---

### Question 41
**What is the output of a NAND gate when both inputs are 1?**
- [x] 0
- [ ] 1
- [ ] X
- [ ] Z

---

### Question 42
**Which HDL is case insensitive?**
- [x] VHDL
- [ ] Verilog
- [ ] SystemVerilog
- [ ] C

---

### Question 43
**Which signal is typically used to reset a synchronous circuit?**
- [x] Active-high reset
- [ ] Active-low enable
- [ ] Clock
- [ ] Data

---

### Question 44
**Which Verilog expression inverts all bits of a signal?**
- [x] ~signal
- [ ] !signal
- [ ] signal~
- [ ] ^signal

---

### Question 45
**How many possible output combinations does a 2-input XOR gate have?**
- [x] 2
- [ ] 1
- [ ] 3
- [ ] 4

---

### Question 46
**Which encoding is best for minimizing signal transitions in counters?**
- [x] Gray code
- [ ] Binary
- [ ] One-hot
- [ ] BCD

---

### Question 47
**Which construct is used for constant value assignment in VHDL?**
- [x] constant
- [ ] signal
- [ ] variable
- [ ] assign

---

### Question 48
**Which Verilog operator is used for bitwise AND?**
- [x] &
- [ ] |
- [ ] ~
- [ ] ^

---

### Question 49
**Which is a valid binary value for a 4-bit signal?**
- [x] 1010
- [ ] 11010
- [ ] 2
- [ ] A

---

### Question 50
**What does the following HDL code describe?**
```verilog
assign y = a ? b : c;
```
- [x] Multiplexer
- [ ] Decoder
- [ ] Adder
- [ ] Register

---
````
