# Creating a New Rust Project

In this tutorial, you will learn how to create a new project, write a basic "Hello COMP423" program, compile, and run it!

## Creating a New Project
1. Navigate to your previously configured directory in VSCode (instructions on [Setting Up a Dev Containter for Rust](http://127.0.0.1:8000/tutorials/rust-setup/)) and open a terminal (`Ctrl + \`).
2. Use Cargo to create a new Rust project:
    ``` rust title="project-setup.rust"
        cargo new hello_comp423 --vcs none
        cd hello_comp423
    ```

    !!! note
        `--vcs none` prevents Cargo from creating a new Git repository, since one has already been initialized.

   

## Write the "Hello COMP423" Program
1. Open `src/main.rs` in the `hello_comp423` folder.
2. Replace the contents with the following code: 
    ```rust title="hello-comp423.rust"
        fn main(){
            println!("Hello COMP423");
        }
    ```

## Build and Run the Program
### Using `cargo build`
1. Compile the program: 
    ```
        cargo build
    ```

    !!!note 
        `cargo build` compiles the code and generates an excutable in the `target/debug` directory (similar to `gcc` creating an executable object file -- like we learned in COMP 211).
    Output:
    ``` scss
        Compiling hello_comp423 v0.1.0 (/workspace/hello_comp423)
        Finished dev [unoptimized + debuginfo] target(s) in 0.79s
    ```

2. Run the compiled executable manually:
    ``` bash title="cargo-build.bash"
        ./target/debug/hello_comp423
    ```
    Output:
    ``` 
        Hello COMP423
    ```
### Using `cargo run`
1. Use the `cargo run` command to compile and run the program in one step:

    ```
        cargo run
    ```

    Output:

    ``` scss 
        Compiling hello_comp423 v0.1.0 (/workspace/hello_comp423)
        Finished dev [unoptimized + debuginfo] targets(s) in 0.72s
        Running 'target/debug/hello_comp423'
        Hello COMP423
    ```
    !!! note
        `cargo build` only compiles the program, leaving the compiled file for later execution. `cargo run` does both, combining both the compilation and the execution of a file into a single command.


