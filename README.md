# Rust
My Rust Notes.


# Basic cli

## update
```
rustup update stable
```
## version
```
rustc --version
rustup --version
cargo --version
```
## compile a file
```
rustc main.rs
```
## initiate a project
```
cargo new <project-name>
cd <project-name>
```
## initiate a project in same folder
```
cargo init
```
## compile a project
```
cargo build
```
## compile and run a project
```
cargo run
```
## install a package
```
cargo install <package-name>
```
## install a package from a git repository
```
cargo install <package-name> --git <git-url>
```
## compile a project with specific target
```
cargo build --target x86_64-unknown-linux-gnu
```
## compile a project with specific target and specific profile
```
cargo build --target x86_64-unknown-linux-gnu --release
```
## compile a project with specific profile
```
cargo build --release
```
## compile a project with specific profile and specific features
```
cargo build --release --features "test"
```
## compile a project with specific features
```
cargo build --features "test"
```


# Codes

## funtion
```rust
fn main() {
    println!("Hello, world!");
}
```
## public function
```rust
pub fn main() {
    println!("Hello, world!");
}
```
## import a public function sum and sub from file "maths.rs"
```rust
// maths.rs
pub fn sum(a: i32, b: i32) -> i32 {
    a + b
}
pub fn sub(a: i32, b: i32) -> i32 {
    a - b
}

```
```rust
// main.rs
mod maths;
fn main() {
    println!("{}", maths::sum(1, 2));
    println!("{}", maths::sub(1, 2));
}
```
```rust
// main.rs
use maths::{sum, sub};
fn main() {
    println!("{}", sum(1, 2));
    println!("{}", sub(1, 2));
}
```
## print
```rust
println!("Hello, world!");
println!("{}", "Hello, world!");
println!("{} {}", "Hello", "world");
println!("{1} {0}", "Hello", "world");
println!("{0} {0} {1}", "Hello", "world",); // Hello Hello world
println!("{x}", x="Hello, world!");
println!("{:b}", 10); // binary
println!("{:x}", 10); // hexadecimal
println!("{:o}", 10); // octal
println!("{:?}", ("hello", 44, true)); // debug
println!("{:?}", (1, 2, 3)); // tuple
println!("{:?}", &[1, 2, 3]); // slice
println!("{:?}", &mut [1, 2, 3]); // slice

```
## variable (immutable by default (cant change))
```rust
let x = 10;
let y = 20;
let z = x + y;
println!("{}", z);
```
## variable (mutable)
```rust
let mut x = 10;
x = 20;
println!("{}", x);
```
## constant (immutable by default (cant change))
```rust
const X: i32 = 10;
const Y: i32 = 20;
const Z: i32 = X + Y;
println!("{}", Z);
```
## assign multiple variables
```rust
let (x, y) = (10, 20);
println!("{}", x + y);
```
 ## variable with type
