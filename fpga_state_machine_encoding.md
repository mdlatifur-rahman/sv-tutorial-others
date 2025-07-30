
# FPGA Encoding Schemes: Binary, One-Hot, and Gray

In FPGA designs, **state encoding** plays a crucial role in determining how efficiently and reliably a finite state machine (FSM) is implemented. Below are the three commonly used encoding schemes:

---

## 1. Binary Encoding

### Description:
Each state is assigned a unique binary value. If there are `N` states, then `ceil(log2(N))` bits are needed to represent each state.

### Pros:
- Requires fewer flip-flops (more compact)
- Efficient in terms of logic area

### Cons:
- Multiple bits change between transitions, which can lead to glitches if transitions are not synchronized

### Example:

FSM with 4 states:
```
State A = 00
State B = 01
State C = 10
State D = 11
```

---

## 2. One-Hot Encoding

### Description:
Each state is represented using a unique bit position. Only one bit is high (1) at a time, others are 0.

### Pros:
- Simple logic (next state logic is easier)
- Fast (no decoding required)
- Glitch-free due to single-bit transitions

### Cons:
- Requires `N` flip-flops for `N` states (more area)

### Example:

FSM with 4 states:
```
State A = 0001
State B = 0010
State C = 0100
State D = 1000
```

---

## 3. Gray Encoding

### Description:
Only one bit changes between successive states. Reduces the possibility of glitches during state transitions.

### Pros:
- Minimizes switching noise
- Good for crossing clock domains

### Cons:
- Not widely used for FSMs (mainly used in counters)

### Example:

4-state Gray code:
```
State A = 00
State B = 01
State C = 11
State D = 10
```
Only one bit changes between each transition.

---

## Summary Table

| Encoding   | Flip-Flops Required | Glitch Resistance | Area Efficient | Usage |
|------------|---------------------|-------------------|----------------|--------|
| Binary     | log2(N)             | ❌                | ✅             | FSMs, counters |
| One-Hot    | N                   | ✅                | ❌             | Small FSMs |
| Gray       | log2(N)             | ✅                | ✅             | Counters, Clock Domain Crossing |

---

## Conclusion

Choosing the right encoding depends on your design constraints:
- Use **Binary** when area is a constraint.
- Use **One-Hot** for speed and simplicity in small FSMs.
- Use **Gray** for glitch-free transitions, particularly in asynchronous designs.

