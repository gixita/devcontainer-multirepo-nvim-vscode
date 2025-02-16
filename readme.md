# External devcontainer configuration for python
## Purpose
When your repo contains a generic devcontainer and you want to use NeoVim without impacting the other contributors.

My use case:
- SSH in a cloud VM (running Ubuntu without privileges, no sudo)
- Build multiple services through the custom docker-compose.yml
- Enter each containers and run nvim, run my service inside the container

## How to use it
- Clone this repository
- Inside the folder "devcontainer-multirepo-nvim-vscode", clone your project.
- Ensure that your project contains all the necessary development tools
```sh
poetry add pytest debuggerpy mypy ruff -G dev
```
- Modify the `.devcontainer/project1-neovim/devcontainer.json` to your liking.

## NeoVim configuration
By adding your configuration inside the nvim folder, the container will be loaded with it.
If you have an already working neovim configuration for python, just modify the `.devcontainer/docker-compose.yml` to mount your nvim config folder, which should be `~/.config/nvim`.

If you want to start fast, you can just clone my config inside the `devcontainer-multirepo-nvim-vscode` folder:
```sh
git clone https://github.com/gixita/neovim_config.git ./nvim/.
```
## Run your devcontainer

[Install first devcontainer cli if not yet done.](https://github.com/devcontainers/cli)

Build and run the container

```sh
devcontainer up --workspace-folder ./project1 --config .devcontainer/project1-neovim/devcontainer.json
```

Enter the container
```sh
devcontainer exec --workspace-folder ./project1 --config .devcontainer/project1-neovim/devcontainer.json bash
```
Change project1 with your project folder.
```
```
Finally start working with 

```sh
poetry shell
nvim
```
