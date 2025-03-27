
## Features

The following features have been implemented:

- Manage tasks through a Kanban board interface (set due dates, labels, add checklists)
- View all your current assigned tasks through the My Tasks view
- Personal projects
- Task comments and activity

This project is still in active development, so some options may not be fully implemented yet.

**For updates on development, join the [Discord server](https://discord.gg/JkQDruh).**

For a list of planned features, check out the [Roadmap](https://github.com/JordanKnott/Project-Manager/wiki/Roadmap)!

## Installation

### With docker & docker-compose

You'll need both [docker](https://www.docker.com/) & [docker-compose](https://docs.docker.com/compose/install/) installed.

First clone the repository:

``` bash
git clone https://github.com/JordanKnott/Project-Manager && cd Project-Manager
```

Now do the following:

``` bash
docker-compose -p Project-Manager up -d
```

This will start a postgres instance as well as a Project-Manager instance.

The second command runs the database schema migrations.

If you visit [http://localhost:3333](http://localhost:3333), you will get redirected to the installation
screen so that you can create the first system user.

### From Source

You'll need [Golang](https://golang.org/dl/) installed on your machine.

Next, clone the repository:

``` bash
git clone https://github.com/JordanKnott/Project-Manager && cd Project-Manager
```

Next we need to build the binary. This project uses [Mage](https://magefile.org/) for its build tool.

``` bash
go run cmd/mage/main.go install
go run cmd/mage/main.go build
```

This will:

- Install all yarn packages for the frontend
- Build the React frontend
- Embed the React frontend in the binary
- Compile the final exectuable binary

The newly created `Project-Manager` binary can be found in the __dist__ folder.

It contains everything neccessary to run except the config file. An example config file can be found in `conf/app.example.toml`.



## How is this different from X (Trello, NextCloud, etc)?

One of the primary goals of Project-Manager is to provide a project management tool that I personally enjoy using for my
own projects and fits my workflow.

During alpha development, the current plan is to build the "basic" features - features that are pretty much
standard across all kanban boards / project management tools.



There is also a [Code of Conduct](https://github.com/JordanKnott/Project-Manager/blob/master/CODE_OF_CONDUCT.md) as well.

## License

[MIT License](LICENSE)
