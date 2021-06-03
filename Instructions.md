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

**STEP 1** Choose a *Project Topic* from the list of JOSS papers [here](Topics.md). 
It is not necessary that you have any prior expertise in the area. Choose any of the topics
that looks interesting to you.  Start by reviewing the JOSS paper, the GitHub repository
for the software, and the documentation (often made available on a [Read the Docs](https://readthedocs.org/)
site). You may need to look at several different topics before finalizing you decision.

In this project, your task is to reproduce at least *two* "computational tasks" based on the 
chosen project topic
and produce at least *two* "visualizations" (using Matplotlib) that show the results of 
the computation. You also need to create a LaTeX based report that describes the software
you are using, the science problem it address (a very high-level description is acceptable),
describes the "computational tasks" you have performed, and includes the visualizations in the body
of the report.  Your report must have a bibliography (although may only need a single JOSS reference!)

**STEP 2** Create a new, *public* GitHub repo for this project called `<GitHubID>/CMSC6950_Project`.  
Regularly commit (with useful commit messages) changes you make related to this project.  Set up, install, and/or configure your
chosen project topic to be able to run on your system. Create a `README.md` that explains precisely
what is required to get the project software to run. If appropriate, create a new `conda` environment
install any software dependencies. Verify that your instructions are sufficient to run this software the
server `cmsc6950.munroelab.ca`.

What constitutes a "computational task" will differ between the different project topics. For
these topics, it will involve performing a calculation, running a model, or extracting data
from an online source.  In any case, implement your project so that this task saves any output 
to an intermediate file.  Make the assumption that the "computation" is non-trivial
and you want to be able to examine the results without having to rerun the task.  Each visualization
(Matplotlib based) should be implemented as Python script that loads in this
intermediate file. Use command line arguments to pass around the filenames for both the intermediate
data and the final image output file.  

**STEP 3** Work through the examples in the documentation or tutorial for the project topic to identify
at least two different computational tasks to perform. While the example may be available as a Jupyter
Notebook, your implementation should be a Python script that is run at the command line. You may choose
to do two distinct computational tasks, or the same computational twice using different parameters, 
configurations, or input data. If run-time parameters need to be passed into your Python script use
command line arguments.  If you want, you may come up with your own computational task using the project
topic software but reproducing a documented example is sufficient for this project.

You may need to work through several examples before settling on computational
tasks that are appropriate for the project. Remember to use git and commit your Python scripts often
during this development and exploration phase of the project. If you find you are hitting a critical
road block and need to choose a different project topic, you are permitted to go back to Step 1 and 
choose a different topic. However, please continue to use the same git repository throughout this
project even if you choose to switch topics. A record of attempts that did not lead to success is
an important part of science!

**STEP 4** Develop at least two visualizations using Matplotlib showing either the output for your computational
task.  Using Jupyter may be a useful tool as you work on your visualization (remember to use git to commit
your notebook to your repository) but, eventually, you will need command line based Python script that 
produces the visualizaiton.  

, In this project, you must use a *Makefile* to control the overall 

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
