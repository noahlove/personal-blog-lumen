---
title: Using mamba and conda in python
date: "2023-02-18T22:40:32.169Z"
template: "post"
draft: false
slug: "/posts/using-mamba-and-conda-in-python"
category: "Python"
tags:
  - "Python"
  - "Mamba"
  - "Conda"
description: "A list of commands for Mamba and python environments"
socialImage: "../../photo.jpg"
---


## Overview 

A Conda environment in Python is a virtual environment that allows you to create a separate space with its own Python installation, dependencies, and packages. This means you can have multiple isolated environments on the same machine with different versions of Python and different packages installed, without interfering with each other.

Conda is a package management system and environment management system that simplifies the installation and management of software packages and their dependencies. It was developed to manage packages in data science, machine learning, and scientific computing applications, where it's common to have complex dependencies between different software libraries.

Creating a Conda environment involves creating a new directory and installing a specific version of Python and packages into it. Once you activate a Conda environment, any package installations or updates are made in that specific environment, and will not affect other environments on the same machine. You can also easily export the environment specification to a YAML file, which can be used to recreate the same environment on another machine.

Overall, Conda environments provide a powerful way to manage dependencies and package installations in Python, especially for data science, machine learning, and scientific computing applications.

### Mamba vs Conda (And why to use Mamba)

Mamba is a community-driven, high-performance replacement for the Conda package manager, developed as an alternative to Conda. Mamba is designed to be faster and more memory-efficient than Conda, and it provides some additional features, such as parallel package downloads and dependency solving.

The main difference between Mamba and Conda is their performance. Mamba is generally faster than Conda, especially when it comes to large dependency graphs. This means that Mamba can install and update packages more quickly, making it a good choice for large projects with many dependencies.

Another difference between Mamba and Conda is that Mamba uses a different solver algorithm that can sometimes produce different results than Conda. This can be both an advantage and a disadvantage, depending on the use case. On one hand, Mamba's solver can sometimes find better solutions for complex dependency graphs. On the other hand, the results may not always be compatible with Conda, which can be a problem if you're working in a team or collaborating with others who use Conda.

## Tips

- Create a new environment for each project: It's a good practice to create a new environment for each project, which helps you keep your dependencies and packages organized and avoids any conflicts between different projects.
- Use YAML files to manage environments: You can use YAML files to create and manage your environments. This allows you to easily reproduce the environment on a different machine or share it with others.
- Keep your base environment clean: The base environment is the default environment that comes with Conda. It's a good idea to keep this environment clean and only install essential packages. You can create new environments for specific projects and install packages there.
- Use the Conda environment activation scripts: Once you create a new environment, you can activate it by running the appropriate activation script. Using these scripts ensures that your environment is properly configured and any necessary environment variables are set.
- Use the Conda command-line interface: Conda provides a powerful command-line interface that allows you to manage environments, packages, and dependencies. Learning how to use the Conda command-line interface can save you time and effort in managing your environments.
- Update your environments regularly: Conda provides a straightforward way to update your environments and packages. Keeping your environments up to date ensures that you have the latest features and bug fixes.
- Use virtual environments within Conda environments: Conda can be used to manage virtual environments, which allow you to further isolate packages and dependencies within an environment. This can be useful when you need to use multiple versions of the same package within the same environment.


## Commands


Updating Mamba
```
mamba update -n base mamba
```

Finding a Package

```
mamba repoquery search PACKAGE
```

Searching for dependencies

```
mamba repoquery depends -a PACKAGE
```

Creating an environment
```
mamba create -n ENV_NAME PACKAGE
```

Adding/Updating software
```
mamba install -n ENV_NAME PACKAGE
mamba update -n ENV_NAME --all
```

Removing a package
```
mamba remove -n ENV_NAME PACKAGE
```

Undoing changes to an environment
```
mamba list -n ENV_NAME --revisions
mamba install -n ENV_NAME --revision 1
```

Show environment
```
conda env export --no-builds
```

Clone an existing environment

```
conda create --name CLONE_ENV_NAME --clone ENV_NAME
```

Removing an environment
```
mamba env remove -n ENV_NAME
conda remove --name ENV_NAME --all
```

Exporting an environment
```
mamba env export -n ENV_NAME > ENV_NAME.yaml
conda list -e > ENV_NAME.txt
conda env export -n ENV_NAME --no-builds | grep -v "prefix" > ENV_NAME.yaml
```

Importing an environment
```
mamba env create --file ENV_NAME.yaml
conda env create --file ENV_NAME.yaml
conda create -n ENV_NAME --file ENV_NAME.txt
```

Deactivate the Environment
```
conda deactivate
```

Viewing a list of your environments
```
conda info --envs
conda env list
```
