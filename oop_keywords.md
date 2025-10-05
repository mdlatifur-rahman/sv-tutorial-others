
---

## 🧠 SystemVerilog OOP Keyword Cheat Sheet

### 🔹 `virtual`
- **Applies to**: Methods (functions/tasks)
- **Purpose**: Enables polymorphism—allows derived classes to override behavior.
- **Example**:
  ```systemverilog
  class Base;
    virtual function void show();
      $display("Base");
    endfunction
  endclass

  class Derived extends Base;
    function void show();
      $display("Derived");
    endfunction
  endclass

  Base b = new Derived();
  b.show(); // Prints "Derived"
  ```

---

### 🔹 `static`
- **Applies to**: Properties and methods
- **Purpose**: Belongs to the class, not to any instance. Shared across all objects. Can't access non-static properties or methods inside a class.
- **Example**:
  ```systemverilog
  class Counter;
    static int count = 0;

    static function void inc();
      count++;
    endfunction
  endclass

  Counter::inc();
  $display("Count = %0d", Counter::count); // Count = 1
  ```

---

### 🔹 `extern`
- **Applies to**: Methods
- **Purpose**: Declares a method outside the class body.
- **Example**:
  ```systemverilog
  class Packet;
    extern function void display();
  endclass

  function void Packet::display();
    $display("Packet Display");
  endfunction
  ```

---

### 🔹 `local`
- **Applies to**: Properties and methods
- **Purpose**: Accessible only within the class itself.
- **Example**:
  ```systemverilog
  class Secret;
    local int code = 42;

    function int getCode();
      return code;
    endfunction
  endclass
  ```

---

### 🔹 `protected`
- **Applies to**: Properties and methods
- **Purpose**: Accessible within the class and its subclasses.
- **Example**:
  ```systemverilog
  class Parent;
    protected int id = 7;
  endclass

  class Child extends Parent;
    function void showId();
      $display("ID = %0d", id);
    endfunction
  endclass
  ```

---

### 🔹 `pure virtual`
- **Applies to**: Methods
- **Purpose**: Declares abstract methods that must be overridden.
- **Example**:
  ```systemverilog
  virtual class Shape;
    pure virtual function void draw();
  endclass

  class Circle extends Shape;
    function void draw();
      $display("Drawing Circle");
    endfunction
  endclass
  ```

---

### 🚫 Not Allowed

| Keyword     | Applies To     | Status     | Reason |
|-------------|----------------|------------|--------|
| `virtual`   | Constructors   | ❌ Invalid | Constructors can't be overridden |
| `static`    | Constructors   | ❌ Invalid | Constructors are tied to object instantiation |

---
