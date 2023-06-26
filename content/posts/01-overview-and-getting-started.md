---
title: "01-Overview and Getting Started"
date: 2023-06-26T22:28:52+05:30
draft: false
---

## why rust?

You might be asking yourself , why should i learn rust ? 

Now lets take two approaches on this question ,

 if you are new to programming or someone who is eager to learn something new and exicting. Learning anything is only going to benefit you, whether is javascript,python, c or  **Rust** .Lets focus on **How**  more than **Why** because if you are stuck on *why should i* , you are never going to go forward . Programming is a vast field and am confident that you will enjoy it . **Welcome !**

 Now lets take a technical approach on why we should learn rust , Lets take about its uses,its advantages and disadvanatages
  
- According to [rust-lang.org](https://www.rust-lang.org/), Rust is *A language empowering everyone
to build reliable and efficient software.* To understand this well, lets talk about memory.Just like everything you are doing in your computer needs memory to work, Programming langauges also need memory to run. We will learn about various ways you can store data later through Data structures and Data types.Programming languages like c, c++ which are called low level languages use memory allocation functions like *malloc()* , *realloc()* and to free that memory, they use *free()*. High level programming languages like python, Java and Go uses **Garbage collector** where memory is managed by the programming laanguage itself.

- Why do we need to manage memory? Performance and security are the main reasons. Higher level languages are slower compared to low level languages becuase the garbage collector uses multiple algorithms to check if the memory is completely freed or not. In low level algorithms, we do it ourselves as i stated above using memory allocation functions , But this causes a problem called **Memory leak** 

- Hackers love Memory leaks, its a good vulnerability to access the website's data and its a huge problem because humans make mistakes and sometime we forget to free the memory just like we forget to turn off the light before getting on bed.**Rust** kind of solves this issue by using the concept of Ownership ( more detailed on this later ). Because of Ownership principle,there is a good amount of performance gain because there is no garbage collector which slows it down and unlike 'c++' where you have might have forget it ,Rust free's the memeory itself once its out of scope.



> fun fact : rust isnt a main stream language yet like python, c or java . so if you find anyone learning or using rust , appreciate them because there are doing it for there passion and love for rust 

> fun fact No.2 : rust is elected as the most loved programming for 8 year straight as of 2023 
