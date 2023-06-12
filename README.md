
## How to Delete .DS_Store Files in a GitHub Repository on Mac

### Step 1: Locate Your Repository in Terminal

Open your terminal application and navigate to the root directory of your repository using the `cd` command. For example, if your repository is located at `/Users/xxx/Desktop/xxx`, you can use the following command:

```shell
cd /Users/xxx/Desktop/xxx
```

### Step 2: Remove .DS_Store Files

To find and remove all the .DS_Store files in your repository, execute the following command:

```shell
find . -name .DS_Store -print0 | xargs -0 git rm -f --ignore-unmatch
```

This command will search for all the .DS_Store files recursively within your repository and remove them using `git rm` command.

### Step 3: Create a .gitignore File

If you don't have a .gitignore file in your repository, you can create one to prevent the .DS_Store files from being added in the future. Execute the following commands:

```shell
touch .gitignore
echo .DS_Store > .gitignore
```

The first command creates an empty .gitignore file, and the second command adds the `.DS_Store` pattern to the file.

### Step 4: Push Changes to GitHub

Now that the .DS_Store files have been removed and the .gitignore file has been created, you can commit the changes and push them to your GitHub repository. Execute the following commands:

```shell
git add .gitignore
git commit -m '.DS_Store removed'
git push origin master
```

The first command adds the .gitignore file to the staging area, the second command commits the changes with a meaningful message, and the third command pushes the changes to the `master` branch of your GitHub repository.
### Step 5:  Write Access to the Repository
In order to push the changes to your GitHub repository, you need to ensure that you have write access. Follow these steps to generate a personal access token:

Go to your GitHub account settings by clicking on your profile picture in the top right corner and selecting "Settings" from the dropdown menu.

In the left sidebar, click on "Developer settings."

In the new page, click on "Personal access tokens."

Click on the "Generate new token" button.

Provide a meaningful description for the token, such as "Repository Write Access."

Under "Select scopes," make sure to select the "repo" option.

Click on the "Generate token" button at the bottom of the page.

GitHub will generate a personal access token for you. You can use is with your github username to push change :)

