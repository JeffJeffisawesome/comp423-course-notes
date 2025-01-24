# Setting up a dev container for Rust
* Primary author: [Jeffrey Zhu](https://github.com/JeffJeffisawesome)
* Reviewer: [Justin Su](https://github.com/jsu21ges)

## Intro

<<<<<<< HEAD
Welcome to the Rust tutorial! Rust is a Low-level programming language, with built-in memory-safety, removing many of the headaches you would receive in ```C/C++.```  
=======
Welcome to the Rust tutorial! Rust is a Low-level programming language, with built-in memory-safety, removing many of the headaches you would receive in ```C/C++```
>>>>>>> 9f318ec7395d4097c2e3ff5ee684cac66c69d1e6
This tutorial aims to help you set up a docker container to run your Rust code in, and run your first piece of code in Rust! A more extensive tutorial can be found [here](https://doc.rust-lang.org/book/), and documentation can be read [here](https://doc.rust-lang.org/std/index.html).

## Prerequisites

<<<<<<< HEAD
You must have docker installed and running before the dev container can be created. Additionally, this tutorial will require you have git and VSCode installed, as well as having the Dev Containers extension on VSCode.
=======
You must have docker installed and running before the dev container can be created. Additionally, this tutorial will require you have git and vscode preinstalled, as well as having the Dev Containers extension on VSCode.
>>>>>>> 9f318ec7395d4097c2e3ff5ee684cac66c69d1e6

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

7. Create a README file (You can add whatever you want into it) in you repository, and then, Add, Commit, and Push your local commits to the GitHub repository:
```
echo "# My First Rust Project" > README.md
git add README.md
git commit -m "first commit"
git push --set-upstream origin main
```

## Creating a dev container project

1. In VSCode, open the ```Rust-Project``` directory. You can do this via: File > Open Folder
2. If you don't have it already, install the Dev Containers extension for VS Code.
3. Create a ```.devcontainer``` directory in the root of your project with the following file inside of this "hidden" configuration directory:
```
.devcontainer/devcontainer.json
```
<<<<<<< HEAD
This json file will ensure that all of the correct dependencies are downloaded when running your code. Additionally, if someone else wishes to run this code, you won't have to worry if they have the right version of Rust downloaded, so long as they too have this devcontainer.json file in their .devcontainer directory.
=======
This json file will ensure that all of the correct dependencies are downloaded when running your code. Additionally, if someone else wishes to run this code, you won't have to worry if they have the right version of Rust downloaded.
>>>>>>> 9f318ec7395d4097c2e3ff5ee684cac66c69d1e6
4. Within this json file, paste in the following:
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
  The `image` specification will ensure that your dev container is using the latest version of rust. The `extensions` specification ensures that you have the `rust-analyzer` plugin from VSCode installed.

## Opening the container:

!!! note 
    Make sure you have Docker running!

    The next step will not work if you do not have Docker running!

1. Reopen the project in a VSCode Dev Container (You should already have the extension installed!).  Press ```Ctrl+Shift+P``` (or ```Cmd+Shift+P``` on Mac) to search, then search "Dev Containers: Reopen in Container," and select the option. You may have to wait a few minutes while the image downloads.

2. Check that everything is good: Once the dev container has opened, make sure that you have a recent version of rust on your system by opening a terminal pane, and typing in
```
rustc --version
```
As of the creation of this tutorial (1/23/2025), the latest stable version of rust is ```1.83.0```

## Making your first Rust Program!

1. Create a new directory (within your container) to make your first Rust project (Ex: ```hello_world```), and then create your first rust file named ```main.rs```. You can do this by typing in the terminal:
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