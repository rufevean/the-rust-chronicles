---
title: "01-Overview and Getting Started"
date: 2023-06-26T22:28:52+05:30
draft: false
---

## Why Rust?

You might be asking yourself, "Why should I learn Rust?"

Now let's take two approaches to this question.

If you are new to programming or someone who is eager to learn something new and exciting, learning anything will benefit you, whether it's JavaScript, Python, C, or **Rust**. Let's focus on **how** more than **why**, because if you are stuck on "why should I," you will never move forward. Programming is a vast field, and I am confident that you will enjoy it. **Welcome!**

Now let's take a technical approach to why we should learn Rust. Let's talk about its uses, advantages, and disadvantages.

According to [rust-lang.org](https://www.rust-lang.org/), Rust is "A language empowering everyone to build reliable and efficient software." To understand this well, let's talk about memory. Just like everything you do on your computer requires memory to work, programming languages also need memory to run. We will learn about various ways you can store data later through data structures and data types. Programming languages like C and C++, which are called low-level languages, use memory allocation functions like *malloc()*, *realloc()*, and *free()* to manage memory. High-level programming languages like Python, Java, and Go use **garbage collectors** where memory is managed by the programming language itself.

Why do we need to manage memory? Performance and security are the main reasons. Higher-level languages are slower compared to low-level languages because the garbage collector uses multiple algorithms to check if the memory is completely freed or not. In low-level languages, we handle it ourselves as I stated above using memory allocation functions. However, this causes a problem called **memory leak**.

Hackers love memory leaks as they provide a vulnerability to access a website's data. It's a significant problem because humans make mistakes, and sometimes we forget to free memory, just like we forget to turn off the light before going to bed. **Rust** solves this issue by using the concept of Ownership (more detailed on this later). Because of the ownership principle, there is a significant performance gain because there is no garbage collector to slow it down. Unlike C++, where you might forget to free memory, Rust automatically frees the memory itself once it's out of scope.

> Fun fact: Rust isn't a mainstream language yet like Python, C, or Java. So, if you find anyone learning or using Rust, appreciate them because they are doing it out of passion and love for Rust.

> Fun fact No. 2: Rust has been elected as the most loved programming language for eight years straight as of 2023.

