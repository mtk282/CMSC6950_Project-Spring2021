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

## Computational Tasks

In this project, you are asked to perform at least *two* "computational tasks" based on the 
chosen project topic and produce at least *two* "visualizations" (using Matplotlib) that show the results of 
the computation. You will also need to create a LaTeX based report.

**STEP 2** Create a new, *public* GitHub repo for this project called `<GitHubID>/CMSC6950_Project`.  
Regularly commit (with informative commit messages) changes you make related to this project.  
Set up, install, and/or configure your chosen project topic to be able to run on your system. 
Create a `README.md` that explains precisely what is required to get the project software to run. 
If appropriate, create a new `conda` environment install any software dependencies. Verify that your
instructions are sufficient to run this software the server `cmsc6950.munroelab.ca`. If you need any system
level libraries installed on this server, please let the instructor know
via Slack.

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
topic software but reproducing documented examples is sufficient for this project.

You may need to work through several examples before settling on computational
tasks that are appropriate for the project. Remember to use git and commit your Python scripts often
during this development and exploration phase of the project. If you find you are hitting a critical
road block and need to choose a different project topic, you are permitted to go back to Step 1 and 
choose a different topic. However, please continue to use the same git repository throughout this
project even if you choose to switch topics. A record of attempts that did not lead to success is
an important part of science!

## Visualizations

**STEP 4** Develop at least two visualizations using Matplotlib showing either the output for your computational
task.  Using Jupyter may be a useful tool as you work on your visualization (remember to use git to commit
your notebook to your repository) but, eventually, you will need command line based Python scripts that 
produces the visualization as files in an appropriate graphics file format. Again, you may need to explore
several different visualizations before commiting to a final visualization.

You are welcome to try and reproduce any Matplotlib figure you see in the documentation, examples, or 
tutorials of the software project topic. However, please attempt to write code for this plot is your *own*
work and not a cut-and-paste from the documentation. In your visualzations, be creative with the
Matplotlib library. A simple line plot with axis labels is not very innovative.

## Reproducible Workflow

**STEP 5** Write a `Makefile` to automate the executation of your computational tasks and your visualizations.
Your `Makefile` may assume that any needed software (as documented in your `README.md` file) has already been 
set up.  If you need to download or create any input data this should be down using a target with Make.  
If possible, do not add input data or intermediate files to your git repository.  You may include your produces image
files to your git repository (this may be helpful for your LaTeX report).  Your `Makefile`
should be written to recreate any dependency as needed. Add a `make clean` target that, once run,
will ensure `git status` will report no untracked or changed files. Temporary auxiliary files (such as `.out`, `.aux`, `.log` from
LaTeX or `.pyc` from python) should not be included in your git repo.

