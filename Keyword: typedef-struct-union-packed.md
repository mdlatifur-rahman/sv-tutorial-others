# SystemVerilog Concepts

This section provides explanations of key SystemVerilog constructs, formatted for easy integration into GitHub documentation.

---

## `$clog2` System Function

The `$clog2` function is a built-in SystemVerilog system function that calculates the ceiling of the base-2 logarithm of a given positive integer.

### 🔍 Purpose

- **Memory Addressing**: Determines the minimum number of bits required to address a memory with a given number of locations.  
  _Example: A memory with 64 locations needs_ `clog2(64) = 6` _bits._

- **Indexing and Looping**: Helps determine the bit width for index variables when working with arrays or data structures, improving efficiency.

- **State Representation**: Calculates the minimum vector width to represent a given number of states.

### 🧾 Syntax

```systemverilog
integer result = $clog2(value);
```

- `value`: A positive integer input.
- `result`: Stores the ceiling of the base-2 logarithm of `value`.

### 💡 Example

```systemverilog
parameter MEM_SIZE = 64;
localparam ADDR_WIDTH = $clog2(MEM_SIZE); // ADDR_WIDTH will be 6
```

> 🔸 Note: `$clog2` is synthesizable if the argument is a constant. It was introduced in **Verilog-2005**.

---

## `typedef struct packed`

The `typedef struct packed` construct defines a new data type grouping multiple variables into a contiguous memory layout.

### 🔍 Purpose

- **Data Encapsulation**: Combines related signals or data fields into a unit for better organization.
- **Simplified Interfacing**: Useful for passing signal bundles between modules.
- **Efficient Memory Utilization**: `packed` ensures no gaps between members—treated as a single bit vector.

### 🧾 Syntax

```systemverilog
typedef struct packed {
  type_1 member_1;
  type_2 member_2;
  // ...
} struct_name;
```

### 💡 Example

```systemverilog
typedef struct packed {
  logic [DEST_ADDR_SIZE_X-1 : 0] x_dest;
  logic [DEST_ADDR_SIZE_Y-1 : 0] y_dest;
  logic [HEAD_PAYLOAD_SIZE-1: 0] head_pl;
} head_data_t;
```

> This defines a structure `head_data_t` grouping destination addresses and head payloads into a packed unit.

---

## `typedef union packed`

The `typedef union packed` construct defines a type where all members share the same memory space. Only one member is accessible at a time.

### 🔍 Purpose

- **Multiple Data Interpretations**: Access memory using different formats.
- **Memory Efficiency**: Uses memory of the largest member only.
- **Simplified Data Handling**: Useful when data formats vary.

### 🧾 Syntax

```systemverilog
typedef union packed {
  type_1 member_1;
  type_2 member_2;
  // ...
} union_name;
```

### 💡 Example

```systemverilog
union packed {
  head_data_t head_data;
  logic [FLIT_DATA_SIZE-1 : 0] bt_pl;
} data;
```

> This allows interpreting `data` as either structured `head_data_t` or as a raw payload `bt_pl`.

---

## 🔄 Difference Between `struct` and `union`

| Feature | `struct` | `union` |
|--------|----------|---------|
| Memory Allocation | Separate for each member | Shared across all members |
| Access | All members accessible simultaneously | Only one member accessible at a time |
| Use Case | Group related data | Represent multiple views of the same data |

> ✅ Use `struct` when grouping signals.  
> 🔄 Use `union` when you need to reinterpret memory.
