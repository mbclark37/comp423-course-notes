# Setting Up a Dev Container for Rust

* Primary author: [Maddie Clark](https://github.com/mbclark37)

* Reviewer: [Lucy Good](https://github.com/lucykgood)

To set up a Dev Container for Rust, you must either have Docker downloaded or have an understanding of GitHub Codespaces.

??? note "What is Docker?"
    Docker is an efficient way for developers to build, share, and run containerized applications on their local machines.

??? note "What are GitHub Codespaces?"
    A GitHub Codespace is an environment where one can develop their programs and have them remain in the cloud.
## Step 1: Start a Blank Directory and Initialize Git
1. Open your terminal.
2. Navigate to where you want this project to reside on your machine.
3. Create a new directory and navigate to it:
    ``` bash title="direcory-setup.bash"    
            mkdir rust-dev-container
            cd rust-dev-container  
    ```
4. Initialize a Git repository:
    ``` bash title="git-init.bash"
            git init
    ```

## Step 2: Configure the Dev Container
1. Download VSCode (if not already installed on device) and open the created directory via the file tab.
3. Add a Dev Container configuration file to your directory named .devcontainer.json and input the following code:

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
        *  name: Pick something (human readable) to identitfy your development environment. Make sure it's unique and differentiable from any other environments you have.
        * image: `mcr.microsoft.com/devcontainers/rust:latest` is an official Microsoft Rust development container image. You can explore Microsoft's collection [here](https://hub.docker.com/r/microsoft/vscode-devcontainers).
        * customizations.vscode.extension: A list of VSCode extensions tht can help with development.


## Step 3: Start the Dev Container
1. Open the Command Palette (`Ctrl + Shift + P` or `Cmd + Shift + P`) and search `Dev Containters: Reopen In Container` to reopen the folder in the Dev Container Environment.
    * VSCode will rebuild the container and open the workspace inside.

## Verify Proper Installation
1. Open the terminal within the Dev Containter (`Ctrl + \`).
2. Ensure a recent version of Rust is being used: 
    ```bash title="bash"
        rustc --version
    ```
    Example output:
    ```scss title="scss"
        rustc 1.73.0 (or later)
    ```
    This verifies a recent version.

## Onto the Next Step!
Now that you've properly initialized a repository and set up your very own development container, navigate to [Creating a New Rust Project](http://127.0.0.1:8000/tutorials/new-rust-project/).



