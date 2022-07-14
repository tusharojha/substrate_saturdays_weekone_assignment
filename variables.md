## Variables

### Binding and mutability

1. 🌟 A variable can be used only if it has been initialized.

```rust
fn main() {
    let x: i32 = 5; // Uninitialized but used, ERROR !

    assert_eq!(x, 5);
    println!("Success!");
}
```

2. 🌟 Use mut to mark a variable as mutable.

```rust
fn main() {
    let mut x =  1;
    x += 2; 
    
    assert_eq!(x, 3);
    println!("Success!");
}
```

### Scope
A scope is the range within the program for which the item is valid.

3. 🌟

```rust
fn main() {
    let x: i32 = 10;
    let y: i32 = 5;
    {
        println!("The value of x is {} and value of y is {}", x, y);
    }
    println!("The value of x is {} and value of y is {}", x, y); 
}
```

4. 🌟🌟

```rust
fn main() {
    let data = define_x();
    println!("{}, world", data); 
}

fn define_x() -> &'static str {
    let x = "hello";
    x
}
```

### Shadowing

5. 🌟🌟

```rust
fn main() {
    let x: i32 = 5;
    {
        let x = 12;
        assert_eq!(x, 12);
    }

    assert_eq!(x, 5);

    let x =  42;
    println!("{}", x); // Prints "42".
}
```

6. 🌟🌟

```rust
fn main() {
    let mut x: i32 = 1;
    x = 7;
    // Shadowing and re-binding
    let x = x; 


    let y = 4;
    // Shadowing
    let y = "I can also be bound to text!"; 

    println!("Success!");
}
```

### Unused Variables

7. 🌟🌟

```rust
fn main() {
    let x = 1; 
    println!("{}", x);
}
```

### Destructuring

8. 🌟🌟

```rust
fn main() {
    let (mut x, y) = (1, 2);
    x += 2;

    assert_eq!(x, 3);
    assert_eq!(y, 2);

    println!("Success!");
}
```

### Destructuring Assignments

9. 🌟🌟

```rust
fn main() {
    let (x, y);
    (x,..) = (3, 4);
    [.., y] = [1, 2];
    // Fill the blank to make the code work
    assert_eq!([x,y], [3, 2]);

    println!("Success!");
} 
```