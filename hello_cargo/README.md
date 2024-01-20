# Building and Running a Cargo Project

From the hello_cargo directory, build the project by entering the following command:

```
$ cargo build
```

This command creates an executable file in *target/debug/hello_cargo* rather than your current directory. You can run the executable with this command:

```
$ ./target/debug/hello_cargo
```

Although the project was built with ```cargo build``` and ran it with ```./target/debug.hello_cargo```, but it can also be run with ```cargo run``` to compile and run the resultant executable all in one command

Using ```cargo run``` is more convinient than having to remember to run ```cargo build``` and the corresponding path to the binary.

Cargo can also provide a command to quickly check your code to make sure it compiles but doesn't produce an executable:

```
$ cargo check
```

Why do this?
It is much faster than ```cargo build``` because it skips the step of producing an executable. Run ```cargo check``` periodically as you  write your program to make sure it compiles. Then run ```cargo build``` when ready to use the executable.

## Recap:
* Create a project using ```cargo new *insert folder name*``` 
* Build a project using ```cargo build```
* Build and run a project in one step using ```cargo run```
* Build a project without producing binary to check for errors using ```cargo check```
* Build result is stored in the *target/debug*

# Building for Release

When a project is ready for release, you can use ```cargo build --release``` to compile it with optimizations. This command creates and executable in *target/release* instead of *target/debug*.

If you're benchmarking code's runtime, run ```cargo build --release``` and benchmark with the executable in *target/release*

