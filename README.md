# Vax

This is a course requirement for CS191/192 Software Engineering Courses of the Department of Computer Science, College of Engineering, University of the Philippines, Diliman under the guidance of Ma. Rowena C. Solamo for AY 2020-2021.

- Aloveros, Aira Mae

- Galino, John Henry

- Israel, Kurt Ian Khalid 

- Yu, Jeremy Vincent 

  

## Getting Started

Make sure that you have Git installed in your device. You can check if you have Git installed by opening your terminal (Powershell/Command Prompt for Windows) and typing `git --version`. This command should output the current version of Git installed in your system. If this results to an error, then you may need to install Git.

### Installing Git

#### For Windows

##### Using Git for Windows

1. Go to Git's official [website](https://git-scm.com/) and download the latest release for Windows.
2. Run the installer. In the **Choosing the default editor used by Git**, choose whichever text editor you are most comfortable with. Otherwise, leave the defaults alone.
3. Once the installer has finished, check if the installation is successful by running `git --version` in PowerShell or Command Prompt.

##### Using `winget`

1. If you have `winget` installed, you may also use it to install Git. `winget` is already included in your system if you are running Windows 11 or a recent version of Windows 10. If not, you may install `winget` by following the instructions in this [link](https://docs.microsoft.com/en-us/windows/package-manager/winget/).

2. Once you have installed `winget`, type the following command on PowerShell or Command Prompt.

   ```
   winget install --id Git.Git -e --source winget
   ```

3. Once the installation is finished, check the install by running `git --version`.

#### For Mac

##### Using Git for Mac

1. Go to Git's official [website](https://git-scm.com/) and download the latest release for Mac.
2. Run the installer. In the **Choosing the default editor used by Git**, choose whichever text editor you are most comfortable with. Otherwise, leave the defaults alone.
3. Once the installer has finished, check if the installation is successful by running `git --version` in your terminal.

##### Using Xcode

1. You may also install Git by installing Xcode in your system. To install Xcode, run the following command in your terminal.

   ```
   xcode-select --install
   ```

2. Once installed, check for the presence of Git by running `git --version` from your terminal.

#### For Linux

Git is usually included in most Linux distributions. In the case that it is not installed, you may install it through your package manager.

##### Debian/Ubuntu

```
sudo apt install git
```

##### Fedora

```
sudo yum install git # (up to Fedora 21)
```
```
sudo dnf install git # (Fedora 22 and later)
```

##### Gentoo

```
sudo emerge --ask --verbose dev-vcs/git
```

##### Arch Linux

```
sudo pacman -S git
```

##### openSUSE

```
sudo zypper install git
```

### Initial Clone

Once you have Git working on your device, you must now get a local clone of the repository. To do this, open your terminal (or Powershell/Command Prompt) and navigate to the folder where you want to place the project using `cd`. 

If you are not comfortable working in the terminal, in **Windows**, you may also do the above by opening the folder where you want to place the project through File Explorer and doing `Shift + Right-click ` on an empty space. This will open a context menu, where you can click "Open PowerShell Window Here" to open the directory inside PowerShell. 

![](https://i.stack.imgur.com/UtB5P.gif)



For **Mac**, you may also do this by drag-and-dropping the folder where you want to put the project to the Terminal icon in the Dock, or typing `cd` in the Terminal, dragging the folder to the Terminal window, then pressing Enter.  ![](https://www.howtogeek.com/wp-content/uploads/2021/07/folder_drag.mov.gif)



For **Linux**, some distros might have "Open in Terminal" in their right-click context menu, similar to Windows, while others might not. If your distro doesn't have the context menu, then you can try dragging the folder to your terminal after typing `cd` and pressing Enter. 

Once you have your folder opened in the terminal, you can then clone the project by entering the command below.

```
git clone https://github.com/Vax-CS192/Vax.git
```

This will create a copy of the repository in the folder you chose. Open the Godot Editor, then import the project folder to open it in Godot.

### Project Structure

There are only two main folders in the project: Assets and Scenes.

#### Assets

This folder will contain all the visual and audio elements that the game will have. Please make sure to place all assets that you need for a screen in a separate folder inside Assets.

#### Scenes

This folder should contain all the scenes and scripts that are needed for the game. It is already subdivided by subsystem, with the intention that all scenes and scripts related to a subsystem will be placed in the folder for that subsystem. However, you are free to change the directory structure as long as it doesn't affect the other subsystems.



## How to Work with this Repository

The recommended workflow for this project folder is [Github Flow](https://docs.github.com/en/get-started/quickstart/github-flow). 

![](https://user-images.githubusercontent.com/6351798/48032310-63842400-e114-11e8-8db0-06dc0504dcb5.png)

**TL;DR version**

1. When you want to work on a screen, you must first create a feature branch. A **feature branch** is like an environment where you can safely make your changes to the project without overwriting the work of others. You can create a feature branch by opening the project folder in a terminal (you may use the steps in [Initial Clone](###Initial Clone)) and entering the command below. 

   ```
   git checkout -b <insert-branch-name> # Example: git checkout -b Lab
   ```

   The command above will create a new branch with your chosen name and place you on that branch. You can check which branch you are currently on by entering `git branch` and you can transfer between existing branches by using `git checkout <name-of-branch-you-want-to-go-to>`.

   **Note**: `git checkout -b` creates a new branch based on the branch you are currently on. Most of the time, for this project, you will need to be in the *main* branch first before creating a new branch so that the new branch contains the latest updates to main. So if you want to create a new branch, you may use the following commands.

   ```
   git checkout main # Go to main branch
   git pull # Update main branch to the latest changes
   git checkout -b <insert-name> # Create new branch based on main
   ```

2. Work on the screen in Godot. When testing your screen, please prefer to use the "Play Scene" button (F6) instead of the "Play" button. The "Play" button is usually used when testing the entire game, not a specific scene only.

   ![Play Scene button](https://docs.godotengine.org/en/stable/_images/nodes_and_scenes_09_play_scene_button.png)

3. When you've finished your changes, you must commit your changes to your branch. This can be done by entering the following commands in the terminal.

   ```
   git add .
   git commit -m <Summary of what you changed>
   ```

   Now, we can upload the changes you made to Github. However, before we can upload your changes, we must make sure that your changes aren't in conflict with the 
   changes that other contributors have made. Thus, run the following command.

   ```
   git pull --rebase
   ```

   This will synchronize your changes with the repository in Github and output any conflicts that you will have to fix. Once the command doesn't output an error   
   anymore, you may now upload your changes using this command.

   ```
   git push
   ```

   This command will upload your changes to *your branch* in Github.

4. When you've finished working on your screen, or you want to make your changes available to the other contributors, you can do a **pull request** to the *main branch* in order to update the main branch in Github. This [link](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) summarizes the steps needed to create a pull request. If your pull request shows that there are no conflicts, then feel free to merge the pull request. You can also ask others for their comments if you want to.

   

## Github-specific stuff

When performing `git push`, Github will ask for your username and password, but it will not accept the password to your account when you enter it. This is because Github has stopped accepting account passwords last year and now implements **personal access tokens**. To create a token, you can follow the instructions [here](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token). When Github asks for a password again, use the personal access token instead to successfully perform the `git push`.
