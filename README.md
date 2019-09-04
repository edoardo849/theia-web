# Theia IDE

This project is a runnable version of the Theia IDE with the VS Code extension capability enabled.

## Requirements

- [node](https://nodejs.org/en/)
- [yarn](https://yarnpkg.com/lang/en/)

## Installation

```sh

git clone 

# This folder is where you can put VS Code's .vsix extensions
mkdir ./theia-plugins

cd ./theia-ide

# Install the dependencies
yarn

# Clean
yarn run theia clean

# Set up the maximum amount of memory that Node can use to that we don't run into heap troubles
export NODE_OPTIONS=--max-old-space-size=8192

# Build the IDE
yarn run theia build

# Run the IDE on port 8444
yarn run theia start --plugins=local-dir:../theia-plugins --hostname 0.0.0.0 --port 8444

# Or as a single command
yarn && \
yarn run theia clean && \
export NODE_OPTIONS=--max-old-space-size=8192 && \
yarn run theia build && \
yarn run theia start --plugins=local-dir:../theia-plugins --hostname 0.0.0.0 --port 8444

```

Now you can open your browser and navigate to <your-domain>:8444 or <your-ip>:8444 and start using Theia.

## Install a VsCode extenstion

Installing a VS Code extension is pretty easy: just visit the VS Code marketplace, donwload the `.vsix` file and put it into the `theia-plugins` folder. During the startup of the IDE, the script will automatically unpack and install the extension. Easy Peasy.

# Further Development

- Run Theia behind a Login Page using nginx as a reverse proxy
- Run Theia with https using letsencrypt
- Build a Docker container to run all of the above