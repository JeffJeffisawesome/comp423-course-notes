# Setting up a dev container for Rust
* Primary author: [Jeffrey Zhu](https://github.com/JeffJeffisawesome)
* Reviewer: [Justin Su](https://github.com/jsu21ges)
## Prerequisites
Make sure that 
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
  "name": "Rust Hello World",
  "image": "mcr.microsoft.com/devcontainers/rust:latest",
  "customizations": {
    "vscode": {
      "settings": {},
      "extensions": [rust-analyzer.rust]
    }
  },
  "postCreateCommand": "pip install -r requirements.txt"
}
```


Code Block:
```
testing
    testing
```

!!! note "Phasellus posuere in sem ut cursus"

    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.