---
title: Using Git to track changes
draft: false
---

When working with many collaborators on the same project, coordination is essential.
For example, when writing a document with many people, it becomes essential to:
- Not overwrite each other's work;
- Know who modified which section of the document;
- If someone makes a bad change, return to a "good" version;
- See the history of the file that is being edited;

A tool that allows you to fulfill all these requirements is a *version control system* (VCS).
If you have ever used collaborative platforms like Google Documents, you will see that every one of these issues are being dealt with:
You can see what each other is doing, you can see what each editor has changed, you can restore a previous version and see all of them in a list.

Git is a *version control* tool that allows for collaboration, just like Google Documents.
Git is widely used by the community:
- It manages whole directories of files, instead of just one (like Google Documents);
- It allows for each collaborator to have a full copy of the files that are managed by Git;
- It works in an *asynchronous* manner, where every collaborator can simultaneously edit the same documents, with potential collisions resolved at a later stage;
- It allows for different, parallel versions of the same files to live side-to-side, so that changes may be tested out before being accepted;
- It allows everyone to collaborate on the same project, with "moderators" being able to approve or reject changes;

These features, its ease of use and its sheer popularity make Git the most widely used version control system (VCS) is the world.

An example of a project using Git is this very handbook: you can collaborate to it by using Git and proposing changes.
More on that below.

## What are versions?
Imagine you are writing a book, like a translation of the Iliad.
You begin with the first paragraph:
```
Goddess, sing the rage of Pelias’ son Achilles,

Destructive, how it gave the Achaeans endless pain

And send many brave souls of heroes to Hades—

And it made them food for the dogs
```
Now, to be sure you did a good job, you ask a friend to check on your work.
They come up with this new *version* of the same document:
```
Sing, o Muse, the rage of Pelias’ son Achilles,

Black and Murderous, how it gave the Achaeans endless pain

And send many brave souls of heroes into Hades dark—

And left their bodies to rot as feasts for dogs and birds
```
As you can see, your friend has made some changes from your own version:
```
[[ Goddess, sing ]] the rage of Pelias’ son Achilles,
[[ Sing, o Muse, ]] the rage of Pelias’ son Achilles,

[[     Destructive     ]], how it gave the Achaeans endless pain
[[ Black and Murderous ]], how it gave the Achaeans endless pain

And send many brave souls of heroes [[ to Hades— ]]
And send many brave souls of heroes [[ into Hades dark— ]]

[[ And it made them food for the dogs ]]
[[ And left their bodies to rot as feasts for dogs and birds ]]
```
Now, imagine that instead of the first paragraph, we are dealing with the whole first chapter, or the whole book.
How can you check your friend's changes?
How do you approve of some of them, but reject others?
How can you preserve both your changes and your friend's, so you can refer back to them if you ever need them?

Git does everything for you, and more.
Platforms built on Git, like GitHub or GitLab, leverage git to allow you and your friend to collaborate together.

> [!IMPORTANT]
> Stop reading here! This next section is a shorter, less complete version of the Pro Git book by Scott Chacon and Ben Straub, which is available online in its entirety at https://git-scm.com/book/en/v2.
> If you have the time, read the Pro Git book instead of this post.
> If you do not have the time to read the book, however, the rest of this post tries to give you a short hands-on tutorial on Git and Github.

