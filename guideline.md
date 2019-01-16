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

## Jupyter Notebooks

- Run on `python`
    - Download the full [anaconda](https://www.anaconda.com/download/) distribution i.e. not miniconda
        - Be sure to choose `Python 3.x`, not `Python 2.x`, as it's the newer version and is fowards-compatible.
        - Be sure to only install for one user, not the whole system
        - Be sure to select
- Use `kernels` to connect your programming language of choice with python and the notebook
    - To see how to get a particular language to work in Jupyter Notebooks, please click on the appropriate language:
        - [STATA](### Installing the STATA Kernel)
        - [R]()

### Creating a notebook

You can either open up the anaconda navigator and then Jupyter Notebooks, or open Jupyter Notebooks directly. Once open, navigate to the directory you would like to create the notebook in (*If you are using a version control system like git, then you should be within the project's repository*)

Select the **New** button in the top right corner, and then select the language you would like to program in (*this assumes that you have downloaded an appropriate `kernel` if you would like to use a language other than `python`*)

### Installing the STATA Kernel

- Download [`stata_kernel`](https://kylebarron.github.io/stata_kernel/getting_started/)
    - follow the instructions on the website, particularly if you are on Windows.
    - It should work with `STATA 12`
        - We have tested it

Open a command prompt (Windows) / terminal (linux/mac) and type/copy-paste the following commands, pressing enter after each time
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

### Installing the R Kernel
