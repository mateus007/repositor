Repositor
=========

Proposed git and development workflow for projects with multiple git repositories

**Why?**

We develop a lot of projects and with this, became such a pained task manage dependencies.

Repositor try to achieve a best workflow for development using multiple repositories with no other libraries dependence like `bower` or `composer`. It is inspired by `modman`, with your workflow and `Makefile`. It's for all development cases with complete flexibility.

**Workflow**

- Start a new project
- Init git on that project - `git init`
- Do initial project setup
- Create a new root folder called `repositories`
- Go to folder `repositories`
- Add `.gitignore` file on folder to git do not track the files inside that folder
- Clone the repositories that will be used on the new project
- Add symbolic links for cloned files and folders in your project structure (the folder `repositories` is intended to stay away from your main project)
- Create the `Makefile` with tasks to update, check and link the cloned repositories
- Develop!

**Conventions**

- All cloned repositories always are remote
- Avoid changes on files from cloned repositories. If necessary, change the cloned repository and update the repository on the project
- Create symbolic links only for needed files. This is the main intent of the repositor workflow.

**Usage:**

    $ mkdir project
    $ cd project
    $ git init
    $ # here you will usually do the project setup

    $ mkdir repositories
    $ cd repositories
    $ touch .gitignore

    $ # Start cloning
    $ git clone https://github.com/mateus007/linha-framework.git
    $ git clone https://github.com/mateus007/angularjs-starter

    $ # Now create tasks for auto pull the repositories
    $ # Create symbolic links with ln -sf
    $ vim Makefile

That's all! Questions?