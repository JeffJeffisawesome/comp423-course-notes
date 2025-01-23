# Setting up a dev container for Rust
* Primary author: [Jeffrey Zhu](https://github.com/JeffJeffisawesome)
* Reviewer: [Justin Su](https://github.com/jsu21ges)
## Prerequisites
You must have docker installed and running before the dev container can be created
## Creating a dev container project
1. Create a new directory for your project. Name it ```Rust-Project```. In terminal, this will look like:
```
mkdir Rust-Project
```
2. In VSCode, open the ```Rust-Project``` directory. You can do this via: File > Open Folder
3. Install the Dev Containers extension for VS Code.
4. Create a ```.devcontainer``` directory in the root of your project with the following file inside of this "hidden" configuration directory:
```
.devcontainer/devcontainer.json
```
5. Within this json file, paste in the following:
```
{
  "name": "First Rust Project",
  "image": "mcr.microsoft.com/devcontainers/rust:latest",
  "customizations": {
    "vscode": {
      "settings": {},
      "extensions": ["rust-lang.rust-analyzer"]
    }
  }
}
```
6. Reopen the project in a VSCode Dev Container. Make sure that you currently have docker open. Press ```Ctrl+Shift+P``` (or ```Cmd+Shift+P``` on Mac) to search, then search "Dev Containers: Reopen in Container," and select the option. You may have to wait a few minutes while the image downloads.

7. Check that everything is good: Once the dev container has opened, make sure that you have a recent version of rust on your system by opening a terminal pane, and typing in
```
rustc --version
```
As of the creation of this tutorial (1/23/2025), the latest stable version of rust is ```1.83.0```

## Making your first Rust Program!
1. Create a new directory to make your first Rust project (Ex: ```hello_world```), and then create your first rust file named ```main.rs```. You can do this by typing in the terminal:
```
mkdir hello_world
touch main.rs
```
2. Edit the main.rs file:
```
fn main() {
    println!("Hello, world!");
}
```
3. In terminal, type:
```
rust main.rs
./main.exe
```
You should see:
```
Hello, world!
```

!!! note "Phasellus posuere in sem ut cursus"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.