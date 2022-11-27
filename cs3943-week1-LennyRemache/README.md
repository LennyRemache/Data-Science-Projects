# Getting Started
Welcome to Introduction to Data Science!

The purpose of this assignment is to get you set up with the tools needed to succesfully complete this course and get you acclimated to the workflow for completing in-class group assignments. This process includes installing Anaconda and learning basic **git** commands. Below is an outline of what is going to be accomplished by the time you reach the end of this document.

## TABLE OF CONTENTS
1. [Install Anaconda](#anaconda)
1. [Update Anaconda](#update)
1. [Install Python libraries](#library)
  1. [Launch command-line terminal](#terminal)
  1. [Using the `conda` command-line program](#conda)
  1. [Creating a course specific conda environment](#env)
3. [Download the repository](#download)
4. [Modify your first Jupyter notebook](#modify)
5. [Commit your changes](#commit)

<a name="anaconda"></a>
### Install Anaconda
While Python's data science tools are well-designed and incredibly powerful, installing them directly on your computer can be a tricky endeavor which requires the proper installation of a number of prerequisite libraries. This installation process can become unwieldy if care is not taken to match the right library version for the correct computer architecture. To make access to these tools simpler, there are package management systems that take care of these details for you. One such package management system built specifically for Python's data science ecosystem is named **Anaconda**. Anaconda is an industry standard toolkit that is free to use for non-commercial purposes (such as an academic course). This first step will provide guidance on installing Anaconda on your computer.

Navigate to the [Anaconda installation documentation](https://docs.anaconda.com/anaconda/install/), follow the installation instructions for your operating system, and return here when done.

<a name="library"></a>
### Install Python libraries

There are multiple ways to install the Python libraries that we will make use of this semester onto your personal computers. Anaconda provides a graphical user interface (GUI) named **Anaconda Navigator** that simplies this process. However, if you do not have much experience using a command-line terminal, this is a good opportunity for a gentle introduction/refresher on its use. 

(MacOS and Linux users can skip to the section labeled [Using the `conda` command-line program](#conda))
<a name="terminal"></a>
#### Launch command-line terminal
Linux and MacOS users have the benefit of a pre-installed command-line terminal that requires no further steps to utilize. However, if you are using a Windows machine, accessing a command-line terminal takes a little bit more effort. Fortunately, Anaconda provides a terminal program when installed on Windows. 

* For Windows users, *Anaconda Prompt* can be accessed through the following steps:

1. Click on **Start**
1. Select **Anaconda3**
1. Select **Anaconda Prompt**
1. Type `conda install m2-base` and press **Enter** (the `conda` command will be covered in greater detail in the next section)
1. Type `y` at the `Proceed ([y]/n)?` prompt


* For MacOS users, *Terminal* can be accessed through the following steps:

1. Click on **Finder** 
1. Open the **Applications** folder
1. From the Applications folder, open the **Utilities** folder 
1. Double-click the **Terminal** app

* For Linux users, terminal access differs by distribution. Please search for distribution specific instructions online.
<a name="conda"></a>
#### Using the `conda` command-line program 
The `conda` program is one of the most common utilities that you will use when working with Anaconda. Read [Getting started with conda](https://conda.io/projects/conda/en/latest/user-guide/getting-started.html) for a brief overview of some basic things you can accomplish with `conda`.
<a name="env"></a>
#### Creating a course specific conda environment
*Getting started with conda* covered the topic of `conda` environments. It is **highly** recommended that you maintain individual environments for different projects that you are working on. You can consider this course one big project and can maintain a single environment for the remainder of the semester. For the purposes of this example, we'll refer to the environment for this course as **introds** but feel free to give whatever name you would like to the environment. Begin by updating `conda`, if you have not already done so by running the following command at the prompt:

```
conda update conda
```
#### Add packages to your environment
While it is possible to create your environemnt and install all of the packages that you require in one step, it is instructive to go through the package installation process one package at a time to get used to it. The **introds** environment can be created with the following command:

```
conda create -n introds
```

After entering `y` at the confirmation prompt, the **introds** environment will be available. Make this environment the active Anaconda environment by issuing the following command:

```
conda activate introds
```

Any time that you restart your computer, you will need to reissue this command to activate the **introds** environment. From here, you can install the packages that we will utilize for the semester.

NumPy is one of the fundamental packages on which many of the tools in the Python data science ecosystem are built. Let's begin by installing this library. Type the following command at the command-line prompt:

```
conda install numpy
```

Installing NumPy will require a number of prerequisite libraries be installed. Confirm that you want to proceed by entering `y` at the prompt. When the command-line prompt is re-displayed, NumPy is now available in any Python program run in the **introds** environment. Repeat this process using the following commands to complete installation of the libraries needed for this course:

```
conda install scipy
conda install pandas
conda install matplotlib
conda install seaborn
conda install scikit-learn
conda install statsmodels
conda install networkx
conda install jupyter
```

When the listed commands are completed, **introds** will be setup for use in this course. 

There are two remaining aspects of your environment to begin getting used to. The final package that was installed (`jupyter`) gives us access to the Jupyter Notebook program which will be covered shortly. All of your in-class assignments will be developed in this environment and your familiarity with using this software will grow as the semester proceeds. In addition, your in-class assignments will be submitted using the **git** version control system. This guide will end with a short introduction to both of these tools.

Before continuing, type and execute the following command:

```
python -m ipykernel install --user --name=introds
```

Execution of this command is necessary, so that all of the packages that you just finished installing into your environment are available when you are working in your Jupyter Notebook.

<a name="download"></a>
### Download repository

The document that you are currently reading is in your personal repository for week 1's assignment. Also, present in this repository is a blank document named **setup.ipynb**. Your goal is to download this document as part of your repository, modify **setup.ipynb** locally on your computer, and add the local changes that you made to this repository.

In the git version control system, downloading a record of your repository can be accomplished using the command `git clone`. The full command is 

```
git clone <repo>
```
where *\<repo\>* is replaced by the url of this repository. The repository url can be obtained by

1. clicking on the **Code** button near the top of this page
1. selecting the **HTTPS** tab
1. copying the full *github.com* url displayed in the dialog box

Replace *\<repo\>* in the `git clone` command with your repository url and execute this command in your terminal application (either Anaconda Prompt on Windows or Terminal on MacOS/Linux). You will be prompted to log into your GitHub account to complete the command. When the command-line prompt returns, your repository, named **cs3943_week1** will be present on your local computer.
  
<a name="modify"></a>
### Modify your first Jupyter notebook
Enter your repository by typing the command:

```
cd cs3943_week1
```

You are now inside of your repository. 


#### Launch the Jupyter Notebook program
To launch the Jupyter Notebook program, you do so by typing the following command:

```
jupyter-notebook
```

When you want to immediately open a Jupyter notebook that already exists, the command is slightly different:

```
jupyter-notebook <notebook-name>.ipynb
```
where *\<notebook-name\>* is the name of the Jupyter notebook file that you want to open. `.ipynb` is the extension for Jupyter notebooks which enable the usage of Python directly in a web browser. In this case, use this command to launch the Jupyter Notebook application and open the **setup.ipynb** file for viewing/modification.

Before modifying your file, complete the following tasks:

1. Select **Kernel** from the options menu
1. Hover over **Change kernel** form the drop-down menu
1. Select **introds** from the list of options

You will need to do this **every time** you open a new Jupyter notebook for in-class assignments to ensure that your Anaconda environment (and all of its related packages are available in your notebook).

Next to the prompt (`In [ ]:`), enter the following code:

```
import numpy as np
print(np.array("Hello World"))
```

Click on the **Run** button underneath the main menu. If all goes well, you should see `Hello World` output. If not, ask for help at this stage.

Now, save your changes to the file by selecting the left most button (to the left of the **+** button) on the same row as the **Run** button, you clicked previously. This is the button that you use for saving changes to your Jupyter notebooks. The changes to your notebook have now been preserved.

<a name="commit"></a>
### Commit your changes

The final step to complete is updating your repository in GitHub so that your changes are reflected here. First, you need to add your modified file to the files that will be included in the update to your repository. Type and execute the following command at the command-line:

```
git add setup.ipynb
```

Now, commit the change to your local repository by typing and executing the following command:

```
git commit -m "adding my changes to GitHub"
```

The `-m` flag allows a message to be included with the changes that you are making so that you can keep track of different updates that you make to files in your repository. Think of this message as a useful form of documentation. Therefore, it is **highly** recommended to use a meaningful commit message. Finally, to have the changes reflected in your GitHub repository type and execute the following command.

```
git push -u origin main
```

You may need to enter your GitHub credentials at this stage. If all goes well, the command-line prompt should return without any error messages. If you get an error, ask for help. The **git** program has many powerful features that we will not be utilizing in this course. But the steps that you just completed are what you will need to do each week to check in your work on the in-class assignment. Keep this README handy for the next couple of weeks as you get used to this process. And, with that, your environment setup for Introduction to Data Science is complete!
