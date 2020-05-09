# Web Development Environment

A development environment using Docker, for websites requiring Node.js and
Apache web server.

Update this README file accordingly for your projects.

## Stack

- Apache 2
- Node.js 12.x (LTS)

## Prerequisites

Please install the following on the host machine:

- Docker (should include docker-compose)

## Setup

Execute terminal commands on your preferred terminal/console.

1. Go to the root of the environment template directory.
2. Copy the website files into the `public\` directory.
    - This directory is served by the Apache web server.
3. Copy/save the project source files under the `src/` directory.
4. Run `docker-compose up` to start the environment.
    - This runs the container in foreground. To stop, press CTRL-C.
    - If you want to run in background, run `docker-compose up -d`.
5. Access http://localhost:8080 on any browser. 
6. To stop the server running in background (`-d`), run `docker-compose stop`.

## Building from source

For projects utilizing build tools powered by Node.js, you need to to this step
every time you need to execute them.

1. Make sure you've run the setup procedures.
2. Run `docker-compose run nodejs bash` on a terminal on the host machine.
3. Inside the container, execute your node build tools (webpack, gulp, etc)
   command.
4. Run `exit` to leave the container.

## Output directory

The Apache container serves the files in the `public/` directory.

Configure your build tool to use this directory or symlink the build/output
directory if it's generated inside the `src/` directory.

Depending on your project, you may need to configure what files to gitignore in
the `public/` directory.

## Cleaning up

If the development is done, don't forget free up resources and disk space by
running `docker-compose down`.
