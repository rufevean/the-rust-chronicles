---
title: "02-Understanding Memory Mangement in Rust"
date: 2023-07-01T11:36:22+05:30
draft: true
---

Today, We are going to discuss about how rust manages its memory and why rust is unique from other programming languages in managing memory.Before going into deep , lets know how data is managed in rust.

Rust mainly uses Stack and Heap datastructures to manange its memory.Before learning about stack aand heap , lets learn about datatypes which uses these stack and heap.

## Datatypes

There are multiple types of data but for today, we are going to discuss about primitive and composite data types.

primitive datatypes such as i32,u32,char,bool,f64 etc have a fixed size determined at compile-time.They are typically stored on the stack when declared as local variables . The stack allocation ensures effiecient and automatic memory management for these types

while as composite datatypes such as strings,enums and structs can have dynamic memory requirements, which may result in their data being stored on the heap.

> even though some parts of composite types,like enum or struct fields which contain primitive types may still use stack, other parts that require dynamic size are typically stored on the heap

**lets walkthrough a simple example of memory management of a string to understand this better**

> For installation of rust, you can refer to this [website]("https://www.rust-lang.org/tools/install")

>For Geting started with rust, you can refer to this [article]("https://rufevean.github.io/the-rust-chronicles/posts/01-overview-and-getting-started/")

Now,lets get started with creating a string

```
fn main(){
    let best_programming_language = String::from("Rust");
}
```

> this is just one of multiple ways we can initiate or create a string,but i couldn't find an article regarding it . if you have any, you are very welcome to contribute into the repository  .

string is a complex type,its dynamic size wont let it be stored in the stack, instead it needs to be stored in heap.

the data is stored in two parts, the actual value of string is stored at a location in heap, but the details of the location(pointer), length and the capacity which are primitive value are stored in stack

![string implementation](./stringimplementation.png)
Before diving into the principles of memory Mangement is rust, lets get a general idea about stack and heap  
### Stack

- stack follows last in first out principle , where last element to go in comes out first.

{{$image := resources.Get"/stack.png"}}

stack is simple yet efficient,the memory managed through the stack is faster and efficient.

> stack uses contiguos memory allocation, and with improve memory locality results in faster memory access times, enhancing overall performance

In stack,values have fixed size at the runtime,so primitive data types mainly tend to use them.

> Stacks are also used in function calls to manage local variables, function parameters, return 
address,enabling effiecient memory allocation and control flow during program execution

### Heap

- In heap, required amount of free space is located and memory is allocated there,

- Accessing memory in heap is slow compared to stack as heap manages memory dynamically, accessing memory involves following pointers which adds overhead and can slow down memory acces

- Allocation and deallocation in heap are also more complex comapred to stack which makes it slower compared to stack.


> as there is no contiguos memory allocation , memory locality isnt guaranteed


Traditionally, languages have fallen into two broad categories 

- automatic memory management at runtime which offers full safety like Java,Python,Go,Haskell etc
- manual memory management which offers full control over memory like C,C++,Pascal etc

Rust offers full control and safety via compile time enforcement of correct memory management using **Ownership** concept

