# Setting up a dev container for Rust
* Primary author: [Jeffrey Zhu](https://github.com/JeffJeffisawesome)
* Reviewer: [Justin Su](https://github.com/jsu21ges)

## Intro

Welcome to the Rust tutorial! Rust is a Low-level programming language, with built-in memory-safety, removing many of the headaches you would receive in ```C/C++```
This tutorial aims to help you set up a docker environment to run your Rust code in, and run your first piece of code in Rust! A more extensive tutorial can be found [here](https://doc.rust-lang.org/book/), and documentation can be read [here](https://doc.rust-lang.org/std/index.html).

## Prerequisites

You must have docker installed and running before the dev container can be created.

## Creating a git repository

1. Create a new directory for your project. Name it ```Rust-Project```. In terminal, this will look like:
```
mkdir Rust-Project
cd Rust-Project
```

2. Type in terminal:  
```git init```  
This will initialize a git repository in the directory.

3. Log into your GitHub account and navigate to the [Create a New Repository](https://github.com/new) page  
Fill in the details as follows:
```
Repository name: Rust-Project  
Visibility: Public
```
4. Ignore everything else, and click **Create Repository.** 

5. Link your local repository to GitHub. You can do this in terminal with:
```
git remote add origin https://github.com/<your-username>/Rust-Project.git
```
Replace `<your-username>` with your GitHub username

6. Check your default branch name with the subcommand `git branch`. If it's not `main`, rename it to `main` with the following command: `git branch -M main`. Old versions of git choose the name `master` for the primary branch, but these days `main` is the standard primary branch name.

7. Add, Commit, and Push your local commits to the GitHub repository:
```
git add .
git commit -m "first commit"
git push --set-upstream origin main
```

## Creating a dev container project

2. In VSCode, open the ```Rust-Project``` directory. You can do this via: File > Open Folder
3. Install the Dev Containers extension for VS Code.
4. Create a ```.devcontainer``` directory in the root of your project with the following file inside of this "hidden" configuration directory:
```
.devcontainer/devcontainer.json
```
This json file will ensure that all of the correct dependencies are downloaded when running your code. Additionally, if someone else wishes to run this code, you won't have to worry if they have the right version of Rust downloaded.
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
cargo new --vcs none hello_world
```
Navigate into `hello_world/src` to find a main.rs file that should contain the following code:
```
fn main() {
    println!("Hello, world!");
}
```

2. In terminal, type:
```
cargo build
cargo run
```
What does `cargo build` do? Think of `build` as similar to `gcc` for `C` code: they both turn human readable code into machine executable files to be run by the computer.

You should see:
```
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 0.04s
     Running `/workspaces/Desktop/code/Rust-Project/hello_world/target/debug/hello_world main`
Hello, world!
```

!!! note "Phasellus posuere in sem ut cursus"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.