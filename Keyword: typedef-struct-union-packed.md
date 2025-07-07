# System Verilog typedef, struct, union

Key Concepts Used:
typedef: Creates a new, user-defined data type with a specific name. This improves code readability and maintainability by allowing complex type declarations to be represented by a simpler name. According to FPGA Tutorial, typedef allows you to define new types built from predefined or user-defined types in Verilog and SystemVerilog.
struct: Groups several variables of different data types into a single unit.
packed: When applied to a struct or union, it indicates that the members should be stored contiguously in memory without gaps. This allows the entire structure or union to be treated as a single vector of bits.
union: Allows a single memory location to be interpreted as different data types. Only one member of a union can be active at any given time. 
These structures and unions are commonly used in Verilog/SystemVerilog for designing hardware that processes or transmits data packets or flits. They provide a structured way to define the layout of these data structures and access their individual fields.


what is the difference between union and struct

In both C and Verilog (specifically SystemVerilog), the key difference between a struct and a union lies in how they handle memory allocation and access to their members. 
Here's a breakdown:
Struct (Structure):
Memory Allocation: A struct allocates separate memory space for each of its members.
The total size of a structure is the sum of the sizes of all its members.
Member Access: All members of a struct can be accessed simultaneously, as they have their own distinct memory locations.
Purpose: struct is used to group related data items of potentially different types into a single unit. This allows you to treat these related data as a single entity, making code more organized and readable, especially when passing bundles of signals in HDL designs. 
Union:
Memory Allocation: A union allocates memory space that is just large enough to hold the largest member.
All members of the union share this same memory location.
Member Access: Only one member of a union can be accessed at a time.
Writing a value to one member of a union will overwrite any value previously stored in another member because they share the same memory.
Purpose: union is useful when you want to interpret a single memory location as multiple different data types or structures. It allows you to have different "views" or "interpretations" of the same underlying data. 
Analogy:
Struct: Imagine a closet with different shelves for different items. Each item has its own dedicated space.
Union: Imagine a single box that can hold either a book, a hat, or a pair of shoes. You can only put one item in the box at a time, but the box needs to be large enough to hold the largest item. 
Packed Structures and Unions in SystemVerilog:
In SystemVerilog, the packed keyword can be used with both struct and union.
Packed Struct: The members are packed together contiguously in memory, treated as a single vector of bits. This can be helpful for interfacing with hardware signals.
Packed Union: All members must be the exact same size, and they share the same memory space. This provides different ways to access the same underlying bit vector. 
In Summary:
The key difference boils down to memory allocation: struct provides separate memory for each member, allowing simultaneous access, while union provides shared memory, allowing access to only one member at a time
