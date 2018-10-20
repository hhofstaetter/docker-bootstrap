# docker-bootstrap

Bootstrap scripts for node/npm frontends with php/mysql backends.

# Configuration

Configuration of the bootstrapper is done with environment variables. The shell wrapper read them from a `.env` file in the same directory.

## Variables

### NODE_VERSION
The node version you want to use. Can be any supported tag from the official node docker image (https://hub.docker.com/_/node/).

### NODE_DIRECTORY
The relative path to the directory your node project will be in. This can be a directory inside the bootstrapper (`NODE_DIRECTORY=example-project`) or a directory outside (`NODE_DIRECTORY=../example-project`).

### NODE_COMMAND
The command that should be run inside the docker container. Most common the npm command to start the dev server.

### NODE_PORT
The port the node application is running an. Will be exposed as port 8080 on localhost of the host

# Create a new node project

* Configure `NODE_VERSION` and `NODE_DIRECTORY` in the `.env` file
* Create the directory for the node project
* Call `./node-bash` to get a shell inside the node docker container
* Use `npm` to install your node application
    * VueJS: `npm install -g @vue/cli` and `vue create .`
    * Nuxt: `npx create-nuxt-app .`
* Add the npm command to start the dev server as `NODE_COMMAND` to the `.env` file  
    * VueJS: `NODE_COMMAND=npm run serve`
    * Nuxt: `NODE_COMMAND=npm run dev`
* Add the port that should be exposed as `NODE_PORT` to the `.env` file
    * VueJS: `NODE_PORT=8080`
    * Nuxt: `NODE_PORT=3000`
* `docker-compose up -d`
    * The output is available on port 8080 of localhost: http://localhost:8080/
