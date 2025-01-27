# Creating Your First Rust Project!

* Primary author: [Maddie Clark](https://github.com/mbclark37)

* Reviewer: [Lucy Good](https://github.com/lucykgood)

## Setting Up Your Development Environment
To set up a Dev Container for Rust, you must either have Docker downloaded or have an understanding of GitHub Codespaces.

??? note "What is Docker?"
    Docker is an efficient way for developers to build, share, and run containerized applications on their local machines.

??? note "What are GitHub Codespaces?"
    A GitHub Codespace is an environment where one can develop their programs and have them remain in the cloud.
### Step 1: Start a Blank Directory and Initialize Git
1. Open your terminal.
2. Navigate to where you want this project to reside on your machine.
3. Create a new directory and navigate to it:
    ``` bash title="directory-setup.bash"    
            mkdir rust-dev-container
            cd rust-dev-container  
    ```
4. Initialize a Git repository:
    ``` bash title="git-init.bash"
            git init
    ```

### Step 2: Configure the Dev Container
1. Download VSCode (if not already installed on device) and open the created directory via the file tab on your menu bar.
2. Add a Dev Container configuration file to your directory named .devcontainer.json and input the following code:

    ```json title="dev-setup.json"
        {
            "name": "Rust Development Environment",
            "image": "mcr.microsoft.com/devcontainers/rust:latest",
            "customizations": {
                "vscode": {
                    "extensions": [
                        "rust-lang.rust-analyzer"
                     ]
                }
            }
        }
    ```
    ??? note "Dev Setup Explanations"
        *  name: Pick something (human readable) to identitfy your development environment. Make sure it's unique from any other environments you have.
        * image: `mcr.microsoft.com/devcontainers/rust:latest` is an official Microsoft Rust development container image. You can explore Microsoft's collection [here](https://hub.docker.com/r/microsoft/vscode-devcontainers).
        * customizations.vscode.extensions: A list of VSCode extensions that can help with development.


### Step 3: Start the Dev Container
1. Open the Command Palette (`Ctrl + Shift + P` on Windows or `Cmd + Shift + P` on Mac), and search `Dev Containers: Reopen In Container` to reopen the folder in the Dev Container Environment.
    * VSCode will rebuild the container and open your new workspace inside.

### Step 4: Verify Proper Installation
1. Open a new terminal within the Dev Container (`Ctrl + \`).
2. Ensure a recent version of Rust is being used: 
    ```bash title="bash"
        rustc --version
    ```
    Example output:
    ```scss title="scss"
        rustc 1.73.0 (or later)
    ```
    This verifies a recent version.

ntainer, navigate to [Creating a New Rust Project](http://127.0.0.1:8000/tutorials/new-rust-project/).

Now it's time to learn how to create a new project, write a basic "Hello COMP423" program, compile, and run it!

## Creating a New Rust Project
1. Navigate to your previously configured directory in VSCode and open a terminal (`Ctrl + \`).
2. Use Cargo to create a new Rust project:
    ``` rust title="project-setup.rust"
        cargo new hello_comp423 --vcs none
        cd hello_comp423
    ```

    !!! note
        `--vcs none` prevents Cargo from creating a new Git repository, since one has already been initialized.

   

### Step 1: Write the "Hello COMP423" Program
1. Open `src/main.rs` in the `hello_comp423` folder.
2. Replace the contents with the following code: 
    ```rust title="hello-comp423.rust"
        fn main(){
            println!("Hello COMP423");
        }
    ```

### Step 2: Build and Run the Program
Before attempting to compile and run the project, it is important to ensure you are in the correct directory, or else the build will be unsuccessful. Run the following code in your terminal.

```bash
    cd /workspaces/rust-dev-container/hello_comp423
```

#### Using `cargo build`
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
#### Using `cargo run`
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

## Success!
Make a commit with your new changes using Git by writing these lines of code in your terminal in VSCode.

``` git
    cd rust-dev-container
    git add .
    git commit -m "Insert descriptive message for your changes here."
```

Congratulations! You have just written your first Rust project!
