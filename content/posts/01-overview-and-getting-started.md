---
title: "01-Overview and Getting Started"
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


## Hello,world!

For any programming language, its a good start by coding a **Hello,world!**  program, Lets take it a bit furthur here, rather than just coding it , lets try to learn why is it coded that way


```
fn main(){
    println!("Hello,World!");
}

```
lets understand it by first seperating the items in this codeblock into two parts

```
fn main(){

}
```

**fn** denotes **Function**.We can think of functions like a formula in maths, you give some inputs, you get some outputs.

**main** here is the name of the function and also In Rust , just like in many programming languages , **main** function is the entry point , this is where the compiler(more on this later) checks first.

moving forward there are two types of brackets in this function, '( )' and '{ }', The first one '( )' is for taking inputs which we call arguements and the latter '{ }' are block delimiters, its specifies the block of code of this function

> note : '()' and '{}' are also used for other purposes, Here is a good reference of them [doc.rust-lang]("https://doc.rust-lang.org/book/appendix-02-operators.html")


```
println!("Hello,World!");

```

Deconstructing this line gives us three parts 

**println!()** which is a **macro** is used to print something into the console.we can also using **println** without the **!** to print something but here it cause an formatting error

```
error[E0423]: expected function, found macro `println`                                                  
 --> test1.rs:2:5                                                                                       
  |                                                                                                     
2 |     println("hello");                                                                               
  |     ^^^^^^^ not a function                                                                          
  |                                                                                                     
help: use `!` to invoke the macro                                                                       
  |                                                                                                     
2 |     println!("hello");                                                                              
  |            +                                                                                        
                                                                                                        
error: aborting due to previous error                                                                   
                                                                                                        
For more information about this error, try `rustc --explain E0423`.

```


 "Hello,world!" is a &str which is a String slice which is a part of a String, not a String but a part of it. Dont be confused , you will understand how Strings work in rust as you progress forward.

To finish of the things we have ";"(semi-colon),which is used in many languages to seperate statements and terminate code blocks, we can think of it like ','(comma) in english sentence .

> tip : Rust has a great compiler,It is strict but thats how good programs are made. So if you found yourself in a pile of errors, just know that it only wants you to be better and write good code



## Under the hood


Now that you have an idea how we can write an **Hello,World!** program in rust, lets dig down on what happens once we compile and run it

### Compilation

Every Programming languages has an extension to its file name (.rs for rust just like a .exe for an application).Once you use the Rust compiler ([rustc]("https://www.rust-lang.org/tools/install")), The compiler takes the source code and generates an executable binary file and Links it with all the dependencies ( required software to execute the program without any errors) and system libraries.

> The executable can be in the form .exe for Windows , .app for macOS and for linux, it can be given any extension but by default it doesnt have one (i use arch btw)

> Think :  everyone thing you see on a computer, is just transmitters just getting on and off with binary signals, isnt it so amazing that there a whole universe just using 0s and 1s?

### Execution 

Once the compilation and linking processes are completed and you execute the program , the os loads it int memory and start executing it. As we discussed about the **main** function is used as the entry point , so the os detects the main function and begins executing code inside it .

After the function is executed , the program terminates and the control is returned to the operating system, it reclaims  the resources that were allocated to that program.
