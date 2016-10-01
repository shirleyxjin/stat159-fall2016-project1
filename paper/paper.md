![](https://raw.githubusercontent.com/ucb-stat159/stat159-fall-2016/master/projects/proj01/images/stat159-logo.png)


## Abstract

This paper is a project for _STAT 159 – Reproducible and Collaborative Data Science_. The intent of this paper is to briefly introduce the roles and basic commands of the common computational tools used for reproducible data science work:
- Makefile
- Git
- GitHub
- Pandoc
- Markdown.

This paper will document the steps to create and recreate this project, and discuss the findings and challenges in using these tools.
## Introduction

Reproducible workflow is becoming increasingly important in many areas of studies where people are paying closer attention to the validity and replicability of analysis performed supporting research results and findings. Reproducible work not only helps the academics examine and verify research progress, but also can be used to improve the overall analysis capability. Computational tools such as **bash**, **Markdown**, **pandoc**, **Git**, **GitHub**, **Makefile**, and text editors such as **Vim**, therefore, are becoming more important and valuable as they make the reproducibility of workflow much easier and more convenient to accomplish. In this paper, I will briefly discuss the roles of some of these computational tools, and detail the challenges in using such tools.
### Makefile
First, let me explain what a makefile is. A Makefile is a file that contains shell commands. It is a file such that when you call that Makefile by command make in that directory you wish, the shell commands contained in the Makefile will be executed. In an effort to create a reproducible workflow, Makefile keeps track of source files and when source files are updated, Makefile can recreate the entire process and update the result files/steps with ease, by simply calling command _make_. Without a Makefile, the process becomes much more complicated and time-consuming, and you’d have to recreate every step that it took to create the original changes.
The typical structure of a rule within a makefile is as follows:
```
target: dependencies ...
	commands
	...
```
For this project, a Makefile was created to compile the individual markdown files into one final paper, and convert the paper markdown file into a html file. There’s also a _clean_ command that will remove the paper both in markdown version and in html version.

### Git
![Git](https://raw.githubusercontent.com/ucb-stat159/stat159-fall-2016/master/projects/proj01/images/git-logo.png)

Next, let’s learn about Git. Git is a version control system that makes the collaboration process much easier and allows a user to keep track of the different changes made and different versions of the files. When collaboration is needed for a digital project, Git helps every member of the team to keep track of the most updated versions so that when changes are made to the versions, there are no conflicting copies and no one has to dig through 10 files if they decide to abort a change and go back to the previous versions. Git was used for this project to track the changes of the versions of the paper, and to have the work available to view on GitHub. Specifically, there are the codes I used to set up a Git repo:
```
mkdir stat159-fall2016-project1
cd stat159-fall2016-project1
git init
```
We tell Git to track a file by:
```
git add 00--abstract.md
```
We can record the changes by:
```
git commit -m "Message"
```
We can check the status of our project by:
```
git status
```

### GitHub
![Github](https://raw.githubusercontent.com/ucb-stat159/stat159-fall-2016/master/projects/proj01/images/github-logo.png)

GitHub is a web-based Git repository hosting service. It provides access control and collaboration features such as bug tracking, feature requests, task management for every project. GitHub is an open source website for sharing of codes used for research papers. It makes the sharing of codes simpler and thus increases the ease of code checking and research reproduction. Several features of GitHub were used for this project, namely the documentation in the form of an automatically rendered README file in markdown format, and project collaboration feature with Professor Sanchez and GSI. Specifically, I set up the remote repository by:
```
git remote add origin http://...
```
And we can push changes from our local repository to GitHub by:
```
git push origin master
```

### pandoc
![pandoc](https://raw.githubusercontent.com/ucb-stat159/stat159-fall-2016/master/projects/proj01/images/pandoc-logo.png)

[Pandoc](http://pandoc.org/) is another great computational tool. Pandoc is an open-source file converter that allows simple conversion of one markup format into another. Pandoc can convert documents in markdown, reStrcturedText, textile, HTML, LaTeX, and many more. It is a useful tool in producing reproducible work as it allows simple conversion of R files, markdown files into publication-ready formats such as HTML and LaTeX. It makes the sharing of code and workflows effortless. For this project, Pandoc was used to convert the project paper markdown file into html format using the following code:
```
pandoc -s paper.md -o paper.html
```

### Markdown
![Markdown](https://raw.githubusercontent.com/ucb-stat159/stat159-fall-2016/master/projects/proj01/images/markdown-logo.png)

The last computational tool I’ll explain is Markdown. [Markdown](http://macdown.uranusjr.com) is a lightweight markup language with plain text formatting syntax that can be easily converted to HTML and other formats. Markdown is typically used to format README files, and text writing using a text editor. Markdown is intended to be easy-to-read and easy-to-write. A markdown document should be published and presented as plain text without displaying the syntax used to format the text.

### Project Discussion
The easiest parts in this project were the write-up of Markdown files, and the structuring of project files through simple commands using bash. Markdown is fairly easy to use, and the syntax is not hard to learn. The commands in bash are also relatively easy, these are commands that I’ve previously had experience working with and the tree structure of Unix directories is logical enough to understand. The utilization of pandoc wasn’t too difficult either. The conversion step was quite simple.

The most challenging parts of this project were the write-up of Makefile and use of Git. These are also the parts that took the longest time. I haven’t had much experience using Makefile and it took me a while to understand the different elements contained in a Makefile and the structure of writing the codes. For this project, the codes were fairly simple, however, the write-up for a more complicated project with many more files and more complicated dependencies will require some effort. However, a Makefile also is the most useful tool in a reproducible workflow in that it automates the workflows and allows updating of data and results much simpler and time-efficient. Git was also fairly complicated for me for this project. I still need to familiarize myself with the different codes and it will take some practice to fully master the tool.

I utilized a lot of lab materials, previous examples and exercises, and external sources for this project. I also leveraged help from a classmate when I got stuck on some codes. This project took approximately 7-8 hours to complete.
## Conclusion

To conclude, this project not only made me understand and be able to utilize the computational tools used in reproducible and collaborative data science, it also made me realize how important having reproducible work is. Through the use of the Markdown, pandoc, Makefile, Git and GitHub, this project could be easily shared and reproduced for learning purposes. Learning the tools is a fundamental step before we can start thinking about the creation of meaningful reproducible data science work.
