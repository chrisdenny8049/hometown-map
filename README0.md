# Lesson 01: Setting up a Modern Mapping Environment and Workflow

## Table of Contents
<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Lesson 01: Setting up a Modern Mapping Environment and Workflow](#lesson-01-setting-up-a-modern-mapping-environment-and-workflow)
	- [Table of Contents](#table-of-contents)
	- [Overview](#overview)
	- [Installing and using the Atom text-editor](#installing-and-using-the-atom-text-editor)
	- [Using Git and GitHub](#using-git-and-github)
		- [Introduction: What is Git?](#introduction-what-is-git)
			- [A brief background to Git and history of version control](#a-brief-background-to-git-and-history-of-version-control)
		- [Setting up an (educational) account with GitHub](#setting-up-an-educational-account-with-github)
		- [Download GitHub for Mac/Windows and basic configuration](#download-github-for-macwindows-and-basic-configuration)
		- [Cloning down the weekly New Maps Plus assignment repository.](#cloning-down-the-weekly-new-maps-plus-assignment-repository)
		- [Making changes to your repository](#making-changes-to-your-repository)
			- [Editing existing files within a Git Repository](#editing-existing-files-within-a-git-repository)
			- [Adding files to a Git Repository](#adding-files-to-a-git-repository)
			- [Synchronizing local commits to the remote repository](#synchronizing-local-commits-to-the-remote-repository)
		- [How does Git work?](#how-does-git-work)
		- [Creating a new repository on your GitHub account.](#creating-a-new-repository-on-your-github-account)
	- [Your Git/GitHub workflow in map671](#your-gitgithub-workflow-in-map671)
	- [Definitions](#definitions)
	- [Video](#video)
	- [Additional Resources:](#additional-resources)

<!-- /TOC -->

## Overview

As almost all the software involved in a modern web mapping workflow involves textual files (data formats and coded scripts), the essential tools for a web mapper make handling these text files as easy as possible. In this lesson we will introduce two specific tools we'll be using throughout this course and beyond, and the process for using them.

**1. Atom** is a free and open-source text editor for working with code and design. It has many features that you’ll come to love such as:

* code syntax highlighting to make code more legible
* beautifying your code to make it more legible
* auto-complete for when you don’t want to type or remember that long variable name, and
* live server preview (so you can test your application or web page on your local machine to see how it will appear and behave when hosted on a remote server).

**2. Git**. Git is a software program and what's known as a "distributed version control system." It records changes to the various files in your project (a "repository" or "repo" for short) as you progress through your work. Using Git allows you to track different versions and, if (or when!) you mess up, go back to a previous version. Git also facilitates better collaboration on web projects.

This lesson will familiarize you with using these tools and establish a workflow we'll be using throughout the course to create maps and publish them to the web.

## Installing and using the Atom text-editor

Throughout the web mapping process, and this course, we'll be spending a lot of time writing code. We write the code in plain-text, and we can do this with any text editor. However, having a powerful text-editor such as Atom makes the process much easier and more enjoyable. Let's first get Atom installed on our machines.

Atom is a "A hackable text editor for the 21st Century." Download and install Atom for either Mac or Windows from the website: [https://atom.io/](https://atom.io/).

There are other good alternative text editors to Atom. Popular ones among web mappers and developers include [Sublime Text](http://www.sublimetext.com/), [Brackets](http://brackets.io/), and [VS Code](https://code.visualstudio.com/).

If you have any trouble getting Atom installed and launched, consult the [Atom Flight Manual](http://flight-manual.atom.io/), which you may want to read anyway. Get to know your tools!

Once you install it, feel free to open it up and play around:

* Check out all the [Atom Packages](http://flight-manual.atom.io/using-atom/sections/atom-packages/) you can install and use with Atom.
* Explore the different visual themes under [Atom Themes](http://flight-manual.atom.io/using-atom/sections/atom-packages/#atom-themes).

I highly recommend reading through the documentation in Chapter 2, [Using Atom](http://flight-manual.atom.io/using-atom/), and learning to use some of the many keyboard shortcuts.

One package you do want to install is [Atom Live Server](https://atom.io/packages/atom-live-server), which we'll discuss more below. Go ahead and do this now. In the file menu, got to **Packages -> Settings View -> Open** to open Atom's Settings. Atom is built using many packages, and within the Settings you can see the ones that come installed by default, as well as search for new ones to install and use. With the **Install** tab selected, search for the package using "live-server". You should see it pop up toward the top of the list. Go ahead and choose "Install".

![Installing the atom-live-server package](graphics/install-live-server.png)  
Figure 01. Installing the atom-live-server package

Before we start using Atom for our New Maps Plus mapping, we need to first get our Git process up and running.

## Using Git and GitHub

Git is a version control system (VCS) for tracking changes in computer files and coordinating work among multiple people. Within map671 we'll use Git to keep track of changes to our files and code, as well as to share and submit our work on the web with the instructor and other students. Within this module we're going to cover Git in both a conceptual and practical sense.

For more practice using Git, consider running through Codeacademy's [Learn Git](https://www.codecademy.com/learn/learn-git) (approximately 2 hours).

### Introduction: What is Git?

Git is a **Distributed Version Control System (DVCS)**. Okay, but what's a version control system (VCS)? A VCS records all changes made to a computer file or set of files. This allows you to review any changes made to the files under version control and allows previous versions of files or projects can be recalled at a later time. Basically, if you mess something up, accidentally delete or copy over a file, you can retrieve an earlier copy of that file.

We'll note now that there are two ways of installing and using Git on your computer system: 1.) with a desktop software client, and 2.) via command line (using the Command Prompt on Windows or the Terminal on a Mac).

**Recommended:** We're going to primarily be instructing this course with the first method using the [GitHub Desktop Client](https://desktop.GitHub.com/) because of the simplicity and ease of use. You might notice the website announces, "The new native." The software was recently updated and is significantly different that the previous version; a common theme we'll notice with open source software. Most importantly, this software installs the Git software on your system along with the client interface (so no need to do that step separately).

To use git outside of the GitHub Desktop client, you need to have experience with using shell or command line prompts. To use Git via command line, you need to first install Git on your machine ([Git for Windows Setup](https://git-scm.com/download/win) or [Installing on Mac](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git#Installing-on-Mac)), preferably so it's globally accessible (i.e., you can run a Git command from whatever directory you're in). Then, rather than using a software interface to use Git, you'll be issuing textual commands.

Additionally, one advantage of using the Atom text editor is its tight integration with Git and GitHub (the editor was actually written by GitHub). You can use the awesome [Git-Plus package](https://atom.io/packages/git-plus) to use Git with your development projects.

If you wish to pursue a more [advanced command line approach](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git), that's great! But understand that we're not explicitly teaching this method within the course and that the course instructor may not have the time to troubleshoot potential problems with you.

The process for connecting with GitHub is a little more complicated as well, so if you want to make life easier for the time being, just stick with the Desktop Client.

<a name="a-brief-background-to-git-and-history-of-version-control"></a>
#### A brief background to Git and history of version control

VCSs have been used for a long time. A very simple form of version control is simply making backups of your files or project directories and storing on a local computer or network system. Of course, this requires one keep careful track of files and file names, often manually. Developers use centralized Version Control Systems (CVCSs) to collaborate with others on projects, which used a single server and database to store files and keep track of all versioned files and changes. Examples of these CVCSs include Subversion and Perforce. While CSVSs were better than developers keeping their own versions of files on their local machines, this centralized approach also provides a single point of failure. If the server crashed (or even worse, became corrupted), the project was still at risk of being lost.

To address this risk, in recent years developers have migrated their workflow to Distributed Version Control Systems (DVCS) such as Git, Mercurial, Bazaar, and Darcs. The primary benefit of a DVCS is that rather than keeping a single backup of a project, every client who "clones" the project fully mirrors the entire repository. This approach "distributes" a full backup of project files among all local computers working on the project.

Git takes a particular approach to version control. Rather than making a fullback of the project with each version and storing a list of file-based changes like other VCSs, Git saves the state of the project as a "snapshot" of what the files look like at the time of commit (more on "committing" below). If a file has changed since the previous commit, then Git saves those changes and records a reference to it within a "snapshot." If a file hasn't changed, then there is no need to re-copy the file (or the entire project's directory structure!). Git retains the previously stored reference, making it very efficient compared with other VCSs.

Another advantage of Git is that repositories are always downloaded, stored, and manipulated locally  (i.e., no need for server requests), which means Git runs very fast, and you can work even without an Internet connection.

Today, another huge advantage of using Git is its close integration with [GitHub](https://github.com/). **GitHub** is a company that provides a Git-enabled platform to share your Git repositories. This is very powerful as it allows other people to collaborate with you on the same repository, and you can even share your projects with the broader public via open web pages. During the course, you will also use this mechanism to submit and share your assignments with your instructors.

### Setting up an (educational) account with GitHub

To get started with GitHub, you first need to create an account (actually, you'll have already created one to access this information, but here it is again).  

Navigate to [https://github.com/](https://github.com/) and sign up with a username, password and email address. **Make sure you use your @uky.edu address as you need it for the next step.** It also may be useful to use the same username you use for CARTO, Mapbox, and other online accounts, for consistency across your own personal branding.

Once you create your account, take a moment to update your profile (under **Your profile**) by clicking on the avatar upper-right corner. Uploading an image of yourself (or some other fun image) is nice, as well as giving your name, location, and a URL to a website if you have one.

GitHub is free to use but it also has paid plans. These paid plans offer the possibility of making repositories private instead of public. This is very helpful while we’re still learning as we may not want our stumbles and ugly code to be visible to the entire world. Later on, private repositories are when working for a client who wants to keep data and development private for the time being.

Fortunately, GitHub provides this service of private repositories free-of-charge to students! Once you’re signed-up, go to [GitHub Education](https://education.GitHub.com/) and click on the blue "Get the Pack" button. It includes access to GitHub private repositories as well as a bunch of other cool stuff.

![GitHub Education](graphics/github-education.png)  
Figure 02. GitHub Education

Sign in with your GitHub account (if you haven’t done so already), click "Request a Discount", and follow the instructions. GitHub will ask you to submit a request using your `@uky.edu` account. Once you’ve submitted, it may take a short while to get approved (3 - 5 days).

### Download GitHub for Mac/Windows and basic configuration

Now that we have our remote GitHub account set up on the web, let's get Git and the GitHub Client running on our local computer. Depending on your operating system, download the GitHub Desktop Client from [https://desktop.github.com/](https://desktop.github.com/).

Once downloaded and opened, GitHub Desktop will ask you to walk through some configuration steps. Enter your GitHub username and password, and then supply your name and email. Please use your real name so that your colleagues and instructors can identify you. This allows the Desktop Client application to pull down files from a remote repository, as well as to add, commit, and push changes to files up to a remote repository.

Once the configuration is successful, you should see an empty GitHub window. We’re finally ready to roll!

For further documentation on this process, see [Getting Started with GitHub Desktop](https://help.github.com/desktop/guides/).

Now that we have our GitHub account connected to the Desktop Client, we'll use it to complete two important processes for this week's module: 1.  Cloning a repository down to our local machine and 2. Creating a new repository on GitHub.

### Cloning down the weekly New Maps Plus assignment repository.

Each week a URL is provided in Canvas to the lesson and assignment hosted as repository on GitHub. When you click on this link, Github will copy this private repository into your account and add your username as a suffix to the repo name. Only you and the instructor have access to this repo.

First, clone the remote *map671-module-01-username* created for you for the assignment. With your GitHub Desktop application open, click on the main menu and find **File > Clone Repository...**. This presents you with a list of the remote GitHub repositories associated with your GitHub account(s) and username (you must be logged into GitHub).

Navigate to your repo or search for it within the **Filter** (if this is your first GitHub repository, then there will only be the one) and choose **map671-module-01-username**. You'll note that it is listed under the newmapsplus organization within Desktop Client.

**NOTE:** Throughout this lesson, when "username" is written you should substitute your own GitHub username.

![Cloning the weekly module repository in GitHub](graphics/02-clone-repo.png)  
Figure 03. Cloning the weekly module repository in GitHub

GitHub Desktop will then clone (i.e., make a copy of) the *map671-module-01-username* repository on your local machine. Select a location on your computer to save your repository. It doesn't matter where it is, as long as you remember where. As always when working on a computer, **stay organized and know where on your system your files/directories are**!

It would make sense to create one directory named something like *map671* and clone each weekly repo into that directory.  Create this directory, select that location and choose **Clone**.

After you click **Clone**, GitHub Desktop will copy the repository from the remote web server to your local machine. Once it's complete, you can verify the process by looking at the repository within your local file/directory structure (hint: you can right-click on any repo name within GitHub Desktop and choose **Open in Finder**).

![Opening the local repository directory through Finder](graphics/03-show-repo.png)  
Figure 04. Opening the local repository directory through Finder

When you open this repository in your file/directory structure, you'll see that the repository is contained within a directory named *map671-module-01-username*. Within this repo, you'll see the *README.md* file that is this lesson.

You may also see a (hidden) directory is named *.git* (if not you can enable your Operating System to view hidden files on your computer). The *.git* directory is used internally by Git to track your files and changes, and you will not directory use the files within this directory. Deleting it will delete the record of your repository. A Git repository also uses relative paths with respect to this *.git* directory, so you can easily move the entire *map671-module-01* directory to another location on your drive or another computer (or USB drive) and continue working with the files while Git tracks your changes!

Switch back to GitHub Desktop. Note that at the top of the window are two tabs: One says "No Uncommitted Changes." This indicates that you currently have no committed changes recorded by Git, and the panel below indicates "0 changes."

![No uncommitted changes in the repository](graphics/03.5-no-changes.png)  
Figure 05. No uncommitted changes in the repository

Next, click on the **History** tab. This will show you all the committed changes to your repository. Here we see there is the commit history of recent changes made to the repository.

![Viewing the commit history of the repository](graphics/04-initial-commit.png)  
Figure 06. Viewing the commit history of the repository

All further changes and commits will first happen within your local development environment and then pushed up to the remote copy of the repository. Let's practice doing that now.

But first, let's use the the atom-live-server to view the *lab-01/index.html* file in our web browser. You can open this file in your Atom text editor and examine the HTML, CSS, and JavaScript within it. Don't worry if it all looks like Greek right now; we'll be taking a closer look at these web standards over the following weeks.

Going to **Packages -> Live Server ->** in the file menu allows you to open the file using a web server (covered in lesson 02) through various ports on your computer (choose **Start on port 3000**). It generally doesn't matter which one you select. Note that there are also convenient keyboard shortcuts to do this as well.

Go ahead and launch the live server. You'll see the file/directory structure now within your web browser, and navigating to within the *lab-01/* The application should open the file within your web browser, and you should see a basic web map centered on Lexington.

![Index.html file served using atom-live-server package](graphics/05-live-server.png)  
Figure 07. Index.html file served using atom-live-server package

We'll be covering how this file makes the web map and page in subsequent modules. For now, let's make a few modifications to the file to better understand the Git process.

### Making changes to your repository

Launch your Atom text editor if not already open. Choose **File -> Add Project Folder**, and navigate to your local copy of the *map671-module-01-username* repository. **IMPORTANT:** throughout this course, it is best to **open the entire directory** of the repository or individual directories within it (e.g., a weekly*module-02* directory), rather that directly opening a single file. Doing so conveniently keeps the file/directory accessible to you within a text editor's file tree in the sidebar.

<a name="editing-existing-files-within-a-git-repository"></a>
#### Editing existing files within a Git Repository

Let's open the *lab-01/index.html* file within the Atom editor and make some basic changes to it. Make the following modifications to the file and **save your changes**.

On line 71, change the text to something other than "Awesome map!" here:

```html
<h1>Awesome map!</h1>
```

I'm going to change mine to this:

```html
<h1>Lexington, KY</h1>
```

**IMPORTANT:** Always remember to save your changes to your file in your text editor before looking for the result in the browser or GitHub Desktop.

After you save the changes, switch to your web browser. You can see your heading has been "live-updated" in the browser.

Now switch back to the GitHub Desktop. We can see at the top of the client that there is "**1 Uncommitted Change.**" Click on this tab. In the right-hand panel, you can see the previous text highlighted in red, and the new text highlighted in green. In Git-speak, this is called a "diff" — it shows the difference between two version of the same file. You have removed lines with a small "-" and have added those with a small "+." Green and red colors indicate key additions/removals.

![Seeing one uncommitted change in GitHub Desktop](graphics/06-make-change.png)  
Figure 08. Seeing one uncommitted change in GitHub Desktop

Next, let's commit this change to our repository. A commit bundles anything that has changed and creates a snapshot of the current state of the repository. Each commit then becomes an individual snapshot that you can access later.

Every commit to a repository requires a commit message. These messages should be descriptive of the changes you made to the files since the last commit. The convention is to use present tense verbs (i.e., "update map title" or "add GeoJSON file to project").

Within the GitHub Client, enter a commit message. You can also add a longer description of the commit (such as for commits that involve many changes to several files). When complete, hit **Commit to master**.

Note that we add this commit to the master branch (we'll talk more about branches and branching later on).

In this case I'll enter the commit message "update page h1 heading" and click **Commit to master**.

After clicking **Commit to master**, GitHub Desktop returns to show there are **"No Uncommitted Changes."** Clicking back to the **History** panel how displays the most recent commit message.

![History panel of GitHub Desktop showing the last two commits](graphics/07-commit-change.png)  
Figure 09. History panel of GitHub Desktop showing the last two commits

**Question:** How often should we commit our work to the repository? Commits are snapshots of a project that we can roll back to if a problem emerges. They also provide opportunities to comment on changes. Think about making commits when you've finished a particular task or made significant progress on a mapping process, or perhaps when you've reached a stopping place for the day. If you've puzzled through something difficult or coded a good solution, then go ahead and "save" this work with a commit. But there's no need to commit every new change to the script or file.

<a name="adding-files-to-a-git-repository"></a>
#### Adding files to a Git Repository

We just modified and saved a file and then committed that change to our repository. Now let's add a new file to our repository.

Choose **File -> New File** within Atom. Atom will open a new untitled document. Save this file within the *lab-01/* directory and name the file *reading-reaction.md*. Make sure the file is saved within your *map671-module-01-username/lab-01/* directory and not somewhere else in your filesystem, and that you include the *.md* file extension.

The extension *.md* stands for Markdown, which is a [text-to-HTML](https://daringfireball.net/projects/markdown/) conversion tool for writing content on the web. GitHub users store a lot of text information in Markdown, and at NMP we've written the lessons and laboratory assignments for you in Markdown as well. You'll be learning and practicing some Markdown as we go! Read more about Markdown in  [The Ultimate Guide to Markdown](https://blog.ghost.org/markdown/).

Within this *reading-reaction.md* file, copy and paste the following Markdown within the Atom text editor (include the pound sign as it creates a h1 heading in Markdown):

`# My reaction to How to Lie with Maps`

Save those changes to the *reading-reaction.md* file. Then switch back to your GitHub Desktop. Once again, you should see that there are changes to the repository, and GitHub Desktop shows these as uncommitted changes ("1 Uncommitted Change" here). On the left, GitHub DeskTop shows us on which file those changes occurred in (in this case, the *reading-reaction.md* file located within *lab-01/* directory).

![The index.html file added to the repository but not committed](graphics/08-add-new-file.png)  
Figure 10. The *index.html* file added to the repository but not committed

Again, we can add a commit message and then commit this change to the repository. Write a message such as "add markdown file for floating sheep" and click **Commit to master**. Once again, GitHub Desktop commits that addition to the project's repository and displays that there are now no uncommitted changes.

So far we've modified the *index.html* file and created a new *reading-reaction.md* file. We've safely stored these within our local Git repository. But, we haven't created a backup of these files. If our local machine became corrupted or lost, we'd lose this work. Let's now push these changes up to our remote GitHub account.

<a name="synchronizing-local-commits-to-the-remote-repository"></a>
#### Synchronizing local commits to the remote repository

GitHub Desktop recently had a **Sync** button at the top right, which offered a manual process to synchronize remote and local repos. The new Github Desktop (that you are likely using) replaces the sync process with a **Fetch** operation that works continuously in the background. A fetch will collect all of the remote changes and compare them to your local repository. Since you are the only one working in your repo you shouldn't expect any changes. The upside of fetch (versus the old sync) is that it keeps a repository synchronized across multiple computers.

To put a local commit on your remote repo, you need to **Push** the commit and Github Desktop will change the right-hand button from _Fetch origin_ to _Push_. If the button says _Pull_, then the remote repo was altered outside (and ahead) of your local repo and you need to pull in the changes to stay synchronized. Go ahead and push your changes to the remote.  

Now switch back to your assignment repository on the New Maps Plus GitHub site within your web browser. Refresh the page to see that your local changes are transferred (or "pushed") to the remote web server.

![Changes to the local repository have been pushed pushed to the remote](graphics/09-push-new-file.png)  
Figure 11. Changes to the local repository have been pushed to the remote.

You can see which files were changed and their associated commit messages. Behold, the transparency of GitHub!

Note that you don't need to push up changes every time you make a local commit, but more when you wish to backup the project on the remote web server.

For further reading, see [Contributing to Projects with GitHub Desktop](https://help.github.com/desktop/guides/contributing/)

Let's take a quick moment to conceptually review what Git's been doing with our files.

### How does Git work?

Files (such as your *index.html* file) reside in one of three states when working with Git: 1.) **modified** (the file has been updated but the changes are not recorded), 2.) **staged** (the changes have been added to the Git record), and 3.) **committed** (the changes have been safely stored in the Git database).

So, the basic workflow for working with Git is as follows:

1. modify your files in the working directory
2. stage the files
3. commit the files

As we saw above, GitHub Desktop masks a bit of the Git process, essentially staging the file(s) for the commit and making the commit in one step. If and when you begin using Git using the command line, there will be more steps involved for successfully using this process. For now, GitHub Desktop makes it simple to work locally, commit changes, and occasionally pushing these changes with the remote server.

### Creating a new repository on your GitHub account.

Now that we've figured out how to clone down the New Maps Plus course material from GitHub, let's make a quick simple web map using our personal GitHub accounts.

First create a new repository on the remote GitHub server through the web interface. Navigate to your GitHub account (e.g., *https://github.com/username*). Click on the small plus symbol upper-right and choose **New repository**.

![Creating a new repository in GitHub](graphics/10-new-repo-on-github.png)  
Figure 12. Creating a new repository in GitHub

On the next screen, complete the following steps:

* Create a new repository by typing *hometown-map* under the repository name (GitHub repository names may contain no spaces, so the hyphen is important). You don't need to use your hometown, but some town of your choosing and another descriptive name for the repository.
* Provide a brief description of the repository (e.g., "Lexington, KY" or "Git repo for my awesome mapping") where indicated.
* Leave the repository **Public** for now, unless you've been upgraded to the educational account, in which case you can mark it as **Private**.
* Check **Initialize this repository with a README** before clicking the green **Create repository** (it's a good idea to always do this when creating a new repository).
* Finally, **Add a license** for your repository. While private repositories will keep your code hidden while you develop it, a license will instruct people on how they can use your published content. A repository without a license is considered a closed repo with no rights granted to other users. We suggest adding an open license to the work you want to share and get promoted online. Learn more about [licensing a repository](https://help.github.com/articles/licensing-a-repository).

![Creating a new repository in GitHub](graphics/11-new-repo-on-github.png)  
Figure 13. Creating a new repository in GitHub

Congratulations! You've created a repository on your GitHub account, currently stored on the GitHub web server. Right now, the only file within your repository is a file named *README.md*. The the GitHub web interface displays the contents of the *README.md* file by default, therefore this file is often used as a textual interface to the project. A *README.md*. file commonly accompanies every new repository to tell users about it.

![Creating a new repository in GitHub](graphics/12-new-repo-on-github.png)  
Figure 14. Creating a new repository in GitHub

You can clone this repository to your local machine as well, the same way we did above with the module-01 repo. Within your GitHub Desktop application choose **Clone** and this time select your newly created repository. Note that this one will be found under your personal GitHub user account, and not **newmapsplus**.

You'll likely want to save this repo in another directory than your **map671/** directory (or where you'll be saving each weekly module repo from newmapsplus). You may end up creating many repositories with your GitHub account, and it may be useful to keep them organized within a single directory on your machine.

Once I do this, I can see that, like the other freshly-cloned repository, this one has "No Uncommitted Changes", and I can view a simple History with only the initial commit.

![A new repository cloned down from my personal account on GitHub](graphics/13-initial-commit.png)  
Figure 15. A new repository cloned down from my personal account on GitHub

Within the GitHub Desktop client, we can switch back and forth between our repositories to see the current state of tracking and changing commits. The important thing is to **keep these repositories organized on your filesystem and distinct in your understanding**. They are different directories with different files. Know which ones you are editing within your Atom text editor, and which you are committing to and synchronizing.

Before we wrap up, let's practice the Git add/commit/push process one more time. Within your filesystem GUI (i.e., either Windows or Finder) copy the *index.html* file we edited earlier from the *map671-module-01-username/lab-01/* directory on your local system and paste a copy of this file into your personal repository you just created (e.g., "hometown-map").

Once you do this, you should see the uncommitted change for the "hometown-map" repository shown within GitHub Desktop application.

![1 Uncommitted Change to an index.html file within the hometown-map repo](graphics/14-push-commit.png)  
Figure 16. 1 Uncommitted Change to an index.html file within the hometown-map repo

Go ahead and write a commit message (e.g., "add index file") and choose **Commit to master** to commit it to the master branch of the Git repo. Then push these changes to your remote repository.

Next, go to your remote repository on GitHub to examine the recently pushed changes. Note that if successful you can see the *index.html* file within the repository at *https://github.com/username/hometown-map*. Here you can click on the file and see all the HTML, CSS, and JavaScript as before in your local text editor.

But how do we get the map to be rendered from this remote repository so we can see the map and not just the code, like we did locally with the atom-live-server? The answer is [GitHub Pages](https://help.github.com/articles/user-organization-and-project-pages/).

Within the **Settings** of your repository on the GitHub website, change the **Source** to "master branch" and choose **Save**.

![Using the master branch of a repository for GitHub Pages](graphics/source-master-branch-pages.png)  
Figure 17. Using the master branch of a repository for GitHub Pages

This setting tells GitHub to "serve" or "render" the files in your repository from a web server. How do you access them? You navigate your web browser to *https://username.github.io/repository-name*. If everything is working correctly, you should see your simple web map page "served" correctly to the browser. The difference between this and the earlier process using the atom-live-server is that you can share this URL (and your map) with the world, rather than only viewing on your personal machine.

The final step in our instructional flow is to add a Contributor to your *hometown-map* repository. On your remote GitHub repo **Settings** tab find the **Collaborators & teams** section. Add "boydx" as a collaborator. This will allow the instructor to add commits and see your private repository code.

## Your Git/GitHub workflow in map671

We're hosting the content for each module of map671 course on the New Maps Plus GitHub account within its own repository. Each week you'll begin by cloning down the repo using the URL provided in the week's Canvas Module. Then, edit the files on your local machine, committing changes as you go. Occasionally you'll be asked to create a repository on your personal account and add files there.

When ready to submit each weekly assignment, push up any recent commits to the remote repository and paste the URL in the Canvas Assignment so the instructor knows you've submitted. Remember that late assignments incur a 10% reduction per day, unless excused with the instructor beforehand.

You can read the content for lessons and labs, written within Markdown files (i.e., files with a *.md* extension), within the text editor (there's an extension you can search for and install under the **extension manager**). However, one nice thing about the "GitHub flavored" Markdown we've used to write content is the support for code syntax highlighting when viewed directly from GitHub itself. And all the hyperlinks work within the web page. So we recommend simply logging into GitHub and reading the lessons from the web page itself.


## Definitions
* **Git**: A (distributed) version control system that allows you to manage (and revert) changes to (text) files.
* **GitHub.com**: An online platform, built on top of Git, that allows for online collaborating and sharing of Git repositories
* **GitHub Desktop**: A program that allows for the management of Git repositories through a graphical user interface (instead of command line)
* **Repository**: A directory containing all of a project’s files, managed by the Git workflow
* **Commit**: A specific snapshot of a project’s files
* **Revert**: Undoing one (or more) commit, basically returning back to a previously saved version of a project
* **Clone**: A copy of a remote repository to a local machine
* **Fork**: A carbon-copy clone of another person’s remote repository to one that’s owned by yourself
* **Remote repository**: A Git repository that exists on a remote server, most often the GitHub.com platform
* **Branch**: A specific *context* of a repository. Often used to work on a specific feature or new idea
* **Merge**: Branches can be merged back into the main branch. This brings all the commits made on a specific branch into the main context of the project. E.g. if a certain feature proves useful it can be added to the main project at that time.

## Video

![Instructional video](graphics/q00.png)

Each lesson has an instructional video that you can access through Canvas. This lesson's video walks you through setting up your workflow. 

## Additional Resources:

* [Set Up Git](https://help.github.com/articles/set-up-git/)
* [Create a Repo](https://help.github.com/articles/create-a-repo/)
* [For A Repo](https://help.github.com/articles/fork-a-repo)
* [Be Social](https://help.github.com/articles/be-social)
