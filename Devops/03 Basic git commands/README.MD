# Hands-On Git Project: Collaborative Website Development with Git and GitHub

In this mini project, we'll create a step-by-step project to simulate the workflow of Tom and Jerry using Git and GitHub. This hands-on project will include installation of Git, setting up a GitHub repository, cloning the repository, creating branches, making changes, and merging those changes back into the main branch.

## Part 1: Setup and Initial Configuration

### 1. Install Git:

- Visit the [official Git website](https://git-scm.com/) and download the version of Git for your operating system. Follow the installation instructions.

### 2. Create a GitHub Repository:

- Sign up or log in to [GitHub](https://github.com).
- Click the "+" icon in the top-right corner and select "New repository."
![image](img/creating%20a%20new%20repo.png)

- Name your repository (e.g.,"ai-startup-website") and initialize it with a README file.
- Click "Create repository."
![image](img/new%20repot%20created.png)

### 3. Clone the Repository:
- on your repository page, click the "Code" button and copy the repository URL.
![image](img/cloning%20repo%20image.png)
- Open your terminal or command prompt.
- Navigate to the directory where you want to clone the repository.
- Clone (Download) the repository from GitHub using the following command:
    ```bash
    git clone <repository_url>
    ```
- Replace <repository_url> with the URL you copied from GitHub.
    ![image](img/clone%20repo%20from%20terminal.png)
- since you just clonned your repository, your branch is main
- Navigate to the repository directory:
    ```bash
    cd <repository_name>
    ```
- create an empty file named index.html
    ```bash
    touch index.html
    ```
- add the following code to the file
    ```bash
     This is the Admin creating an index.html file for Tom and Jerry
 
- Check change has not been staged
    ```bash
    git status
    ```
- stage the changes
    ```bash
    git add index.html
    ```
- confirm the changes has been staged for commit
    ```bash
    git status
    ```
    Now, after staging the changes, the file name will appear in green in the terminal output. This color changes signifies that the file has been successfully staged, making it ready for the next step, which is committing the changes.
- commit the changes
    ```bash
    git commit -m "This is my first commit"
    ```
    this take the changes and records them in the repository's history with a message describing what was done. This commit is a miltestone, marking a specific point in the project's development.

- push main branch to GitHub
    ```bash
    git push origin main
    ```
## Part 2: Simulating Tom and Jerry's Work

To simulate both Tom and Jerry's working on the same laptop, you'll switch betwween two branches, making changes as each character.
1. Tom's work   

    - Navigate to the project directory just cloned:    
        ```bash
        cd repository_name
        ```
        This is moves you into the project's directory

    - check the curren branch: This shows you a list of all branches in your local repository. Initially, you'll only have the main branch because that the default starting pont and no other branches have been created yet.
        ```bash
        git branch
        ```
    - create a new branch for Tom's work:
        ```bash
        git checkout -b update-navigation
        ```
    ![image](img/creating%20a%20new%20branch%20for%20tom's%20work.png)

    This create a new branch named "update-navigation" ( it cane be named to wheatever you want). The command also automatically switches to the newly created brach from the "main" branch. This branch "update-navigation" is where you'll simulate Tom's updates to the website without affecting whatever is tin the main branch.
    
    - Check the branch again to see your newly created bramch.
        ```bash
        git branch
        ```
        ![image](img/toms%20git%20branch%20show.png)

        Running git branch again, now shows your newly created branch in green, indicating that you are currently on it.
    - Recall you created an empty file named index.html. The file will also exist in the 'update-navigation' branch: open the index.html and add the content below:
        ```bash
        This is the Tom adding Navigation to the AI-website
        ```
        This simulates Tom's contribtion to the project. The text represent the work he's doing ont he navigation bar. in the real world , this will be an actual software code.
    
    - Check changes has not been staged
        ```bash
        git status
        ```
