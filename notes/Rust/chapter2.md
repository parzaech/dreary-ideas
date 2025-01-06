# Chapter 2

Processing a guess:

```rust
use std::io;

fn main() {
	println!("Guess the number!");
	println!("Please input your guess.");

	let mut guess = String::new();

	io::stdin()
    .read_line(&mut guess)
    .expect("Failed to read line");

	println!("You guessed: {}", guess);
}
```

-to obtain input from users we need to bring the library in to the scope of every program. using `use` . The `io` library comes from the standard library, known as `std` .

-already defined items in standard library https://doc.rust-lang.org/std/prelude/index.html. 

-if a type isn’t in the prelude we have to bring that type into scope `std::io` .

-`let` statement to create the variable.

-Variables are **immutable** by default.

-To make a variable mutable, we add `mut` before the variable name.

-`String::new`, a function that returns a new instance of a `String`. It is a string type provided by the standard library that is a growable, UTF-8 encoded bit of text.

-This `new` function creates a new, empty string.

-In full, the `let mut guess = String::new();` line has created a mutable variable that is currently bound to a new, empty instance of a `String` .

-The `stdin` function returns an instance of [`std::io::Stdin`](https://doc.rust-lang.org/std/io/struct.Stdin.html), which is a type that represents a handle to the standard input for your terminal.

-can also be called as `std::io::stdin`.

-read_line method is called and `&mut guess` is passed as argument to tell it where to store the string. though the real job of read_line method is to append user input into the string(without overwriting its content).

-references are also mutable and immutable like variables in rust.Hence, you need to write `&mut guess` rather than `&guess` to make it mutable. 

-read_line method also returns a value `Result` . It is an [*enumeration*](https://doc.rust-lang.org/book/ch06-00-enums.html), often called an *enum*, which is a type that can be in one of multiple possible states. We call each possible state a *variant*.

-`Result`’s variants are `Ok` and `Err` .

-An instance of `Result` has an [`expect` method](https://doc.rust-lang.org/std/result/enum.Result.html#method.expect) that you can call.

-If this instance of `Result` is an `Err` value, `expect` will cause the program to crash and display the message that you passed as an argument to `expect`.

-If this instance of `Result` is an `Ok` value, `expect` will take the return value that `Ok` is holding and return just that value to you so you can use it. In this case, that value is the **number of bytes in the user’s input.**

-if we don’t call expect, we will get a warning when we compile it.

-set of `{}` is a placeholder, that holds the value in place.

-if there are many expressions to print then maintain a same order comma separated list. 

-can also do like `“x = {x}”` 

Generating a secret number: