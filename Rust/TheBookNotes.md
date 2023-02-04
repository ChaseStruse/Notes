# The Book

[The Book](https://doc.rust-lang.org/book/)

## Getting Started

Anatomy of a Rust Program 

```
fn main() {
            
}           
```

main functions are important due to them being the first function that gets run in a rust program. \
Rust requires {} and functions are defined with fn \
`println!("Hello, world!");` // This is how you print to the console in rust \

***
Things to note:
- Rust indents with four spaces not tabs
- `println!` calls a macro called `println` this is indicated by the `!` more about this later
- Most lines of rust code end with a semicolon
<br />

Compile rust with `rustc` command <br />
ex: `rustc main.rs` <br />
run the shell script created  <br />
ex: `./main`  <br />
<br />
Hello Cargo <br />
- Cargo is rusts build system and package manager                       <br />
- Used to manage rust projects because cargo handles most tasks for you <br />
- Ex: Cargo handles building your code                                  <br />
- Ex: Cargo handles downloading libraries code is dependent on          <br />
- Ex: Cargo builds those libraries as well                              <br />
<br />

## Common Programming Concepts

[Chapter Found Here](https://doc.rust-lang.org/book/ch03-01-variables-and-mutability.html) <br /> 

Variables and Mutability in Rust are different than most languages. By defualt a variable in rust is immutable (can't be changed). <br />
To declare a standard variable in rust you do the following: `let x: u32 = 1;   // u32 is optional you dont have to specify type` <br />
To declare a mutable variable you do the following: `let mut x: u32 = 1;` <br />
To declare a constant variable you do the following: `const HOURS_IN_THE_DAY: u32 = 24;` <br />
<br />

Shadowing <br />
Rust allows you to shadow a variable which means you can declare a variable with the same name. Confusing? Heres a code example: <br />
```
let x = 5;
let x = x + 5;
```
One major difference between shadowing and mut is that you can change the data type. Confusing? Heres a code example: <br />
```
let spaces = "    ";
let spaces = spaces.len();
```
<br />

Data Types <br />
Rust is a statically typed languaged meaning rust must know the type of all variables at compile time. Most of the time the compiler <br />
will infer the data type based on the data given to the variable. <br />
<br />

Compound Types <br />
To declare a tuple you do the following: `let tup: (i32, f64, u8) = (500, 1.2, 1);` <br />
To access data in a tuple you do the following: `let (x, y, z) = tup;  //x = 500, y = 1.2, z = 1` <br />
Another way to access data in a tuple is to do the following: `let five_hundred = tup.0;` <br />
<br />
To declare an array you do the following: `let arr: [i32, 4] = [1, 2, 3, 4];` <br />
To access data in an array you do the following: `arr[0];  //1` <br />
<br />

Functions <br />
To declare a function you do the following:
```
fn test_func() {

}
```

To declare a function with parameters you do the following:
```
fn test_func(x: i32){

}
```

To declare a function with a return value you do the following:
```
fn return_x_please(x: i32) -> i32 {
    return x;
}
```


Control Statements <br />
To use an if/elseif/else statment you do the following:
```
if 1 < 5 {
    println!("Nice");
} else if 1 > 5 {
    println!("Wait what?");
} else {
    println!("Not nice");
}
```

You can use an if statement in a variable declaration by doing the following: <br />
`let x = if true { 5 } else { 6 };  // x = 5` <br />

***
Loops <br />

This code block creates a loop that can only be exited manually by stopping it in the console
```
loop {
    println!("again!");
}
```

Return values from the loop by doing the following:
```
let mut counter = 0;

let result = loop {
    counter += 1;

    if counter == 10 {
        break counter * 2;
    }
};

// result = counter * 2
```

In the case of nested loops you can use loop labels to identify the outermost loop.
```
    let mut count = 0;
    'counting_up: loop {
        println!("count = {count}");
        let mut remaining = 10;

        loop {
            println!("remaining = {remaining}");
            if remaining == 9 {
                break;
            }
            if count == 2 {
                break 'counting_up;
            }
            remaining -= 1;
        }

        count += 1;
    }
```
In this example the loop label is 'counting_up, and that loop will be broken when count = 2, the inner most loop is broken when remaining = 9 <br /> 
<br /> 
While Loops  <br />
```
    let mut number = 3;

    while number != 0 {
        println!("{number}!");

        number -= 1;
    }
```
<br />
For Loops <br />
```
    let a = [10, 20, 30, 40, 50];

    for element in a {
        println!("the value is: {element}");
    }
```
Here is another example using rev() <br />
```
    for number in (1..4).rev() {
        println!("{number}!");
    }
    println!("LIFTOFF!!!");
```
<br />

## Ownership

What is ownership in rust? <br /> 
Ownership is a set of rules that govern how Rust program manages memory<br /> 
Unlike other languages Rust manages memory by using a set of rules that the compiler checks <br /> 
<br /> 
The Stack and the Heap <br /> 
The stack and the heap is an extremely important concept when it comes to systems programming languages like Rust. <br /> 
It is important to distinguish whether the value is on the stack or the heap because that affects how the language behaves. <br />  
Notes regarding Stack vs Heap <br /> 
- Stack stores the values it recieves in order and in turn removes the values in opposite order, last in first out 
- Adding data to the stack is referred to as pushing onto the stack
- Removing data from the stack is referred to as popping off the stack
- Heap is less organized
- When you put data in the heap you request a certain amount of space to be allocated, during this the memory allocator will return a pointer once the location is found
- That process is known as either allocating on the heap or just allocating 
- You can store the value on the stack but to get the actual value you have to access the heap with the pointer
- Pushing to the stack is faster than allocating on the Heap
- Accessing data on the stack is also faster than accessing data on the heap due to having to follow the pointer to get to the value
<br /> 
Ownership Rules
- Each value in Rust has an owner
- There can only be one owner at a time 
- When owner goes out of scope the value is dropped
<br /> 
For these examples it will be using the String data type. <br />
```
#![allow(unused)]
fn main() {
    let s = String::from("hello");
}
```
In this example we are using a String type that manages data allocated on the heap thus making room to change the data size after compile time <br />
We can mutate this string in the following ways:
```
fn main() {
    let mut s = String::from("hello");

    s.push_str(", world!"); // push_str() appends a literal to a String

    println!("{}", s); // This will print `hello, world!`
}
```


