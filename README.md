# Rust from Scratch

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

### 7.Printing Demos

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