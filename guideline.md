---
title: "PHO Data Management Guidelines"
author: "Callum Arnold"
date: today
output:
  html_document:
    toc: yes
    toc_float:
      collapsed: yes
      smooth_scroll: yes
---

PHO Data Management Guidelines
------------------------------

# Reproducible Work

## What is reproducible work?

- Contains relevant code, including which packages were used
- Contains enough text, either via `markdown` or comment to be able to understand what the purpose of each code is
    - Ideally integrates code and results, along with text, into a single document

## Why is it important?

Simply put, all code and work has mistakes and bugs. If you are able to


# Structuring a project

- VCS
- Data isn’t touched one collected:
- Do all data munging within your program i.e. no editing the excel spreadsheets!!!
- Never set explicit file paths if you can avoid it i.e. `setwd()`
    - try and use a package that allows you to set relative paths e.g. `here_here` in `R`. This allows the project to be passed to someone else in its entirity and the code won't break because they don't have the same folder names and set up as you (also the case if you work on multiple computers/OS)

# Git

Think of it as tracked changes for your code. When working on a project by yourself, it’s important to be able to go back to previous versions if you make a mistake and can’t remember all the steps you went through since your last stable version.

## Branching

# Notebooks

- Many examples of different kinds of notebooks
- Jupyter useful as you can see the results immediately integrated within the document
    - Has a system to allow other statistical and programming languages to run via kernels
        - Other systems don’t allow this level of integration, so will not be explored in much detail

## Jupyter notebooks

This section will give you a brief overview of what a Jupyter notebook is and how to use them, but if you would like a more detailed understanding, please read the official [documentation](https://jupyter-notebook.readthedocs.io/en/stable/notebook.html).

Jupyter notebooks are run on `python`, though additional things can be downloaded to allow you to use your programming language of choice. For examples of what you can do with Jupyter notebooks, click [here](), and [here](https://github.com/jupyter/jupyter/wiki/A-gallery-of-interesting-Jupyter-Notebooks#programming-and-computer-science) for a collection of neat and applied notebooks.

- Download the full [anaconda](https://www.anaconda.com/download/) distribution i.e. not miniconda
    - Be sure to choose `Python 3.x`, not `Python 2.x`, as it's the newer version and is fowards-compatible.
    - Be sure to only install for one user, not the whole system
    - Be sure to select `Add Anaconda to my PATH environment variable` under Advanced Options
    -
- Use `kernels` to connect your programming language of choice with python and the notebook
    - To see how to get a particular language to work in Jupyter Notebooks, please click on the appropriate language:
        - [Stata](### Installing the Stata Kernel)
        - [R](### Connecting R with Jupyter)

### Creating a notebook

You can either open up the anaconda navigator and then Jupyter Notebooks, or open Jupyter Notebooks directly. Once open, navigate to the directory you would like to create the notebook in (*If you are using a version control system like git, then you should be within the project's repository*)

Select the **New** button in the top right corner, and then select the language you would like to program in (*this assumes that you have downloaded an appropriate `kernel` if you would like to use a language other than `python`*)

### Installing the Stata Kernel

The instructions for installing the `stata_kernel` are based from the original documentation [here](https://kylebarron.github.io/stata_kernel/getting_started/). It should work with `Stata 12` (we have tested it). If these instructions do not work for you, it may be that there has been an update to the `kernel`, at which point, please refer to the original documentation linked above.

Open a command prompt (Windows) / terminal (linux/mac) and type/copy-paste the following commands, pressing enter after each line

- `pip install stata_kernel`
- `python -m stata_kernel.install`

---
**Windows-specific steps**

In order to let `stata_kernel` talk to Stata, you need to link the Stata Automation library:

1. In the installation directory (most likely `C:\Program Files (x86)\Stata12` or similar), right-click on the Stata executable, for example, `StataSE.exe` (this will just show as `StataSE`, but is listed as an application). Choose `Create Shortcut`. Placing it on the Desktop is fine.
2. Right-click on the newly created `Shortcut to StataSE.exe`, choose `Properties`, and append` /Register` to the end of the Target field. So if the target is currently `"C:\Program Files\Stata12\StataSE.exe"`, change it to `"C:\Program Files\Stata12\StataSE.exe" /Register` (note the space before `/`). Click OK.
3. Right-click on the updated `Shortcut to StataSE.exe`; choose Run as administrator.
4. Enter your CIHS details
---

### Installing the SAS kernel

*This has not yet been tested here at PHO. The instructions for installing the `sas_kernel` are based from the original documentation [here](https://github.com/sassoftware/sas_kernel)*

Open a command prompt (Windows) / terminal (linux/mac) and type/copy-paste the following commands, pressing enter after each line. First we need to install a dependecy called `saspy` that helps the kernel connect `SAS` to `python`

- `pip install saspy`
- `pip install sas_kernel`

You should now see something like this.

```
Available kernels:
python3    /home/sas/anaconda3/lib/python3.5/site-packages/ipykernel/resources
sas        /home/sas/.local/share/jupyter/kernels/sas
```

Now verify that the SAS Executable is correct

- find the `sascfg.py` file -- it is currently located in the install location (see above) `[install location]/site-packages/saspy/sascfg.py`. To query `pip` for the location of the file, type `pip show saspy`. Failing that, this command will search the OS for the file location: `find / -name sascfg.py`
- edit the file with the correct path the SAS executable and include any options you wish it include in the SAS invocation. See examples in this [file](https://github.com/sassoftware/saspy/blob/master/saspy/sascfg.py)


### Connecting R with Jupyter

If you are hoping to make nice documents and reproducible work using `R`, I would highly recommend that you use the `R Markdown` or `R Notebook` through [`RStudio`](https://www.rstudio.com/products/rstudio/download/) application instead. However, if you would prefer Jupyter, then please read on.

It is possible to download an `R kernel`, much like for `Stata` and `SAS`, but it can be a bit fickle, so a different approach is described below. It is important to note that with this method you are installing a fresh version of `R`, so you will not have access to the packages you have previously installed - you will need to reinstall them in this `R` environment, which could be done within a Jupyter notebook.

Open a command prompt (Windows) / terminal (Linux/Mac) and type/copy-paste the following commands, pressing enter after each line

- `conda install r-essentials r-igraph`
- `Rscript -e 'install.packages("languageserver")'`

If you would rather install an `R kernel` than a fresh install of `R` within the `anaconda` distribution, you can follow the instructions [here](https://richpauloo.github.io/2018-05-16-Installing-the-R-kernel-in-Jupyter-Lab/). The advantage of this is that it allows the notebook to access previously installed packages as they are not running off a fresh version of `R`.


### Connecting other kernels

To see a full list of `kernels` available for Jupter, along with the appropriate documentation and installation instructions, follow this [link](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels).
