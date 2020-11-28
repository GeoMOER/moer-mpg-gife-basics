---
title: "Assignments and Working Environment"
toc: true
toc_label: In this info
---



Within this course you will submit your solutions for the course assignments to your GitHub-hosted learning log, i.e. your  personal classroom repository. Don't get confused about _"personal repository"_. Once you have a GitHub account, you can create as many repositories as you like at your account and invite any team members you want but for assignments within our courses, always use your classroom repository. 
<!--more-->
The classroom repository will be created automatically by following a link to the respective classroom assignment which will be provided by the instructors. Your team's classroom repository will be hosted as part of GeoMOER, our learning log space at GitHub for Marburg Open Educational Resources.

If not stated otherwise, the deadline for an assignment is the date and time of the next course session. The submissions generally encompass R or R markdown with compiled html files or presentations in PDF format.

To start with, get yourself a GitHub account if you have not one already and create your team's learning log using the link provided by the course lecturers. Be aware that once the learning log repository is created, you will stick to this until the end of the course.
{: .notice--info}

Aside from submitting assignments, you should use your repository for everything related to this course which is a potential subject to version control, team collaboration and issue tracking.
{: .notice--success}



## A note on assignments in education
Please remember that also this course uses assignments. Hence, our very strong suggestion is the following: First, try to solve each task at hand individually. Second, invite and involve colleagues and share your individual solutions. Help each other, leaf no one behind, discuss problems, pros and cons and rethink your solution which will be the one which is submitted and/or forms the basis for the next task in your problem solving workflow. In doing so you will get the maximum from this course because learning and training your skills is most effective in problem-based and peer-to-peer scenarios.


Please do not take any shortcuts here, just do it right and take as much from this course as you can.
{: .notice--success}

## Mandatory working environment
We value freedom of choice as an important good but giving our long-term experience freedom of choice comes to an end when we talk about the mandatory working environment for this course. The reason for this is simple: you work with team-based assignments and a piece of code written on the laptop of person A should run basically without any changes on the computer of person B. The situation gets nastier if you should test some code of a peer which is not part of your team or if the instructors would like to run your script on their own system. Hence, let's save everybody's time and focus on the things which are really important. Once the course is finished, feel free to use any working environment structure you like.

### Coping with different absolute paths across different computers
The biggest problem when it comes to cross-computer project path environments is not the project environment itself, i.e. the subfolders of your project *relative* to your project folder but the *absolute* path to your project folder. Imagine you agreed on a project folder called mpg-envinsys-plygrnd. On the laptop of person A, the absolute path to the root folder might be C:\Users\UserA\University\mpg-envinsys-plygrnd while on the external hard disk of person B it might be X:\university_courses\mpg-envinsys-plygrnd. If you want to read from your data subfolder you have to change the absolute directory path depending on which computer the script is running. Not good.

One solution to this problem is to agree on a common structure *relative* to your individual R home directory using symbolic links (Linux flavor systems) or junctions (Windows flavor systems).
{: .notice--success}

Example: Agree with your team mates on a top-level folder name which hosts all of your student projects. For example, this folder is called edu. Within edu, the project folder of this course is called mpg-envinsys-plygrnd. Create the edu anywhere you want, e.g. at D:\stuff\important\edu. Then create a symbolic link to this folder within your R home directory i.e. the directory where `path.expand("~")` points to.

To create this link on Windows flavor systems, start a command prompt window (e.g. press [Windows], type "CMD", press [Return]) and change the directory of the command prompt window to your R home directory which is C:\Users\your-user-name\Documents by default. Then use the `mklink \J` command to create the symbolic link. In summary and given the paths above:

```yaml
cd C:\Users\your-user-name\Documents
mklink /J edu D:\stuff\important\edu
```

On Linux flavor systems, the R home directory is your home directory by default, i.e. /home/your-user-name/. If you create your edu folder on /media/memory/interesting/edu, the symbolic link can be created using your bash environment:
```yaml
cd /home/<your-user-name>/
ln -s /media/memory/interesting/edu edu
```
Now one can access the edu folder on both the windows and the Linux example via the home directory, i.e. ~/edu/. All problems solved.


While this will work on all of your private computers, it will not work on the ones in the University's computer lab. To handle that as smooth as possible, you can use the functionality of the envimaR package which allows to set defaults for all computers but one special type which is handled differently. See [the example on setting up a working environment](https://geomoer.github.io/moer-mpg-gisfe-basics/unit00/unit00-10_environment_setup.html).
{: .notice--info}

### Mandatory folder structure


Your initial working environment should look like the following. It will grow over time based on additional information supplied within the individual assignments. 
```yaml
└── mpg-envinsys-plygrnd
    ├── data
    │   ├── aerial
    │   │   └── org
    │   ├── auxdata
    │   ├── data_mof
    │   ├── grass
    │   ├── lidar
    │   │   ├── level0
    │   │   ├── level1
    │   │   ├── level1
    │   │   │   └── normalize
    │   │   ├── level2
    │   │   └── org
    │   └── tmp
    ├── doc
    ├── log
    ├── run
    └── src
    ├── name_of_github_repository
    │   ├── doc
        └── src
 
```
The last folder will be the one you have checkout from your GitHub-hosted team learning log.

This is no guideline, this is a rule. Read it, learn it, live it and have a nice ride.  
{: .notice--danger}

Have a look at [the example on setting up a working environment]({{ site.baseurl }}/unit01/unit01-05_environment_setup.html).



