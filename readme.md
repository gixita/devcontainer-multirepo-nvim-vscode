# External devcontainer configuration for python
## Purpose
When your repo contains a generic devcontainer and you want to use NeoVim within the container and without impacting the other contributors.

## How to use it
- Clone this repository
- Inside the folder "devcontainer-multirepo-nvim-vscode", clone your project.
- Ensure that your project contains all the necessary development tools
```sh
poetry add pytest debuggerpy mypy ruff -G dev
```
- Modify the `.devcontainer/project1-neovim/devcontainer.json` to your liking.

