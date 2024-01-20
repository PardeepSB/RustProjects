# Guessing Game

To obtain input then print result as output, need ```io``` library. This library comes from the standard library, ```std```:

```rust
use std::io;
```

Rust has a set of items defines in the standard library that it brings into the scope of every program. This set is called the *prelude*, as you can see everything in it is in the standard library

## Storing Values with Variables

A variable to store a user input can be created like this:

```rust
let mut variable_name = String::new();
```
This line creates a mutable variable that is currently bound to a new, empty instance of a ```String```.

We use the ```let``` statement to create a variable. Here is another example:

```rust
let apples = 5;
```
This line creates a new variable called ```apples``` and binds it to the value 5. In Rust, variables are **immutable** by default, meaning **once we give the variable a value, the value won't change**.

To make a value mutable, add ```mut``` before a variable name:

```rust
let apples = 5;      //immutable
let mut bananas = 5; //mutable
```

## Receiving User Input

```stdin``` function from the ```io``` module allows handling of user input:

```rust
io::stdin()
    .read_line(&mut guess)
```

If the io library is not imported at the beginning of the program, the function can still be used by writing:

```rust
std::io::stdin()
```

The next line following ```stdin()``` calls the ```read_line``` method on standard input handle to get input from the user. Also, passing ```&mut guess``` as argument tells it what string to store the user input in.

```rust
    .read_line(&mut guess)
```
The job of read_line is to take whatever the user types into standard input and append it into a string (without overwriting its contents). ```&``` indicates that this argument is a reference, which allows multiple parts of code access one piece of data without needing to copy that data into memory multiple times.

```Note: References are immmutable by default. Hence, you need to write ```&mut guess``` rather than ```&guess``` to make it mutable```

## Handling Potential Failure with Result

```rust
    .expect("Error Message");
```

This line could have been written as:
```rust
io:stdin().read_line(&mut guess).expect("Error Message");
```
however it is difficult to read, thus better to separate.

```read_line()``` also returns a ```Result``` value, which is an enum, with a possible state, ```variant```.

```Result```'s variants are ```Ok``` and ```Err```. ```Err``` means the operation failed, and it contains information about how/why the operation failed. 

## Printing Values with println! Placeholders

Aside from closing curly brackets, there's only one more way to print values with placeholders.

```rust
println!("You Guessed: {guess}");

//or

let x = 5;
let y = 10;
println!("x = {x} and y + 2 = {}", y + 2);
```

