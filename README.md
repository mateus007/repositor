Repositor Dependency Manager
=========

Repositor is a tool to manage dependencies from multiple git repositories on your projects.

## Why?

We develop a lot of small projects and with this, became a pain manage dependencies on large projects that use some small projects.

Repositor try to achieve a best workflow for development using multiple repositories with no other libraries dependence like `bower` or `composer`. It is inspired by `modman` and `modgit`. It's for all development cases, in all programming languages with complete flexibility.

With Repositor, you can configure which repositories your project depends and more specifically, what files and folders from this repository should be used in your project - and whatever the location where they should be. Repositor will keep a copy of the repositories in your project (outside the main git) and distribute only the necessary files in your project so that it can be updated more easily.

The most notable difference between `repositor` and other package managers is that with the `repositor`, you make your way around. It is you who defines which files and folders will be used in your project and where they should be inserted. Repositor fits your design, not the opposite.

## Installation

**curl installation**

    $ curl https://raw.githubusercontent.com/mateus007/repositor/master/repositor > repositor
    $ chmod +x repositor
    $ sudo mv repositor /usr/local/bin

**wget installation**

    $ wget -O repositor https://raw.githubusercontent.com/mateus007/repositor/master/repositor
    $ chmod +x repositor
    $ sudo mv repositor /usr/local/bin

**Manual download**

* Download shell script [here](https://raw.githubusercontent.com/mateus007/repositor/master/repositor)
* Copy `repositor` file to `/usr/local/bin` (or any folder in your $PATH)
* Run `chmod +x repositor`

## Workflow

- Start a new project
- Init git on that project - `git init`
- Do initial project setup
- Init repositor on that project - `repositor init`
- Update the `repositor.conf` file with configurations for repositories - see `example.conf`
- Run `repositor [repository] clone` to create copy of repository and deploy files
- Develop!

## Conventions

- All cloned repositories always are remote
- Avoid changes on files from cloned repositories. If necessary, change the cloned repository and after, update the repository on the project
- Use only needed files from others repositories. This is the main intent of the repositor workflow.

## Usage

**New project**

    $ mkdir project
    $ cd project
    $ git init
    $ # here you will usually do the project setup

    $ repositor init
    $ vim repositor.conf
    $ # configure the project dependencies on repositor.conf file

    $ repositor [repository] clone
    $ # repositor [repository-two] clone
    $ # ...

**Updating a repository**

    $ repositor [repository] update

**Do some mess on repository code? Re-deploy**

    $ repositor [repository] deploy

**More commands and help**

    $ repositor --help

That's all! Questions?