```rust
let a: i32 = 10;
let b: f32 = 10.0;
let c: bool = true;
let d: char = 'a';
let e: String = "hello".to_string();
let f: i64 = 1000000000000;
let g: 


```
## range of a data type
```rust
println!("{}", std::i32::MAX);
println!("{}", std::i64::MAX);
println!("{}", std::u32::MAX);
println!("{}", std::u64::MAX);
println!("{}", std::f32::MAX);
println!("{}", std::f64::MAX);
println!("{}", std::i32::MIN);
println!("{}", std::i64::MIN);
println!("{}", std::u32::MIN);
println!("{}", std::u64::MIN);
println!("{}", std::f32::MIN);
println!("{}", std::f64::MIN);
```
## fixed length strings
```
let s = "hello";
println!("{}", s);
```
## mutable strings
```rust
let mut s = String::from("hello");
s.push_str(", world!"); // push_str for string
s.push('!'); // push for char
println!("{}", s);
```
## immutable strings
```rust
let s = String::from("hello");
println!("{}", s);
```
## get length of a string
```rust
let s = String::from("hello");
println!("{}", s.len());
```
## string methods
```rust
let s = String::from("hello");
s.push_str(", world!");
s.contains("world");
s.starts_with("hello");
s.ends_with("world");
s.replace("world", "rust");
s.trim();
s.split_whitespace();
s.split("");
```
## iterate over a string
```rust
let s = String::from("hello");
for c in s.chars() {
    println!("{}", c);
}
```
## iterate over a string with index
```rust
let s = String::from("hello");
for (i, c) in s.chars().enumerate() {
    println!("{} {}", i, c);
}
```
## tuple ()
```rust
let t = (1, 2, 3);
println!("{}", t.0);
println!("{}", t.1);
println!("{}", t.2);
```
## tuple with type
```rust
let t: (i32, f32, String) = (1, 2.0, String::from("hello"));
println!("{}", t.0);
println!("{}", t.1);
println!("{}", t.2);
```
## array
```rust
let a = [1, 2, 3];
println!("{}", a[0]);
```
## array with type
```rust
let a: [i32; 3] = [1, 2, 3]; // type i32 with length 3 (fixed)
println!("{}", a[0]);
```
## array with type and mutable
```rust
let mut a: [i32; 3] = [1, 2, 3]; // type i32 with length 3 (fixed)
a[0] = 10;
println!("{}", a[0]);
```
## slice
```rust
let a = [1, 2, 3, 4, 5];
let s = &a[1..3]; // [2, 3]
println!("{}", s[0]);
```
## vector
```rust
let v = vec![1, 2, 3, 4, 5];
println!("{}", v[0]);
```
## vector with type
```rust
let v: Vec<i32> = vec![1, 2, 3, 4, 5];
println!("{}", v[0]);
```
## vector with type and mutable
```rust
let mut v: Vec<i32> = vec![1, 2, 3, 4, 5];
v[0] = 10;
println!("{}", v[0]);
```
## vector methods
```rust
let v = vec![1, 2, 3, 4, 5];
v.push(6);
v.pop();
println!("{}", v[5]);
```
## vector loop
```rust
let v = vec![1, 2, 3, 4, 5];
for i in v.iter() {
    println!("{}", i);
}
```
## vector loop and mutate
```rust
let mut v = vec![1, 2, 3, 4, 5];
for i in v.iter_mut() {
    *i += 1;
}
```
## vector loop and mutate with index
```rust
let mut v = vec![1, 2, 3, 4, 5];
for (i, x) in v.iter_mut().enumerate() {
    v[i] += 1;
}
```
## conditionals
```rust
let x = 10;
if x == 10 {
    println!("x is 10");
} else if x == 20 {
    println!("x is 20");
} else {
    println!("x is not 10 or 20");
}
```
## conditionals with if let
```rust
let x = Some(10);
if let Some(y) = x {
    println!("{}", y);
}
```
## loops
```rust
let mut x = 0;
// infinite loop
loop {
    x += 1;
    if x == 10 {
        break;
    }
}
// infinite loop with continue
loop {
    x += 1;
    if x == 10 {
        continue;
    }
    println!("{}", x);
}
// while loop
while x < 10 {
    x += 1;
    println!("{}", x);
}
// for range
for i in 0..10 {
    println!("{}", i);
}

```
## functions
```rust
fn add(x: i32, y: i32) -> i32 { // (->) i32 is return type
    x + y // no semicolon  = return statement
}
```
## pointers
```rust
let x = 10;
let y = &x; // y is a reference to x
println!("{}", y);
```
## pointers with type
```rust
let x = 10;
let y: &i32 = &x; // y is a reference to x
println!("{}", y);
```
## pointers with type and mutable
```rust
let mut x = 10;
let y: &mut i32 = &mut x; // y is a reference to x
println!("{}", y);
```
## structs
```rust
struct Point {
    x: i32,
    y: i32,
}
```
## structs with type
```rust
struct Point {
    x: i32,
    y: i32,
}
let origin = Point { x: 0, y: 0 };  
```
## structs with type and mutable
```rust
struct Point {
    x: i32,
    y: i32,
}
let mut origin = Point { x: 0, y: 0 };
origin.x = 10;
```
## tuple structs
```rust
struct Point(i32, i32);
let mut point = Point(1, 2);
point.0 = 3;
println!("{}", point.0);
```
## impl
```rust
struct Point {
    x: i32,
    y: i32,
}
impl Point {
    fn new(x: &i32, y: &i32) -> Point {
        Point { x: x, y: y }
    }
}
let origin = Point::new(0, 0);
println!("x: {}; y: {}", origin.x, origin.y);
```
