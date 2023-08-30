<p align = "center" draggable=”false” ><img src="https://github.com/AI-Maker-Space/LLM-Dev-101/assets/37101144/d1343317-fa2f-41e1-8af1-1dbb18399719" 
     width="200px"
     height="auto"/>
</p>


## <h1 align="center" id="heading">:wave: Welcome to Software Development for LLMOps 101!!</h1>

Welcome to the beginning of your journey to becoming an LLM Operations (LLMOps) Engineer! 🎉 Follow these steps to get your development environment teed up! After you've finished this set-up, feel free to go through the associated `Whodunit?`! 🕵️‍♀️

![ai_kadhim_setting_up_developers_environment_873c1f1c-1fdb-4cbd-997c-b0479554b8d0](https://github.com/AI-Maker-Space/LLMOps-Dev-101/assets/37101144/b0f4e041-33a9-407f-bc9d-5aabd626652a)


## :books: Quick Review
We will be using some terminal commands, so let's make sure you know what they are and what they do! 

| Command      | Stands For |  Description |
| ----------- | ----------- | -------------|
| `ls`      | long listing       | lists all files and directories in the present working directory |
| `ls -a`  | long listing all   |  lists hidden files as well |
| `cd {dirname}`      | change directory       | to change to a particular directory |
| `cd ~`   | change directory home        | navigate to HOME directory |
| `cd ..`      | change directory up       | move one level up |
| `cat {filename}`   | concatenate        | displays the file content |
| `sudo`      | superuser       | allows regular users to run programs with the security privileges of the superuser or root |
| `mv {filename} {newfilename}`   | move        | renames the file to new filename |
| `clear`      | clear       | clears the terminal screen |
| `mkdir {dirname}`   | make directory        | create new directory in present working directory or at specified path |
| `rm {filename}`   | remove        | remove file with given filename |
| `touch {filename}.{ext}`   | touch        | create new empty file |
| `rmdir {dirname}`   | remove directory        | deletes a directory |
| `ssh {username}@{ip-address} or {hostname}`   | secure shell        | login into a remote Linux machine using SSH |

<p></p>

## :hammer_and_wrench: Tools We'll Be Using
We will also be using a few tools such as `git`, `conda`, and `pip`.
<details>
<summary>Git</summary>

Git is a free and open source distributed version control system designed to handle everything from small to very large projects. These are the commands we will be using with `git`:

`git clone` -> clone a remote repository to your local computer

`git add` -> add files to a commit

`git commit -m {message}` -> commit changes with a message

`git push` -> push commit to remote repository
</details>

<details>
<summary>Conda & Pip</summary>

Conda is an open-source, cross-platform, language-agnostic package manager and environment management system. We will use `pip` within `conda` environments to manage our package installations. `pip` is Python's package management system. `conda` comes with Anaconda. And Anaconda is a convenient way to set up your Python programming environment since it comes with an enviornment management tool (`conda`) and comes with extra packages that are commonly used in data science and ML.

Some commands we will use in this lesson when it comes to `conda` and `pip`:

`conda create --name llmops-course python=3.11 pip` -> This creates a virtual environment. A virtual environment is a Python environment such that the Python interpreter, libraries, amnd scripts installed into it are isolated from those installed on other environments and any libraries installed on the system. So basically, this allows you to keep all your project's code/dependencies/libraries separated from other projects. You are specifically saying to create said environment with the name `llmops-course`, use `python` version 3.8, and use `pip` as your package manager. The command `conda` invokes the underlying logic to actually make the virtual environment and manages said environments for you.

`conda activate llmops-course` -> This activates the virtual environment you made with the above command for your current terminal session.

`pip install numpy pandas matplotlib jupyter` -> This installs the four packages mentioned - `numpy`, `pandas`, `jupyter` and `matplotlib`. `numpy` is used for scientific computing, `pandas` is used for data analysis, and `matplotlib` is used for data graphics. `jupyter` is discussed later in this tutorial in depth! `pip` is the Python package manager and you are telling it to `install` the listed packages to your environment.

`pip install openai` -> This installs the OpenAI packages so you can access the OpenAI API using your API Key. We recommend your run through our [OpenAI Notebook](https://colab.research.google.com/drive/16Y67VozkGVErtrF3WQArpM52AOk5pBGu?usp=sharing#scrollTo=3qCKaH6vD-jZ) to learn how to utilize the OpenAI API.
</details>

<p></p>

## :rocket: Let's Get Started! 
Let's start off by setting up our environment!  Review the environment setup instructions for the local environment that you'll be using in this course.
<details>
  <summary>Windows</summary>


* Install [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install) using Powershell

```powershell
wsl --install
```
* Install [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab) (You can even make it your [default!](https://devblogs.microsoft.com/commandline/
windows-terminal-as-your-default-command-line-experience/))

* Install [Ubuntu](https://www.microsoft.com/en-us/p/ubuntu/9pdxgncfsczv?activetab=pivot:overviewtab)

* Make sure you've install the correct version with the command `wsl -l -v`
    
(If you find yourself getting stuck on the WSL2 install, [here](https://www.youtube.com/watch?v=VMZH9Pj2dXw&ab_channel=StefanRows) is a link to video instructions)

Give it a test drive! 

![WindowsTerminal](https://user-images.githubusercontent.com/72572922/160048214-37f08855-8b29-4c13-9d25-e0f69806f752.jpg)

Continue by installing the following tools using [Windows Terminal](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab) to setup your environment. When prompted, make sure to add `conda` to `init`.

| Tool | Purpose | Command                                                                                           |
| :-------- | :-------- | :------------------------------------------------------------------------------------------------ |
| :snake: **Anaconda**  | Python & ML Toolkits | `wget https://repo.anaconda.com/archive/Anaconda3-2021.11-Linux-x86_64.sh` <br> `bash Anaconda3-2021.11-Linux-x86_64.sh` <br> `source ~/.bashrc` |
| :octocat: **Git**  | Version Control | `sudo apt update && sudo apt upgrade` <br> `sudo apt install git-all`   |
| :memo: **VS Code** | Development Environment | [Download](https://code.visualstudio.com/download) |

</details>

<details>
  <summary>Linux (Debian/Ubuntu)</summary>

Open terminal using <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>T</kbd>. Enter the following commands in terminal to setup your environment. When prompted, make sure to add `conda` to `init`.
| Tool | Purpose | Command                                                                                           |
| :-------- | :-------- | :------------------------------------------------------------------------------------------------ |
| :snake: **Anaconda**  | Python & ML Toolkits | `wget https://repo.anaconda.com/archive/Anaconda3-2021.11-Linux-x86_64.sh` <br> `bash Anaconda3-2021.11-Linux-x86_64.sh` <br> `source ~/.bashrc` |
| :octocat: **Git**  | Version Control | `sudo apt update && sudo apt upgrade` <br> `sudo apt install git-all`   |
| :memo: **VS Code** | Development Environment | [Download](https://code.visualstudio.com/download) |

</details>

<details>
  <summary>macOS Intel</summary>

To get started, we need to download the MacOS package manager, <strong>Homebrew</strong> :beer:, so that we can download the tools we'll be using in the course. If you don't already have Homebrew installed, run the following commands:

1. Open terminal using <kbd>⌘</kbd>+<kbd>Space</kbd> and type `terminal`.

2. Install Homebrew using the command below, following the command prompts:

    `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"` 

3. Update Homebrew (This may take a few minutes)

    `git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core fetch --unshallow`

    `git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-cask fetch`
     
4. Install the `wget` command to continue following along
     `brew install wget`

Enter the following commands in terminal to setup your environment. When prompted, make sure to add `conda` to `init`.

| Tool | Purpose | Command                                                                                           |
| :-------- | :-------- | :------------------------------------------------------------------------------------------------ |
| :snake: **Anaconda**  | Python & ML Toolkits | `wget https://repo.anaconda.com/archive/Anaconda3-2021.11-MacOSX-x86_64.sh` <br> `bash Anaconda3-2021.11-MacOSX-x86_64.sh` <br> `source ~/.bashrc` |
| :octocat: **Git**  | Version Control | `brew install git`   |
| :memo: **VS Code** | Development Environment | [Download](https://code.visualstudio.com/download) |

</details>

<details>
  <summary>macOS ARM</summary><br>

To leverage the Mx chip from Python, you must use a special Python distribution called [Miniforge](https://github.com/conda-forge/miniforge). 
Open terminal using <kbd>⌘</kbd>+<kbd>Space</kbd> and type `terminal`. Enter the following commands in terminal to setup your environment.

Miniforge can be installed using Homebrew or from the source. We suggest trying Homebrew option first.

### Option 1 Homebrew

To get started, we need to download the MacOS package manager, <strong>Homebrew</strong> :beer:, so that we can download the tools we'll be using in the course. If you don't already have Homebrew installed, run the following commands:

1. Open terminal using <kbd>⌘</kbd>+<kbd>Space</kbd> and type `terminal`.

2. Install Homebrew using the command below, following the command prompts:

    `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"` 

3. Update Homebrew (This may take a few minutes)

    `git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core fetch --unshallow`

    `git -C /usr/local/Homebrew/Library/Taps/homebrew/homebrew-cask fetch`
     
4. Install the `wget` command to continue following along
     `brew install wget`

5. Install the `xcode-select` command-line utilities by typing the following command in the terminal

    `xcode-select --install`

After running the commands from the table, when prompted, initiate your conda base environment by running `conda init`.
| Tool | Purpose | Command                                                                                           |
| :-------- | :-------- | :------------------------------------------------------------------------------------------------ |
| :snake: **Miniforge**  | Python & ML Toolkits | `brew install miniforge` |
| :octocat: **Git**  | Version Control | `sudo apt update && sudo apt upgrade` <br> `sudo apt install git-all`   |
| :memo: **VS Code** | Development Environment | [Download](https://code.visualstudio.com/download) |

</details>


<p></p>


## <img src="https://upload.wikimedia.org/wikipedia/commons/f/f3/Visual_Studio_Code_0.10.1_icon.png" height=40px/> Let's configure our VS Code environment!

<details>
  <summary>Install the IntelliCode Extension</summary>

  IntelliCode is an AI-powered code completion extension to boost coding productivity. :sunglasses:

  1. Click the `Extensions` <img src="https://github.com/AI-Maker-Space/LLMOps-Dev-101/assets/37101144/f17d8f45-f174-4b9b-be92-8f1e85d8a77b" width=30px/> tab in the navigation panel on the left side of VS Code. 

  2. Type "IntelliCode" in the search bar.

  3. Click `install` <img src="https://github.com/AI-Maker-Space/LLMOps-Dev-101/assets/37101144/4c06f2a7-d7c3-4c59-b656-82170518cbeb" width=30px/> on the <ins><strong>Microsoft IntelliCode Extension</strong></ins>

</details>

<details>
  <summary>Install the Python and Jupyter Notebook Extensions</summary>

  1. Click the `Extensions` <img src="https://github.com/AI-Maker-Space/LLMOps-Dev-101/assets/37101144/f17d8f45-f174-4b9b-be92-8f1e85d8a77b" width=30px/> tab on the left side of the window.

  2. Type "Python" in the search bar.

  3. Click `Install` <img src="https://github.com/AI-Maker-Space/LLMOps-Dev-101/assets/37101144/4c06f2a7-d7c3-4c59-b656-82170518cbeb" width=30px/>  on both the <ins><strong>Python Extension</strong></ins> and on the <ins><strong>Microsoft Jupyter Notebook Extension</strong></ins>

</details>

<details>
  <summary>Set the Python Interpreter</summary>

  1. Open VS Code and click on `New File...`

  2. Open the Command Pallette 
    <strong>(Mac: </strong></ins> <kbd>Shift</kbd><kbd>⌘</kbd>+<kbd>P</kbd> 
    ,<strong> Windows: </strong></ins> <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>)

  3. Type "Python" in the search bar.

  4. Click on `New Python File`

  5. Open the Command Pallette again.  Can you remember the shortcut?  If    not, see #2 above again.

  6. Type "Python Interpreter".

  7. Click on `Python: Select Interpreter`

  8. Select the `Conda` environment that you installed earlier. 
  
  <p align = "center" draggable=”false”>
  <img src="https://github.com/AI-Maker-Space/LLMOps-Dev-101/assets/37101144/d95ff119-2c97-4bf8-9133-1bf167f61f6e"> 
  </p>

  9. Now you're ready to start coding!

</details>

<p> </p>

## <img src="https://octodex.github.com/images/original.png" width=40px/> Let's Make Sure That GitHub is Ready to Roll!

If you don't already have one, make an account on [Github](https://github.com/)!  

<details>
  <summary>Github SSH Setup</summary>
  Secure Shell Protocol (SSH) provides a secure communication channel of an unsecured network.  Let's set it up!
  
  <p></p>

  1. Generate a Private/Public SSH Key Pair.
    
  ```console
  ssh-keygen -o -t rsa -C "your email address for github"
  ```

  2. Save file pair.  Default location `~/.ssh/id_rsa` is fine! 
  

  3. At the prompt, type in a secure passphrase.
  4. Copy the contents of the public key that we will share with GitHub. 

     * Mac: `pbcopy < ~/.ssh/id_rsa.pub` 

     * Windows (WSL): `clip.exe < ~/.ssh/id_rsa.pub`

     * Linux: `xclip -sel c < ~/.ssh/id_rsa.pub`
  
  5. Go to your GitHub account and go to `Settings`. 
  
  6. Under `Access`, click on the `SSH and GPG keys` tab on the left.

  ![image](https://github.com/AI-Maker-Space/LLMOps-Dev-101/assets/37101144/5fb54f16-7279-49c4-bda3-2da36cbbc306)


  7. Click on the `New SSH Key` button.
  
  ![image](https://github.com/AI-Maker-Space/LLMOps-Dev-101/assets/37101144/d5551c28-9d70-438c-b45d-43698384e3ff)

  
  8. Name the key, and paste the public key that you copied. Click the `Add SSH Key` button
  

  ![image](https://github.com/AI-Maker-Space/LLMOps-Dev-101/assets/37101144/8f7c4496-0e88-4058-9baf-73495322db8b)


</details>

<details>
  <summary>Viewing the Repositories</summary>

Login and click on the top right user icon, then go to `Your repositories`. 

<p align="center">
  <img width="648" alt="image" src="https://github.com/AI-Maker-Space/LLMOps-Dev-101/assets/37101144/18b766c6-ca91-4926-ad79-5fc101c3e6a0">
</p>
</details>


<details>
  <summary>Creating a New Repository</summary>

When viewing the respository page, click on `New` and proceed to create your repo.


<p align="center">
  <img width="335" alt="image" src="https://github.com/AI-Maker-Space/LLMOps-Dev-101/assets/37101144/dba31b88-0058-499c-a891-349de2d35279">
</p>
<hr>

**Filling Respository Details**

Create the repository by inputting the following:
* `Repo name`
* `Repo description`
* Make repo `public`
* Add a `README`
* Add `.gitignore` (Python template)
* Add `license` (choose MIT)

Then click `Create Repository`.

<p align="center">
  <img width="724" alt="image" src="https://github.com/AI-Maker-Space/LLMOps-Dev-101/assets/37101144/c20a19c1-548e-4576-b4b2-1d2ca99deae7">
</p>

</details>

<details>

<summary>Clone Your Repo</summary>

  1. Open your terminal and navigate to a place where you would like to make a directory to hold all your files for this class using the command `cd`. 


  ```console
  cd {directory name}
  ```
  
  2. Once there, make a top level directory using `mkdir`. 

  ```console
  mkdir {directory name}
  ```

  3. `cd` into it and make another directory called `code`. 

  ```console
  cd {directory name}
  ```

  ```console
  mkdir code
  ```

  4. `cd` into it and run your `git clone {your repo url}` command. 

  ```console
  cd code
  ```

  ```console
  git clone {your repo url}
  ```

</details>


<details>
  <summary>Adding The AI Makerspace Whodunit? Content to Your Repo</summary>

  1. `cd` into your repo and check your remote git. 

  ```console
  cd {your repo name}
  ```

  ```console
  git remote -v
  ```

  At this point, you should just have access to your own repo with an origin branch with both fetch and push options.

  2. Let's setup our global configuration:

  ```console
  git config --global user.email "your email address"
  ```

  ```console
  git config --global user.name "your name"
  ```

  3. Let's add a local branch for development.

  ```console
  git checkout -b LocalDev
  ```

  You can change anything here in this branch!

  ```console
  git add .
  ```

  Commit the changes with the branch addition.

  ```console
  git commit -m "Adding a LocalDev branch."
  ```

  4. Let's push our local changes to our remote repo.

  ```console
  git checkout main
  ```

  ```console
  git merge LocalDev
  ```

  ```console
  git push origin main
  ```


5. Add the Whodunit (WD) repo as an extra remote repo:

  ```console
  git remote add WD git@github.com:AI-Maker-Space/whodunit.git
  ```

  Let's check our remote repos:

  ```console
  git remote -v
  ```

  At this point, you should have access to both your own repo and the AI Maker Space repo and should see something like this:

  ```console
  WD    git@github.com:AI-Maker-Space/whodunit.git (fetch)
  WD    git@github.com:AI-Maker-Space/whodunit.git (push)
  origin git@github.com:ai-kadhim/TestRepo.git (fetch)
  origin git@github.com:ai-kadhim/TestRepo.git (push)
  ```

  Let's update our local repos:

  ```console
  git fetch --all
  ```

  Make a new branch for the Whodunit material (WDBranch).
  ```console
  git checkout --track -b WDBranch WD/main
  ```
  
  You should see something like this:
  
  ```console
  Branch 'WDBranch' set up to track remote branch 'main' from 'WD'.
  ```

  You can visually check whether you are in that branch:

  ```console
  git log --all --graph
  ```

  Now let's push our updated local repo to our remote repo!

  ```console
  git checkout main
  ```

  ```console
  git merge WDBranch --allow-unrelated-histories
  ```

  If there are any conflicts you'll need to resolve them.
  ```console
  git add .
  ```
  
  ```console
  git commit -m "message-here"
  ```
  
  ```console
  git push origin main
  ```

  From now on... after each release follow these steps to update your repo with new content:
  ```console
  git fetch --all
  git checkout WDBranch
  git merge --ff-only @{u}
  git add .
  git commit -m "branch is updated"
  git checkout main
  git merge WDBranch --allow-unrelated-histories
  ```

  You will be asked to add a comment about why this change is necessary --> add a message.
  
  ```console
  git push origin main
  ```
</details>

<p></p>

<details>
  <summary>Adding The AI Makerspace Build Your-Own RAQA System Content to Your Repo</summary>

  1. `cd` into your repo and check your remote git. 

  ```console
  cd {your repo name}
  ```

  ```console
  git remote -v
  ```

  At this point, you should just have access to your own repo with an origin branch with both fetch and push options.

  2. Let's setup our global configuration:

  ```console
  git config --global user.email "your email address"
  ```

  ```console
  git config --global user.name "your name"
  ```

  3. Let's add a local branch for development.

  ```console
  git checkout -b LocalDev
  ```

  You can change anything here in this branch!

  ```console
  git add .
  ```

  Commit the changes with the branch addition.

  ```console
  git commit -m "Adding a LocalDev branch."
  ```

  4. Let's push our local changes to our remote repo.

  ```console
  git checkout main
  ```

  ```console
  git merge LocalDev
  ```

  ```console
  git push origin main
  ```


5. Add the `Build Your-Own RAQA System` (YFL) repo as an extra remote repo:

  ```console
  git remote add YFL git@github.com:AI-Maker-Space/LangChain-Concepts-101---Build-Your-Own-RAQA-System.git
  ```

  Let's check our remote repos:

  ```console
  git remote -v
  ```

  At this point, you should have access to both your own repo and AI Makerspace and should see something like this:

  ```console
  YFL    git@github.com:AI-Maker-Space/LangChain-Concepts-101---Build-Your-Own-RAQA-System.git (fetch)
  YFL    git@github.com:AI-Maker-Space/LangChain-Concepts-101---Build-Your-Own-RAQA-System.git (push)
  origin git@github.com:ai-kadhim/TestRepo.git (fetch)
  origin git@github.com:ai-kadhim/TestRepo.git (push)
  ```

  Let's update our local repos:

  ```console
  git fetch --all
  ```

  Make a new branch for the `Build Your-Own RAQA System` material (YFLBranch).
  ```console
  git checkout --track -b YFLBranch YFL/main
  ```
  
  You should see something like this:
  
  ```console
  Branch 'YFLBranch' set up to track remote branch 'main' from 'YFL'.
  ```

  You can visually check whether you are in that branch:

  ```console
  git log --all --graph
  ```

  Now let's push our updated local repo to our remote repo!

  ```console
  git checkout main
  ```

  ```console
  git merge YFLBranch --allow-unrelated-histories
  ```

  If there are any conflicts you'll need to resolve them.
  ```console
  git add .
  ```
  
  ```console
  git commit -m "message-here"
  ```
  
  ```console
  git push origin main
  ```

  From now on... after each release follow these steps to update your repo with new content:
  ```console
  git fetch --all
  git checkout YFLBranch
  git merge --ff-only @{u}
  git add .
  git commit -m "branch is updated"
  git checkout main
  git merge YFLBranch --allow-unrelated-histories
  ```

  You will be asked to add a comment about why this change is necessary --> add a message.
  
  ```console
  git push origin main
  ```
</details>

<p></p>

## <img src="https://jupyter.org/assets/homepage/main-logo.svg" width=40px/>  Bringing it all together with Jupyter Notebooks

<details>

  <summary>Activating Your Conda Environment</summary>

  1. Now, let's activate the environment we set-up earlier with the command `conda activate llmops-course`. If you were successful, you could see `(llmops-course)` preceeding your terminal commands.

</details>

<details>

  <summary>Adding a Feature Branch</summary>

  Let's add a feature branch to our local repo.  Earlier, we showed you how to add a feature branch and content to your repo via the Terminal.  This time we are going to show you how to do it using the VS Code GUI.  
  
  1. Click on the `main` <img src="images/vscode_main_branch.png" width=30px/> branch in the lower left side of the screen 

  2. You will then see a drop-down menu with some branch-level option commands.  Select the `Create a new branch` option.

  3. You will be prompted to enter the name for the branch.  Let's give our branch an informative name `feature-hello-world`.  The `feature` pre-fix is a common Git convention and let's our collaborators know what the purpose of the branch and the name of the feature.

  4. Now that we have a feature branch to work on, let's add some code to it!

</details>

<details>
  <summary>Hello World! - Part 1</summary>
  1. Next we will review some terminal commands and make some     additions to our repo.  Do these in your terminal where your     current working directory is your repo.

  * Check your current working directory: `pwd` 

  * Create a new file: `touch hello_world.py`

  * Create new directory: `mkdir app`

  * Move file to directory: `mv hello_world.py app/hello_world.py` 

  * Check that the move command worked: `cd app` and then `ls`, you
  should see your `hello_world.py` file

  * Lastly, lets clear our terminal screen: `clear`

  2. Click on the `Explorer` <img src="images/vscode_explorer_tab.png" width=30px/>  tab.

  3. Click on your `hello_world.py` file and type the following into the file:

  ```console
  print("hello world! let's do some ml ops!")
  ```

  4. Save. And now go to the integrated terminal by clicking `CTRL + ~`. In the terminal run your first program of the class by doing `cd app` -> `python hello_world.py`. Congrats, we are off to a great start!

</details>

<details>
  <summary>Hello World! - Part 2 - Notebook Edition</summary>

  1. Create a new file under `app` by clicking on the `Add file` button <img src="images/vscode_add_file.png" width=30px/> and let's name this file `hello_world.ipynb`. The `.ipynb` extension is a notebook extension which will allow you to interact with your code via a notebook in  VS Code, instead of a vanilla Python file. You might need to select your kernel in the top right of the notebook file, if so, choose the one we created previously.
  
  2. In the first cell of `hello_world.ipynb` lets do our imports. 

      ```
      import pandas as pd
      import numpy as np
      import matplotlib.pyplot as plt
      ```

  3. Run the cell by either clicking the play button or by doing `CTRL + ENTER`. 

  4. Create a new cell and in that put the following code:
      ```
      np.random.seed(0)

      values = np.random.randn(100) # array of normally distributed random numbers
      s = pd.Series(values) # generate a pandas series
      s.plot(kind='hist', title='Normally distributed random values') # hist computes distribution
      plt.show()   
      ```
      
  5. Run the cell and you should see your histogram plot! Well done. 

  ![coding histogram](images/coding_histogram.jpeg)

  6. Now let's commit our code to our remote repository. This can be done one of two ways - either through the terminal or through VS Code's GUI. I'll explain both ways and you can choose which you'll use.
    
  * Click `Source Control` <img src="images/vscode_source_control_tab.png" width=30px/>  on the left icon bar.

  * Add a message to your commit by typing in the message field. 

  * Click the check mark <img src="images/vscode_commit_check_mark.png" width=30px/> button under changes to add your files to this commit.  If you haven't saved your changes, you will be prompted to `Save All and Commit`.  Click `Save All and Commit`.
  
     
     
       <details>
       <summary>OPTIONAL: Manually staging individual files</summary>
          1. You can manually stage files by pressing the `+` button.
          
       ![image](https://i.imgur.com/2NnnSbc.png)
       </details>

  * Click the elipsis in `Source Control` <img src="images/vscode_ellipsis.png" width=30px/> ribbon and click `Push`.  You may also be prompted to `Sync Changes`.  This will do Pull and Push, which will fetch new changes to the code and push your updates as well.

  * You can then put in a pull request in GitHub <img src="images/github_pull_request.png" width=100px/>  to merge into the branch that you pulled from, in this case the main branch.  In real life, you would then review the code changes with another developer/team lead/supervisor and address any potential code conflicts.  
  
  <p align = "center" draggable=”false” ><img src="images/github_pull_request_compare.png" 
      width="500px"
      height="auto"/>
  </p>
  
</details>

# 🤖 Build Your Own RAQA!
Are you ready? Let's get to building your [first retrieval-augmented question answering application](https://github.com/AI-Maker-Space/LangChain-Concepts-101---Build-Your-Own-RAQA-System)!

# ⛓️ Get Your Chain Game On!
It's time to put the Chain in Langchain. Let's [build your first LLM App](https://colab.research.google.com/drive/1CAE_gdSQlcDsXGc6YbL1GAnnlZPZuE3b?usp=sharing).

### That's it for now!  And so it begins.... :)
<p></p>



Generating an OpenAI API key
Navigate to [OpenAI's API Developer settings](https://platform.openai.com/account/api-keys) and click on `+ Create new secrete key`.
![image](https://github.com/AI-Maker-Space/LLMOps-Dev-101/assets/37101144/b6179d51-76ac-42a8-8304-39f8b5c9a8c8)

Name your key and click `Create secret key`
![image](https://github.com/AI-Maker-Space/LLMOps-Dev-101/assets/37101144/be0ea05f-59d3-4d20-939d-b402e3d4bbb2)

Copy the key and save it for later use. We will use this key several times in deploying projects. Please do not lose this key or you will need to generate a new one
![image](https://github.com/AI-Maker-Space/LLMOps-Dev-101/assets/37101144/cfaec5fa-5380-4aca-a6ae-6c14c8db6789)






