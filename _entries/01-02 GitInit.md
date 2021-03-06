---
sectionid: gitinit
sectionclass: h2
title: Git Init and Ignore
parent-id: intro
---

### Challenges
* Create a Public GitHub repo in your GitHub account
* Create an local folder and init a Git repo (or clone your GitHub repo, if you initialized it)
* Create a .gitignore file for .Net Core
* Commit the file and push to your GitHub repo
* Create a Resource Group for your

#### Challenge verification
Your GitHub Repo looks like this

![Git Ignore file](media/github/gitrepoignorefile.png)

This command should contain the resource group you will be working in.
```sh
az group list --output table
```

#### Tips

* https://github.com/new
* https://docs.microsoft.com/cli/azure/group#az-group-create

#### Step-by-step solution

<details>
<summary>Create GitHub repo</summary>

Start by creating a new repo in GitHub: https://github.com/new (do not initialize with any files).

![New Git Repo](media/github/newrepo.png)
</details>
<details>
<summary>Init local Git repo and add .gitignore file</summary>

First create a folder to host the project. Since we will be adding this to GitHub, a thought folder structure is of good use. An example (..\github\[account name]\[repo name]\)

```sh
..\[repo name]> git init
..\[repo name]> dotnet new gitignore
```
</details>
<details>
<summary>Commit and push to GitHub</summary>

Navigate to the root of the repo folder and add a reference to your GitHub repo and then stage (add) the files.

```sh
..\[repo name]> git remote add origin https://github.com/[account name]/[repo name]
..\[repo name]> git add .
..\[repo name]> git status
```

Check that all files are staged and then commit:

![Git Status](media/github/gitstatus.png)

Then commit and push the files (-u to initially set upstream repo and branch).

```sh
..\[repo name]> git commit -m 'Initial commit'
..\[repo name]> git push -u origin master
```
Your GitHub repo should now contain the .gitignore file.

![Git Ignore file](media/github/gitrepoignorefile.png)
</details>
<details>
<summary>Create Resource Group</summary>
Run the following az command (choose name and location based on preference):

```sh
az group create --name <Resource-Group-Name> --location westeurope
```

To see a list of available locations you can run this command (some might require whitelisting):
```sh
az account list-locations --query '[].name'
```
</details>
