# About
I am creating this tutorial as I learn swift, I am going to document everything I learn so that maybe some of you can learn along with me. Please note that this is in no way a final draft, and I am **not a swift expert**.

## Text Editor
I really like to use atom. If you like to use  a different text editor thats fine - but you will have to find out if/how it supports swift. For atom I used the [Swift-Debugger package](https://atom.io/packages/swift-debugger) and it has worked well for me so far.

## Installing Swift
You can install swift using [this guid](https://github.com/apple/swift#getting-started), however if you are on a mac and have xcode already installed, you may already have it.

## REPL
The REPL (Read–Eval–Print Loop) is a good way to play around with a language for the first time. We will use the repl to learn the basics of swift. If you have some experience with swift, you may want to skip this part.

To start the repl just type the following into terminal:
```
$ swift
```

TIP: the repl works similar to the CLI in the cense that you can press up-arrow to go to the last run command.

### Hello World!

Now you should see something like this:
```
1>
```

You can type any bit of swift code you want here and it will evaluate it for you the same way a swift script would. For example, the following code will print out hello world.

```
4> print("Hello World")
Hello World
5>
```

### Variables

In swift you can use `var` to declare a variable and `let` to declare a constant.

For example, if I **let** `i` equal `0` and then change it to `3`, I will get this error:
```
 13> let i = 0
i: Int = 0
 14> i = 3
error: repl.swift:14:3: error: cannot assign to value: 'i' is a 'let' constant
i = 3
~ ^

repl.swift:13:1: note: change 'let' to 'var' to make it mutable
let i = 0
^~~
var
```

### Importing modules

Lets say we want to get a random number, for this we have to import a module. On mac we will import the Darwin module (on linux you can import Glibc). In the repl just type `> import Darwin` then once its does we can get our random number with `arc4random_uniform(10)` (again this will be slightly different on linux but I trust any linux user to be able to find the solution with a quick google search).

### Arrays

We define an array like this:

```
let bears = ["black bears", "brown bears", "polar bears", "grizzly bears", "pandas", "not pandas"]
```

then we can simply call any of its elements like so:
```
print(bears[0]) //prints the first element in the array
```

### For loops

These are really great in swift, with the following code you can print out everything in an array:

```
for bear in bears {
  print(bear)
}
```

### Changing types

If we wanted to, say, compare an integer to a random number, we will have a problem because our  random number will be type `UInt32` and our integer will (obviously) be type `Int`. To convert from any one type to an Int we can do `Int(mynotint)`. Here are how to convert integers and strings:

`Int(x)` -> returns an int
`String(name)` -> returns a string


### Finishing up with the repl

Now to put everything together we can make the following program that randomly skips over certain elements in an array:

```
import Darwin

let ints = [0,1,0,4,2,3,1,0,2,3,2,1,0,1,0,3,4,2]
let randomNumber = Int(arc4random_uniform(5)) //or something else...

for element in ints {
  if element == randomNumber {
    print("skiped!")
  }else{
    print(element)
  }
}
```

This will create an array and go through, printing out every element except the ones it randomly skips.

### Exiting

To exit the repl just type `:exit`. `:` is where you can type repl commands, but I don't know about that yet so we will have to go over that later.

## Project