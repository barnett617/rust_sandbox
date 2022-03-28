## Simple File Demo

### 1.Install Rust

```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

### 2.Check Version

```
rustup --version
```

> Recommand: Using Iterm to do the following

### 3.Create Hello World

```
touch hello.rs
```

```rs
fn main() {
    println!("Hello World!");
}
```

### 4.Compile

```
rustc hello.rs
```

### 5.Run the executable file

```
./hello
```

## Rust Project by Cargo

### 1.Check cargo version

```
cargo --version
cargo update
```

### 2.Init project

If there is an existing empty project folder

```
cargo init
```

Or using cargo to create a project folder with target name

```
cargo new project_name
```

### 3.Run the project

```
cargo run
```

### 4.Build for debugging

```
cargo build
```

### 5.Build for release

```
cargo build --release
```

### 6.Module Import

```
touch src/print.rs
```

```rs
pub fn run() {
    println!("Hello from print file");
}
```

Then rewrite main.rs as follows:

```rs
mod print
fn main() {
    print::run();
}
```

```
cargo run
```

### 7.Printing

#### 1)Simple Print

```rs
fn main() {
    println!(1);
}
```

#### 2)Basic Formating

```rs
fn main() {
    println!("Number {}", 1);
}
```

```rs
fn main() {
    println!("{} + {} = {}", 1, 1, 2);
}
```

#### 3)Positional Arguments

```rs
fn main() {
    println!(
        "{0} is from {1} and {0} loves {2}",
        "Wilson", "mass", "coding"
    );
}
```

#### 4)Named Arguments

```rs
fn main() {
    println!(
        "{name} likes {hobby}",
        name = "Wilson",
        hobby = "running"
    );
}
```

#### 5)Placeholder traits

```rs
fn main() {
    println!(
        "Binary: {:b}, Hex: {:x}, Octal: {:o}",
        10, 10, 10
    );
}
```

#### 6)Placeholder for debug traits

```rs
fn main() {
    println!(
        "{:?}",
        (12, true, "hello")
    );
}
```

#### 7)Basic math

```rs
fn main() {
    println!(
        "10 + 10 = {}",
        10 + 10
    );
}
```

### 8.Variables

#### 1)Basic variable

```rs
fn main() {
    let name = "Wilson";
    println!(
        "My name is {}",
        name
    );
}
```

#### 2)Mutable variable

```rs
fn main() {
    let mut age = 18;
    println!("I am {}", age);
    age = 28;
    println!("No, I am {}", age);
}
```

#### 3)Constant variable

```rs
fn main() {
    const ID: i32 = 001;
    println!("ID is {}", ID);
}
```

### 9. Types

```rs
fn main() {
    // Default i32
    let x = 1;
    // Default i64
    let y = 2.5;
    // Explicit type
    let z: i64 = 3121321321312;
    // Boolean
    let is_active: bool = true;
    // Boolean from expression
    let is_greater: bool = 10 < 5;
    // Char
    let a = 'a';
    // Char from unicode
    let emoji = '\u{1F550}';
    println!("{:?}", (x, y, z, is_active, is_greater, a, emoji));
}
```

### 10. Strings

```rs
fn main() {
    let hello = "Hello";
    println!("hello is: {}", hello);

    let mut hello_str = String::from("Hello ");
    println!("hello_str is: {}", hello_str);

    // Get length
    let len = hello_str.len();
    println!("len is: {}", len);

    // Push char
    hello_str.push('W');
    println!("hello_str after pushing W: {}", hello_str);

    // Push string
    hello_str.push_str("orld!");
    println!("hello_str after pushing orld!: {}", hello_str);

    // Capacity in bytes
    let capacity = hello_str.capacity();
    println!("capacity in bytes: {}", capacity);

    // Check empty
    let is_empty = hello_str.is_empty();
    println!("Is hello_str empty: {}", is_empty);

    // Check contain
    let is_contain = hello_str.contains("World");
    println!("Does hello_str contains World: {}", is_contain);

    // Replace
    let replace_result = hello_str.replace("World", "Wilson");
    println!("Replacing result: {}", replace_result);
    println!("hello_str after replacing World with Wilson: {}", hello_str);

    // Loop through words from splited
    for word in hello_str.split_whitespace() {
        println!("looping...");
        println!("word: {}", word);
    }

    // Create string with capacity
    let mut str_with_capacity = String::with_capacity(10);
    println!("string generated from specific capacity: {}", str_with_capacity);
    str_with_capacity.push('a');
    str_with_capacity.push('b');
    println!("specific capacity string after push chars: {}", str_with_capacity);

    // Assert: nothing if pass, or throw fail reasons
    assert_eq!(2, str_with_capacity.len());
    assert_eq!(10, str_with_capacity.capacity());
}
```

Output:

```
hello is: Hello
hello_str is: Hello 
len is: 6
hello_str after pushing W: Hello W
hello_str after pushing orld!: Hello World!
capacity in bytes: 12
Is hello_str empty: false
Does hello_str contains World: true
Replacing result: Hello Wilson!
hello_str after replacing World with Wilson: Hello World!
looping...
word: Hello
looping...
word: World!
string generated from specific capacity: 
specific capacity string after push chars: ab
```