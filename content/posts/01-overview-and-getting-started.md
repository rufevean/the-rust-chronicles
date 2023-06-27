---
title: "01-Getting started with Rust"
date: 2023-06-26T22:28:52+05:30
draft: false
---

## Why Rust?

You might be asking yourself, "Why should I learn Rust?"

Now let's take two approaches to this question.

If you are new to programming or someone who is eager to learn something new and exciting, learning anything will benefit you, whether it's JavaScript, Python, C, or **Rust**. Let's focus on **how** more than **why**, because if you are stuck on "why should I," you will never move forward. Programming is a vast field, and I am confident that you will enjoy it. **Welcome!**

Now let's take a technical approach to why we should learn Rust. 

According to [rust-lang.org](https://www.rust-lang.org/), Rust is "A language empowering everyone to build reliable and efficient software." To understand this well, let's talk about memory. Just like everything you do on your computer requires memory to work, programming languages also need memory to run. We will learn about various ways you can store data later through data structures and data types. Programming languages like C and C++, which are called low-level languages, use memory allocation functions like *malloc()*, *realloc()*, and *free()* to manage memory. High-level programming languages like Python, Java, and Go use **garbage collectors** where memory is managed by the programming language itself.

Why do we need to manage memory? Performance and security are the main reasons. Higher-level languages are slower compared to low-level languages because the garbage collector uses multiple algorithms to check if the memory is completely freed or not. In low-level languages, we handle it ourselves as I stated above using memory allocation functions. However, this causes a problem called **memory leak**.

Hackers love memory leaks as they provide a vulnerability to access a website's data. It's a significant problem because humans make mistakes, and sometimes we forget to free memory, just like we forget to turn off the light before going to bed. **Rust** solves this issue by using the concept of Ownership (more detailed on this later). Because of the ownership principle, there is a significant performance gain because there is no garbage collector to slow it down. Unlike C++, where you might forget to free memory, Rust automatically frees the memory itself once it's out of scope.

> Fun fact: Rust isn't a mainstream language yet like Python, C, or Java. So, if you find anyone learning or using Rust, appreciate them because they are doing it out of passion and love for Rust.

> Fun fact No. 2: Rust has been elected as the most loved programming language for eight years straight as of 2023.



## Hello, World!

For any programming language, it's a good start to code a **Hello, World!** program. Let's take it a bit further here and try to understand why it is coded that way.

```rust
fn main() {
    println!("Hello, World!");
}
```

Let's break down the code into two parts:

```rust
fn main() {

}
```

In Rust, `fn` denotes a **function**. We can think of functions like formulas in math, where you give some inputs and get some outputs.

`main` is the name of the function and, in Rust (as in many programming languages), the `main` function is the entry point. This is where the compiler (more on this later) checks first.

Moving forward, there are two types of brackets in this function: `( )` and `{ }`. The first one `( )` is for taking inputs, which we call arguments, and the latter `{ }` are block delimiters that specify the block of code for this function.

> "{}" and "()" are also used for other purposes, here is an good article to explore them [doc.rust-lang]("https://doc.rust-lang.org/book/appendix-02-operators.html")

> fun fact : every function can take arguments in () except the `main` function

```rust
println!("Hello, World!");
```

Deconstructing this line gives us three parts:

- `println!()` is a **macro** used to print something to the console. We can also use `println` without the `!`, but it would cause a formatting error.
- "Hello, World!" is a `&str`, which is a string slice, a part of a string but not the whole string. Don't be confused; you will understand how strings work in Rust as you progress.
- To finish off, we have `;` (semicolon), which is used in many languages to separate statements and terminate code blocks. We can think of it like `,` (comma) in an English sentence.

> Tip: Rust has a great compiler. It is strict, but that's how good programs are made. So, if you find yourself facing a pile of errors, just know that it only wants you to be better and write good code.

## Under the Hood

Now that you have an idea of how to write a **Hello, World!** program in Rust, let's dig down into what happens once we compile and run it.

### Compilation

Every programming language has a file extension for its source code (`.rs` for Rust, just like `.exe` for an application). When you use the Rust compiler ([rustc](https://www.rust-lang.org/tools/install)), it takes the source code and generates an executable binary file. It then links it with all the dependencies (required software to execute the program without errors) and system libraries.

> The executable can have different extensions depending on the operating system: `.exe` for Windows, `.app` for macOS, and no extension by default for Linux

> Thought: Everything you see on a computer is just transmitters turning on and off with binary signals. Isn't it amazing that there's a whole universe just using 0s and 1s?

### Execution

Once the compilation and linking processes are completed, and you execute the program, the operating system loads it into memory and starts executing it. As we discussed, the `main` function is used as the entry point, so the operating system detects the `main` function and begins executing the code inside it.

After the function is executed, the program terminates, and control is returned to the operating system, which reclaims the resources that were allocated to that program.
