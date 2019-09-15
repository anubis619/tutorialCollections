# A small cheatSheet for Git and GitHub

## Author: Marius Voinescu

### Date: 14/09/2019

## Git:

A list of all the commands that you use whit Git
* * *

## Commands:

### Initialize a git repository from the terminal:

```bash
git init
# initializes the repository
```

### Add a file or files to staged:

```bash
git add <file you want to add>
# add files under staged for your repository

git add .
# will add  all files under the current directory
# git add . will only add  files under the current directory, so if you have modified files under a separate folder they will not be added

# to add all updated files anywhere in the working project use the bellow command
git add --all
# alternative:
git add -A

```

### Commit your stated files:

```bash
git commit -m "Message"
# Message should be descriptive but not very long

# Alternative:
git commit -a -m "Message"
# Using the above command will add all the files to the staged thanks to the -a parameter. This can be used if you have modified files after you have already staged for example
```


* NOTE:
  When opening git diff and it opens the git file, to close you will need to type:

  ```bash
    q
  ```

* NOTE on git diff, git log and git show.
  Instead of the sha information, we can go ahead and use HEAD~n, where n is the number of commits behind the most recent commit

### Checking differences on a file:

```bash
git diff <fileName>
# Replace fileName with the name of file you want to check difference on

git diff <sha1> <sha2>
# replace <sha1> and <sha2> with the first 8 characters of each commit sha you want to check differences between
```

### Checking the repository commit log:

```bash
git log
// Explore the repository log of the active repository
```

### Using Git show to have a better view as it combines both git diff and git log:

```bash
git show <commit sha>
# replace the <commit sha> wit the first 8 characters of the commit you want to get
# details on. The git show command will provide a much better view of what exactly
# happened on that specific commit you query and check
```


### Adding a remote to your git repository:

```bash
git remote add origin <url>
# replace <url> with the link of you GitHub Repository
```

### Pushing you files to the Github remote:

```bash
git push -u origin master
# Will push your repository to the master branch
```

### Getting updates from the online repository:

```bash
git pull origin master
# pull changes from the master branch to origin branch locally
```

### Setting the upstream branch for the github repository will no longer require the origin and master on the git pull command:

```bash
git branch --set-upstream-to=origin/<branch> master
#  The above command is used to set tracking information for this branch
# If you set the above command it will make the "git pull" command easier as it will already know where to pull
```

### Cloning a repository:

```bash
git clone <url>
# Replace <url> with the url of the repository you want to clone locally
```

### Checking blame information using the terminal:

```bash
git annotate <file>
# git annotate is used to get data on the specific file and details on commits.
# An alternative for this command on VSC would be the extensions of GitLens that
# shows that data within the editor as seen in the picture attached at the end of this.
```

### Git Checkout and Git Reset:

* If you have files that are stated and you want to revert to a previous version you will have to use git reset first and then git checkout.
* If you have no files that are stated, then you can just use git checkout.

```bash
git checkout -- {file}
# replace file with the file that you want to discard changes in the working directory
git reset HEAD <file>
# If you hav staged the file already git checkout will no longer work t, so for that you will need to use git reset to unstage the file
```

### Creating a new branch and switching to it:

```bash
git branch <name>

# to check the branches use:
git branch

# to switch branches we will use a command already discussed above
git checkout <branch name>
```

* If you have already pushed the information to your repository you can revert using the following command:

```bash
git checkout <sha> <file>
# replace sha with the first 8 characters of the sha you want to revert to
# replace file with the file you want to revert

```

* * *
* * *

## GitHub:
  
* Uses Git (copies or clones the repository)
* Just one more computer that has a clone o the repository
* Online. You need an internet connection active in order to push or pull.
* Adds user management on the repositories
* Tool Integration

### How to Fork a repository from GitHub

![GitHub Fork](/img/GitHubFork.jpg)


## Working with branches

Best practices:

* Always have a working version of the project as the master branch
* A best practice would be to have a master, test, and dev branch. Names might vary but their functionality will be the same more or less.

Visual Studio Code extension that I recommend:

* * *

### GitLens blame information:

![GitLens Blame](/img/GitLens_Blame_annotations.png)

To get more details about the extension:

[GitLens GitHub Repository](https://github.com/eamodio/vscode-gitlens)

[GitLens site](https://gitlens.amod.io/)