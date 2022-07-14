## Char, bool & unit

### char

1.
```rust
use std::mem::size_of_val;
fn main() {
    let c1 = 'a';
    assert_eq!(size_of_val(&c1),4); 

    let c2 = '中';
    assert_eq!(size_of_val(&c2),4); 

    println!("Success!");
} 
```

2.
```rust
fn main() {
    let c1 = '中';
    print_char(c1);
} 

fn print_char(c : char) {
    println!("{}", c);
}
```

### Bool

3.
```rust
fn main() {
    let _f: bool = false;

    let t = true;
    if t {
        println!("Success!");
    }
} 
```

4.
```rust
fn main() {
    let f = true;
    let t = true && false;
    assert_eq!(!t, f);

    println!("Success!");
}
```

### Unit type

5.
```rust
fn main() {
    let _v: () = ();

    // let v = (2, 3);
    assert_eq!(_v, implicitly_ret_unit());

    println!("Success!");
}

fn implicitly_ret_unit() {
    println!("I will return a ()");
}

// Don't use this one
fn explicitly_ret_unit() -> () {
    println!("I will return a ()");
}
```

6. 🌟🌟 What's the size of the unit type?

```rust
use std::mem::size_of_val;
fn main() {
    let unit: () = ();
    assert!(size_of_val(&unit) == 0);

    println!("Success!");
}
```