# CMSC 6950 Project

Spring 2021

Due: June 17, 2021

## Introduction

In computational science, a very common scenario is
- develop a software code that computational solves a scientific problem;
- run that software under various conditions;
- save the output as intermediatary file storage;
- visualization the output using charts and figures;
- document your results in a scientific paper or report;

For this project, I want you to imagine that you are new researcher in a given computational
science domain.  At a recent conference, you saw a presenation by another research group
and you want to try and reproduce some of their work. Fortunately, they have released
their software as open-source and published it in the
[Journal of Open Source Software (JOSS)](https://joss.theoj.org/)

Choose a *Project Topic* from the list of JOSS papers [here](Topics.md) 

You have 
Suppose that you are trying to solve some problem and you are writing a report that describes 
the solution to that problem. Imagine that you have chosen to use a
third-party Python software package to help solve the problem. In this project, you will
use that software package to solve your problem and describe the results in a LaTeX
based report along with a minimum of two visualizations and/or tables (at least one of
which needs to be completed with matplotlib).


The report is supposed to be about the solution to the imaginary problem, but some
students in the class have interpreted the project as being about a Python software
package itself. However, please do not rewrite your reports; either way of presenting the
report (as either a) a description of a solution to a problem that happens to use a
third-party Python package or b) a description of a third-party Python package that
happens to show how that package can solve a problem) is completely acceptable.

An important goal is making your overall workflow (data management, data analysis,
visualization, and report generation) reproducible (See
[https://lorenabarba.com/blog/barbagroup-reproducibility-syllabus](https://lorenabarba.com/blog/barbagroup-reproducibility-syllabus)
for papers that explain
what reproducibility means here). To achieve a reproducible workflow, the software tool
make should be used to set up your workflow in a Makefile. This Makefile is responsible
for orchestrating the sequence of steps needed into discrete steps where intermediate
files (such as downloaded input data, processed files, plots, and PDFs) are generated
and saved. Deleting only a few of these intermediate files should result in the make only
needing to regenerate the portions of the workflow that are dependent on the deleted
intermediate files.

It is typical that a computational workflow will involve the downloading, cleaning, filtering,
or generating of some type of input data. Your project should clearly describe what the
“input data” is for your workflow.

Write Python scripts (.py files) or bash scripts (.sh files) that actually do the required

steps in your workflow. While Jupyter notebooks are a great tool for exploring how to

implement your project, notebooks should not be a part of the eventual workflow.

Instead, write stand alone python scripts that take in either command line arguments or

input files and produce new files as output. Again, a Makefile should be included in the

project that actually is used to run these various scripts you have created.

To submit your project, you need to create a public GitHub repository with your workflow

and LaTeX report. Your commit log should reflect the incremental progress you make

toward completing the project. You may include processed data files and plots in your

repo as well but your Makefile should include a “make clean” target that removes any

files that can be reproduced. Temporary auxiliary files (such as .out, .aux, .log from

latex or .pyc from python) should not be included in your git repo. If any step in your

workflow takes a significant amount of time to run (for this project, let’s say that is

greater than 3 minutes) then you should include the intermediate result in your repository

so that others do not have to wait to run a long workflow.

Finally, there are always steps (like installing required software, or registering for an API

key) that may need to be set up before your Makefile is able to run correctly. Please

document those required steps in a Readme.md file in the repo. At minimum, this

Readme file should contain the title of the report, your name, a link to the repo of the

software package you are using, and a sentence like “To regenerate this report, clone

this repo and type \`make\`”. Additional information can be provided in the Readme.md if

you think it is important.

The project will be evaluated according to the following marking scheme based on 10

components:

1. Description of data source/problem

Does the report explain what is the problem to be solved and the data

used? Does it identify the source of the data?

2\. Description of analysis workflow

Does the report explain the approach used in solving the problem? Does

the report make a cited reference to the software package or algorithm

being used? Is it clear what functionality or library function calls of the

third-party software is being used?

3. Use of third-party Python package

When considering the Python code in the scripts of the project, the

third-party software package being called correctly? When compared

against the documentation for the software, does it appear that software is

being used correctly? The code that calls the third-party software package

readable and understandable?

4\. Use of git and GitHub

Has the project been submitted using GitHub? Does the git commit log

show at least 3 (and probably more) separate commits? Are the commit

messages meaningful?

5\. Makefile and reproducibility

When the instructions in the Readme.md are correctly followed, does

running make reproduce the entire workflow? This can also be tested by

deleting one of the intermediate files (targets) as given in the Makefile and

confirming that the processing and plotting still work.

6\. Creation of LaTeX report

Is the report a LaTeX document showing use of \\section, \\maketitle, and

\\includegraphics ? Does running either pdflatex or latexmk regenerate a

PDF version of the report without errors?

7\. Matplotlib based visualization (1)

Does the plot have reasonable styling options (e.g. axis labels, legends,

colorbar) applied? Does the matplotlib code that generates and saves the

figure in a file work correctly? Does the plot make sense in the context of

the report?

8\. Visualization or data product (2)

Does the visualization make sense in the context of the report? This

second visualization could be a matplotlib figure, a map, a table, or any

other type of data project that is appropriate to the context of the report.

9\. Peer evaluation

Thinking about the previous eight evaluation components, how would you

rate the overall execution of this project? Were you able to reproduce the

workflow? Was the code readable and understandable? Did the report try

and use the third-party package in an interesting or novel way? How does

this project compare to others you evaluate in your peer group?

10\. Originality and novelty

Does the project go beyond a simple reproduction of the third-party

software package’s documentation or examples? Does the code and

project make use of the other concepts we have learned about in

CMSC6950 (bash scripting, python data structures and functions, numpy,

matplotlib, and pandas)? Is the input data data set chosen novel or has

the third-party package been applied creatively?


Each component is worth 10 points (project total, 100 points). Rubric for each
component:

0 - Component not attempted or submitted in any way

3-4 - Only a preliminary and incomplete attempt at satisfying component requirements.

5-6 - Partial completion of component showing an attempt that demonstrates some

knowledge of topics covered in CMSC6950

7-8 - Minimal completion of component’s requirements but only superficially

demonstrating knowledge of topics in CMSC6950

9-10 - Completion of component’s requirements and demonstrating mastery of topics

covered in CMSC6950