An important goal of this project is making your overall workflow (data management, data analysis,
visualization, and report generation) reproducible (See
[https://lorenabarba.com/blog/barbagroup-reproducibility-syllabus](https://lorenabarba.com/blog/barbagroup-reproducibility-syllabus)
for papers that explain
what reproducibility means here). To achieve a reproducible workflow, the software tool
make is being used. Make is responsible for orchestrating the sequence of steps needed into 
discrete steps where intermediate files (such as downloaded input data, processed files, plots, and PDFs) are generated
and saved. Deleting only a few of these intermediate files should result in make only
needing to regenerate the portions of the workflow that are dependent on the deleted
intermediate files.

Test your workflow regularly by cloning your GitHub repository on `cmsc6950.munroelab.ca` and running `make`. Assuming
you have already completed the instructions in your `README.md` file, your entire computational workflow should
run without errors. 

## Report

**STEP 6** Write a LaTeX based report that describes the software
you are using, the science problem it address (a very high-level description is acceptable),
describes the "computational tasks" you have performed, and includes the visualizations in the body
of the report.  Your report must have a bibliography (although may only need a single JOSS reference!)

Your `Makefile` should have a target `report.pdf` that includes any needed dependencies. This should be the default
target. You may use the software platform *Overleaf* to aid in the creation and testing of your LaTeX report.
Remember to connect it with your GitHub project so that you creating a history of changes to your report.
Depending on your operating system, installing LaTeX may be simple or complicated so it is your
choice if you want to install it or not.  On `cmsc6950.munroelab.ca`
a full LaTeX installation will be available so that you can confirm that LaTeX is working as expected.  Add
your produced `report.pdf` to the GitHub repo so that others can see the completed documented without having to 
rerun your entire workflow.  

It is typical that a computational workflow will involve the downloading, cleaning, filtering,
or generating of some type of input data. Your project report should clearly describe what the
*input data* for your workflow (if applicable). 

Remember to write Python scripts (`.py` files) or bash scripts (`.sh` files) that actually do the required
steps in your workflow. While Jupyter notebooks are a great tool for exploring how to
implement your project, notebooks should not be a part of the eventual workflow.
Instead, write stand alone python scripts that take in either command line arguments or
input files and produce new files as output. Again, a requirement of the project is that `Makefile`
be used to run the various scripts you have created.

Your project is submitted using the public GitHub repository `<GitHubID>/CMSC6950_Project` 
with your codes and report. Your commit log should reflect the incremental progress made while
toward completing the project. 

## Evaluation

The project will be evaluated according to the following marking scheme based on the following ten
components:

1. *Description of project topic and software used*  Does the report explain (broadly) what the scientific problem is being solved. Is the software chosen for the project well described? Is sufficient background information presented so that the reader can understand the context of the rest of the report? 

2. *Description of computational tasks and workflow*  Does the report explain the approach used in solving the problem? Does
  the report make a cited reference to the software package and/or algorithm
  being used? Is it clear what functionality or library function calls of the third-party software is being used?

3. *Computational tasks*
  When considering the Python code in the scripts of the project, the
  third-party software package being called correctly? When compared
  against the documentation for the software, does it appear that software is
  being used correctly? The code that calls the third-party software package
  readable and understandable?

4. *Use of git and GitHub*
  Has the project been submitted using GitHub? Does the git commit log
  show several separate commits? Are the commit
  messages meaningful?

5. *Makefile and reproducibility*
  When the instructions in the `Readme.md` are correctly followed, does
  running make reproduce the entire workflow? This can also be tested by
  deleting one of the intermediate files (targets) as given in the Makefile and
  confirming that the processing and plotting still work.

6. *Creation of LaTeX report*
  Is the report a LaTeX document showing use of \\section, \\maketitle, and
  \\includegraphics ? Does running either `pdflatex` or `latexmk` regenerate a
  PDF version of the report without errors?

7. *Matplotlib based visualizations*
  Do the figures have reasonable styling options (e.g. axis labels, legends,
  colorbar) applied? Does the matplotlib code that generates and saves the
  figure to a file work correctly? Do the plots make sense in the context of
  the report?

8. *Scope and effort*
  Are there at least two computational task included? Are there at least two
  visualizations included in the work flow? Do the computational tasks
  and visualizations attempted (as seen in the either the report or the git
  history) demonstrate engagement with the project topic at a level consitent
  with a graduate course?

9. *Peer evaluation*
  Thinking about the previous eight evaluation components, how would you
  rate the overall execution of this project? Were you able to reproduce the
  workflow? Was the code readable and understandable? How does
  this project compare to others you evaluate in your peer group?

10. *Originality and mastery*
  Does the project go beyond a simple reproduction of the third-party
  software package’s documentation or examples? Does the submitted code and
  project make use of the other concepts learned about in
  CMSC6950 (bash scripting, python data structures and functions, numpy,
  matplotlib, and pandas)? Have the chosen computatational tasks using the third-party package been applied creatively?

Each component is worth 10 points (project total, 100 points). Rubric for each
component:

- 0 - Component not attempted or submitted
- 3-4 - Only a preliminary and incomplete attempt at satisfying component requirements.
- 5-6 - Partial completion of component showing an attempt that demonstrates some
knowledge of topics covered in CMSC6950
- 7-8 - Minimal completion of component’s requirements but only superficially
demonstrating knowledge of topics in CMSC6950
9-10 - Completion of component’s requirements and demonstrating mastery of topics
covered in CMSC6950
