---
layout: default
title: 0x000 - Binary Decoder
parent: Assignments
nav_order: 1
has_children: false
has_toc: true
permalink: /assignments/0x000-binary-decoder
---

# 0x000 - Binary Decoder

**Due at 11:59pm on September 22, 2022**

Binary file decoders are historically a great source of computer security vulnerabilities.
Decoders fall into a perfect storm as they:
* are often written in low-level programming languages,
* have to manage many edge cases and failure modes inherent to the format, and
* have to accept untrusted user input.

To experience the challenges of implementing a decoder first hand, you are going to write one!
In this assignment, you'll use C to implement a decoder for the QOI image format.
The goal here isn't to write an absolutely perfect decoder with no bugs or vulnerabilities.
In fact, you'll actually have more fun in Lab 0x001 (zero-indexed) if your decoder has some problems (more on that later).
For this assignment, you'll only be evaluated on:
* Can you open the provided benchmark images? Read more [here](https://github.com/eced4406/qoi-starter-project#benchmark).
* Is your code well organized, documented, and readable?

One important learning outcome for this course is getting exposure to modern tools that will help you be productive while writing secure software or firmware.
I've provided a starter project for you to use [here](https://github.com/eced4406/qoi-starter-project).
Please follow the instructions on the project's README to get started.
It is important that you use this starter project as a subsequent lab will build on it.
I also expect you to submit your assignment as a patch against the starter project.
I'll provide instructions on how to use Git to achieve this closer to the assignment due date.

You can find the specification for the QOI image format [here](https://qoiformat.org/qoi-specification.pdf).
You'll of course be able to find implementations of the QOI decoder online.
You won't get much out of this assignment if you just copy one.
If you're stuck, lean on your classmates for ideas, or post a message in our discussion board.
Please submit your own work.

## Grading

This assignment will be graded out of 10 points.
* Automated benchmark assessment (7 points)
  * `0.qoi`: `QOI_OP_RGB` and `QOI_OP_RGBA` (2 points)
  * `1.qoi`: `QOI_OP_RUN` (2 points)
  * `2.qoi`: `QOI_OP_INDEX` (2 point)
  * `3.qoi`: `QOI_OP_DIFF` and `QOI_OP_LUMA` (1 point)
* Code quality (3 points)
  * Is your code easy to read?
  * Is your code well-organized?

Code "quality" is somewhat subjective.
Here is a non-exhaustive list of some common code quality issues for which I might dock you points:
* Using "magic" constants. Prefer named macros or `const` variables to help readers understand where your constants are coming from. 
* Using global, mutable state. Global variables can make your program difficult to follow. When a function modifies a global variable, it means there are side-effects that you need to keep track of. Prefer passing any state your function needs into the function directly via an argument. This also makes testing easier!
* No documentation / bad naming. Make it easy for readers of your code to understand what is going on. Think carefully about how you name your variables and functions such that they convey what your program is doing. If you've given your symbols good names and it still not obvious what is going on, add a comment to explain it.

## Submitting Your Assignment

Submit your assignment electronically through Brightspace.
Use git to generate a patch file containing all the differences between your completed assignment and the project template.

```
$ cd path/to/your/project/repo # substitute with your path
$ git checkout assignment # substitute with whatever you named your branch
$ git diff main > B00XXXXXX.patch # substitute with your Dal banner number
```

This will generate a patch file in your current directory.
This is the file that you'll submit on Brightspace.
You can open it with a text editor to manually inspect it.
In the comments section of your Brightspace submission, tell me what environment you used when working on your assignment (e.g. Windows + WSL, Windows, MacOS, Linux, etc.).
Also, paste the output of the `qoi_benchmark` program when you run it against your decoder.

If you want, you can simulate what I'll do when marking your assignment.

```
$ cd somewhere/else/on/your/computer
$ git clone --recurse-submodules https://github.com/eced4406/qoi-starter-project.git submission-test
$ cd submission-test
$ git checkout -b B00XXXXXX # substitute with your banner number
$ git apply path/to/your/B00XXXXXX.patch
$ code . # open it up in VS Code to check it over
```

## Helpful Links

* [git - the simple guide](https://rogerdudler.github.io/git-guide/)
* [qoi - lossless image compression in O(n) time](https://phoboslab.org/log/2021/11/qoi-fast-lossless-image-compression)

## Frequently Asked Questions

*I'm on Windows and I'm having trouble getting a Linux environment up and running. What should I do?*

I'd recommend just doing this assignment on Windows if you're not able to quickly get into a Linux environment.
I don't want you wasting too much time on the environment and not having time to finish the assignment.

We can worry about the Linux environment for the labs later.
Also, you're going to be working in groups for the labs, so really only one person in your group needs the environment set up.
I'm working with Jordan Wright to get a virtualbox environment working on the lab computers.

*I'm on Mac. I installed all the required tools with Homebrew, but I'm getting an error related to an old CMake version. Help!*

If you install/upgrade CMake with Homebrew as per the instructions, you should have the latest and greatest CMake installed.
The problem is that there is another one on your system that is taking priority.
It's likely you have CMake installed via MacPorts from a previous course.
Depending on which shell you're using, you probably have a line in your `~/.profile` or `~/.zprofile` file adding some MacPort path to the front of your `PATH` environment variable.
To resolve this, just add the Homebrew install path to the front of the list.
This will ensure that things installed via Homebrew will have priority (this is fine as long as you aren't using MacPorts for some other course this semester).

Before:
```
export PATH=/opt/local/bin:/opt/local/sbin:$PATH
```

After (Intel Macs):
```
export PATH=/usr/local/bin:/opt/local/bin:/opt/local/sbin:$PATH
```

After (Apple Silicon Macs - M1/M2):
```
export PATH=/opt/homebrew/bin:/opt/local/bin:/opt/local/sbin:$PATH
```

*I'm on Windows and I'm trying to get WSL2 working. I followed the instructions for Linux. Everything builds, but when I go to run the viewer, nothing shows up (or I get an error re. SDL2 not being able to initialize). What should I do?*

First, see the top question about getting stuck setting up a Linux environment.
If you still want to continue down this path, check your version of Windows.
WSL2 has GUI support baked in if you're using a new enough version of Windows.
See this [blog](https://docs.microsoft.com/en-us/windows/wsl/tutorials/gui-apps) and this [repo](https://github.com/microsoft/wslg#welcome-to-wslg) for more info.

If you can't upgrade to the latest build of Windows/WSL2, you might still be able to get it working by running your own X server.
See Seamus's comment [here](https://teams.microsoft.com/l/message/19:03a0c5adf1f54a999863929653d403ad@thread.tacv2/1662602214031?tenantId=60b81999-0b7f-412d-92a3-e17d8ae9e3e0&groupId=4e08a2f1-1d09-4402-ba36-20b67bd3bdfb&parentMessageId=1662572367248&teamName=ECED%204406%20-%20Computer%20Security&channelName=Assignment%20Help&createdTime=1662602214031&allowXTenantAccess=false).

I have updated the Linux instructions to install several required X development libraries.
Please make sure to install them before trying to configure your CMake project.
See [this thread](https://teams.microsoft.com/l/message/19:03a0c5adf1f54a999863929653d403ad@thread.tacv2/1662741324732?tenantId=60b81999-0b7f-412d-92a3-e17d8ae9e3e0&groupId=4e08a2f1-1d09-4402-ba36-20b67bd3bdfb&parentMessageId=1662741324732&teamName=ECED%204406%20-%20Computer%20Security&channelName=Assignment%20Help&createdTime=1662741324732&allowXTenantAccess=false) in our `#Assignment Help` channel.

*I can build the application, but when I go to run it, the window doesn't open.*

The qoi_viewer application takes one command line argument: the path to the .qoi file to open.
If you just run the application without specifying the path, all you'll see is a help message about how to run the program.

When running from the command line, just add the path (absolute or relative to your current working directory) of a qio file to the end of your command:

```
$ cd build/out/bin # You might have to add Debug or Release to the end on Windows
$ ./qoi_viewer /path/to/your/repo/data/dice.qoi # remember to substitute this path with the real one!
```

This is great for a quick test, but you probably want to set up VS Code to build and run the application without having to go to the command line.
* Open up the "Run and Debug" menu on the left hand sidebar.
* Click "create a launch.json file", and then click "Add Configuration".
* Pick the "C/C++: Launch" option (the exact text may different depending on your platform).
* Update the "program" field to point to `"${command:cmake.launchTargetPath}"`.
* Add the path to the QOI file you want to open to the "arguments" list.
* Save the file.
* From the Command Palette, run "CMake: Set Debug Target" and select "qoi_viewer". Now you can launch the viewer by typing F5 or by hitting the green play button at the top of the "Run and Debug" sidebar tab.

You can read more about debugging C/C++ projects with VS Code here:
* https://code.visualstudio.com/docs/cpp/cpp-debug
* https://vector-of-bool.github.io/docs/vscode-cmake-tools/debugging.html
