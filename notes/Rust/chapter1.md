# Rust

### Chapter 1

-rustup(oilup)

-.rs extension

-rustc

-`println!` calls a Rust macro :: if it called a function then dont use  `!` 

-a `!` means that you’re calling a macro instead of a normal function and that macros don’t always follow the same rules as functions

-`$ rustc [main.rs](http://main.rs/)`  Rust outputs a binary executable

-Rust is an *ahead-of-time compiled* language, meaning you can compile a program and give the executable to someone else, and they can run it even without having Rust installed.

-Cargo handles::building your code, downloading the libraries your code depends on, and building those libraries::libraries = dependencies

-`cargo new hello_cargo` :: directory with a *Cargo.toml* file and a *src* directory with a *main.rs* file inside :: also creates git files to ignore that :: `cargo new --vcs=git`

-[*TOML*](https://toml.io/) (*Tom’s Obvious, Minimal Language*) format, which is Cargo’s configuration format.

-above format gives a sections like heading to the package

for eg. 

[package] :: start of a package :: gives the configuration of the package.

[dependencies] :: section to list the used libraries in the project.

-packages of code are referred to as *crates*.

- top-level project directory is just for README files, license information, configuration files, and anything else not related to your code.

-Cargo placed the code in the *src* directory

-`cargo init` :: to create toml file automatically

-cargo build creates a directory *target/debug/hello_cargo* cargo puts the binary into the debug directory, running it first time also creates a cargo.lock file in the base directory this keeps the exact version of all the dependencies used.

-use `cargo run` to compile the code and it also executes the file also.

-Using `cargo run` is more convenient than having to remember to run `cargo build` and then use the whole path to the binary, so most developers use `cargo run`.

-the above command also checks if the code is modified or not after that only it compiles otherwise it just executes the binary

-`cargo check` :: it just compiles doesn’t show the output

-tldr:: to check for errors middle of development and not compiling :: using `cargo check` will speed up the process of letting you know if your project is still compiling! As such, many Rustaceans run `cargo check` periodically as they write their program to make sure it compiles. Then they run `cargo build` when they’re ready to use the executable.

- `cargo build -—release` :: this command will create an executable in *target/release* instead of *target/debug*. its one for development and one for final product for benchmarking.

### Chapter 2