## Installation
To follow along with this tutorial, [install Git](https://git-scm.com/downloads) for your operating system.
Git is a [command line tool](https://en.wikipedia.org/wiki/Command-line_interface), so you will need to use a terminal emulator to use it.
For Linux, you can use whatever emulator your distribution uses.
For MacOs, you can use the Terminal app.

> [!WARNING]
> If you install Git for Windows, you will have the option to install the "Git Bash" terminal.
> It's highly advised that you use that terminal emulator (and not Windows Powershell) to use Git on Windows, or at least when following the tutorial here.

If you have never used a terminal before, check out [the MacOS terminal guide from Apple](https://support.apple.com/guide/terminal/welcome/mac) or [this guide for the Terminal in Ubuntu](https://ubuntu.com/tutorials/command-line-for-beginners) if you are a Linux user.
It's strongly advised to read a bit about terminals before moving forward with the rest of this introduction.

### First run

> [!TIP]
> In this tutorial, commands starting with `> ` are commands that you type out,
> while lines starting with no symbol are the outputs of the commands that are run.
> Text in the triangular brackets `<>` is text you should replace with something else.
> For instance, `<your name here>` would be replaced by `Jhon Stewart` (if your name was Jhon Stewart).

Once Git is installed, you should be able to ask Git what its version is:
```bash
> git --version
git version 2.48.1
```
Your own version might be different.

Git needs to know something about you to work correctly.
In particular, it needs to know your **username**, your **email** and which text editor you'd like to use.
To configure Git, use the following commands:
```bash
> git config --global user.name "<your name here>"
> git config --global user.email "<your email here>"
> git config --global core.editor "<your editor here>"
```

When choosing an editor, it's recommended to use Nano, the simple terminal-based editor.
Read more about Nano [here](https://www.nano-editor.org/docs.php).
To set Nano as your editor, use `git config --global core.editor nano`.

> [!WARNING]
> If you are using Windows and want to use Nano to follow along, you will need to
> download and install it [here](https://www.nano-editor.org/download.php).
> After you do, close and re-open the Git Bash console.
> Linux and MacOS users will probably have Nano installed by default.
> 
> To check if you have installed nano correctly, run `nano --version`.
> You should see the version of the tool print out. If you get an error,
> then you did not install Nano correctly.

## Repositories
As we've said, Git manages a folder, containing any number of files and sub-folders.
This folder is called a *repository*.
Everything is Git revolves around a repository.

You can tell Git to start managing a folder with the `git init` command:

```bash
> mkdir git-tutorial
> cd git-tutorial
> git init
Initialized empty Git repository in /tmp/git-tutorial/.git/
```

You will see that Git has created a `.git` folder in the root of the repository.
It is this folder that marks this place as a Git repository.

You can check the status of the repository with:
```bash
> git status
On branch main

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```
We will learn what this message means in the following sections.

## Commits
Each recorded version of a repository is called a *commit*.
You have to explicitely tell Git to take a snapshot of the changes you have made to the file(s) in a repository with the `git commit` command.

First, let's add some files to the repository:
```bash
touch iliad.txt
nano iliad.txt
```

Inside Nano, type the initial paragraph of the Iliad (or copy-paste it) from the example above.

> [!NOTE]
> You need not use Nano: you can use any editor of your choice.

Once you're done, save and exit nano with CTRL+X, saying "Yes" to save the modified buffer and leaving the default `iliad.txt` filename.

You can check that everything went smootly by reading the contents of the file:
```bash
> cat iliad.txt
Goddess, sing the rage of Pelias’ son Achilles,
Destructive, how it gave the Achaeans endless pain
And send many brave souls of heroes to Hades—
And it made them food for the dogs
```

We are happy with this version.
To tell Git to preserve it, we can use the `git add` command:
```bash
> git add iliad.txt
```

The change to the repository ("The file `iliad.txt` was added") will be recorded and added to a list of changes called the "staging area".
You can add and remove as many changes as you'd like with `git add` and `git rm --cached <file>`, respectively.
You can check at any time what modifications there are and what modifications are in the staging area with the `git status` command:
```bash
> git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   iliad.txt
```

Once you are happy with what you modified, and you have moved to the staging area all those modifications you want to record, tell git to create a new commit (read: version):
```bash
> git commit
```
This will open your preferred editor (if you followed this guide, Git will have opened nano for you) to let you enter a *commit message*.
A commit message is a very short line that describes the changes you are committing.

Type in the first line of the file a commit message of your choice (I chose "Add new Iliad translation"), then save and quit.
Git will let you know that you successfully committed your changes:
```bash
[main (root-commit) 67b70d0] Add new Iliad translation
 1 file changed, 4 insertions(+)
 create mode 100644 iliad.txt
```

The commit summary is interesting: it states the commit message again, and also lets us know that this is the first commit ever of this repository (`root-commit`).
The alphanumeric string shown here, `67b70d0` is the commit's *hash*.
In reality, the *hash* of the commit is very long (you can find it out with `git rev-parse HEAD`), and it is used to uniquely identify that specific commit, and only that commit.
So, if you ever want to look at the files *as they were* when you ran this `git commit`, you can refer back to that specific hash.

Now, make a few more commits.
Edit the `iliad.txt` file and commit your changes by adding them to the staging area and committing them.
You can also create new files, new folders with other files, etc...

> [!TIP]
> You can use `git add .` to add *every change* in the folder you are currently in.
> If you are in the root folder of your repository (i.e. where the `.git` folder is),
> this essentially stages every change in your project.

Once you have made at least two extra commits, continue reading.

## Checking the commit history
Once you have a few commits, we can look at the history of the project.
Run the following command:
```bash
> git --no-pager log
commit 164564fb7354784ddab6f4eb90ed0eafcfb84767 (HEAD -> main)
Author: Luca Visentin <luca.visentin@unito.it>
Date:   Mon Feb 24 15:40:39 2025 +0100

    Create the author file with authorship information

commit 9f95d49d300964eb49ec525059678ba62285b578
Author: Luca Visentin <luca.visentin@unito.it>
Date:   Mon Feb 24 15:39:59 2025 +0100

    Edit Iliad translation

commit 67b70d0af9eba867f1d634243a12a96e4874af53
Author: Luca Visentin <luca.visentin@unito.it>
Date:   Mon Feb 24 15:29:58 2025 +0100

    Add new Iliad translation
```
This will show us the full commit history of our repository, complete with the hash values of each commit.

Notice that our last commit is marked as `HEAD -> main`.
The "Head" commit is the commit that is currently displayed in the repository: we are looking at the project "at this commit".
Currently, the Head commit is our latest commit: this is perfectly reasonable.

If you want to see what the repository looked like at a previous commit, you will need to switch to that commit.
Fortunately, the command is named just that:
```bash
> git switch 67b70d
Note: switching to '67b70d'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 67b70d0 Add new Iliad translation
```
Git warns you that you are not at the "tip" of the commit history: if you change files now, you will need to "branch out" the commit history.
Look around the repository (e.g. run `cat iliad.txt`): it is exactly as it were when you ran the first commit.

> [!IMPORTANT]
> The command you will need to use will have a different hash that the ones displayed here.
> This is because every commit hash is different, including between my and your repository.


To go back to the latest commit, use `git switch` with 

UNDER CONSTRUCTION ---
