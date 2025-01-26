# Setting up a dev container for Rust

* Primary author: [Maddie Clark](https://github.com/mbclark37)

* Reviewer: [Lucy Good](https://github.com/lucykgood)

To set up a Dev Container for Rust, you must either have Docker downloaded or have an understanding of GitHub Codespaces.

* What is Docker?
Docker is an efficient way for developers to build, share, and run containerized applications on their local machines.

* What are GitHub Codespaces?
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

    *  name: Pick something (human readable) to identitfy your development environment. Make sure it's unique and differentiable from any other environments you have.
  * image: Either provide a path to a Docker file or use one from a set of prebuilt container images. Microsoft has a collection [here](https://hub.docker.com/r/microsoft/vscode-devcontainers).
  * customizations.vscode.extension: A list of VSCode extensions tht can help with development.

4. Install official ```rust-analyzer``` VSCode plugin by the Rust Programming Language Group.
5. Show ```rustc --version``` in order to ensure you are using a more recent version of rust.

## Start the Dev Container
1. 
2. Open the Command Palette (`Ctrl + Shift + P` or `Cmd + Shift + P`) and search `Dev Containters: Reopen In Container`.

