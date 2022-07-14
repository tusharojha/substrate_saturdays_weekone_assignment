## Ownership

1. 

```rust
fn main() {
    // Use as many approaches as you can to make it work
    let x = String::from("hello, world");
    let y = x;
    println!("{}",y);
}
```

```rust
fn main() {
    // Use as many approaches as you can to make it work
    let mut x = String::from("hello, world");
    let y = x;
    x = y;
    println!("{}",x);
}
```

2.

```rust
fn main() {
    let s1 = String::from("hello, world");
    let s2 = take_ownership(s1);

    println!("{}", s2);
}

// Only modify the code below!
fn take_ownership(s: String) -> String {
    println!("{}", s);
    s
}
```

3.

```rust
fn main() {
    let s = give_ownership();
    println!("{}", s);
}

// Only modify the code below!
fn give_ownership() -> String {
    let s = String::from("hello, world");
    s
}

```

4.
```rust
fn main() {
    let s = String::from("hello, world");

    print_str(s.clone());

    println!("{}", s);
}

fn print_str(s: String)  {
    println!("{}",s)
}
```

5.
```rust
fn main() {
    let x = (1, 2, (), "hello");
    let y = x;
    println!("{:?}, {:?}", x, y);
}
```

### Mutability

6. 
```rust
fn main() {
    let s = String::from("hello, ");
    
    // Modify this line only !
    let mut s1 = s;

    s1.push_str("world");

    println!("Success!");
}
```

7.
```rust
fn main() {
    let x = Box::new(5);
    
    let mut y = Box::new(6);      // Implement this line, dont change other lines!
    
    *y = 4;
    
    assert_eq!(*x, 5);

    println!("Success!");
}

```

8.
```rust
fn main() {
   let t = (String::from("hello"), String::from("world"));

   let _s = t.0;

   // Modify this line only, don't use `_s`
   println!("{:?}", _s);
}
```

9.
```rust
fn main() {
   let t = (String::from("hello"), String::from("world"));

    // Fill the blanks
    let (s1, s2) = t.clone();

    println!("{:?}, {:?}, {:?}", s1, s2, t); // -> "hello", "world", ("hello", "world")
}

```