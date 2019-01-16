---
title: "PHO Data Management Guidelines"
author: "Callum Arnold"
date: "16 January 2019"
output:
  html_document:
    toc: yes
    toc_float:
      collapsed: yes
      smooth_scroll: yes
---


# Reproducible Work

## What is reproducible work?

- Contains relevant code, including which packages were used
- Contains enough text, either via markdown or comment to be able to understand what the purpose of each code is
    - Ideally integrates code and results, along with text, into a single document

## Why is it important?

Simply put, all code and work has mistakes and bugs. If you are able to


# Structuring a project

- VCS
- Data isn’t touched one collected:
- Do all data munging within your program i.e. no editing the excel spreadsheets!!!
- Never set explicit file paths if you can avoid it i.e. `setwd()`

# Git

Think of it as tracked changes for your code. When working on a project by yourself, it’s important to be able to go back to previous versions if you make a mistake and can’t remember all the steps you went through since your last stable version.

## Branching

# Notebooks

- Many examples of different kinds of notebooks
- Jupyter useful as you can see the results immediately integrated within the document
    - Has a system to allow other statistical and programming languages to run via kernels
        - Other systems don’t allow this level of integration, so will not be explored in much detail

## Jupyter Notebooks

- Run on python
    - Download anaconda

### Kernels

- Needed to connect your programming language of choice with python and the notebook
- Download stata_kernel
