# Conceptualising Git Setup with Tom and Jerry

This document explains a basic Git workflow through the example of two developers, Tom and Jerry. It outlines how they collaborate on the same project using Git and a remote repository.

---

## 1. Initial Setup

- Both Tom and Jerry have Git installed on their computers.
- They clone (or download) the project repository from a central repository (like [GitHub](https://github.com), [GitLab](https://gitlab.com), or [Bitbucket](https://bitbucket.org)) to their local machines.
- Cloning provides them with a complete copy of the project, including all files and version history.

---

## 2. Starting Work

- Tom and Jerry pull the latest changes from the central repository to ensure they have the most current version of the project, including the `index.html` file.
- They each create a new branch from the main branch:
  - Tom creates a branch named `update-navigation`.
  ![image](img/Tom%20branch%20checkout.png)
  - Jerry creates a branch named `add-contact-info`.
 ![image](img/jerry%20creating%20new%20branch%20add-contact.png)

Branches allow them to work independently without affecting the main development line.

---

## 3. Making Changes

- On his branch, Tom updates the navigation bar in `index.html`.
![image](img/tom%20navigation%20bar%20modified.png)
- Simultaneously, Jerry updates the footer of the same file to add contact information.
![image](img/jerry%20creating%20new%20branch%20add-contact.png)
- Both developers commit their changes to their respective branches. A **commit** in Git is like saving your work along with a message describing what was changed.


---

## 4. Merging Changes

- After completing their changes, Tom and Jerry push their branches to the central repository.
![image](img/new%20branch%20pushed%20to%20remote%20repo%20by%20tom.png)
- Tom initiates a **pull request (PR)** to merge his `update-navigation` branch. A PR is a request for the team to review and approve his changes before integrating them into the main project.
![image](img/tom%20creating%20a%20pull%20request%20.png)
- Once approved, the team merges Tom’s PR into the main branch, updating the `index.html` file.
![image](img/pull%20request%20merged%20for%20tom%20.png)
- Jerry then pulls the latest changes from the main branch into his `add-contact-info` branch to ensure his work integrates with Tom's recent changes.
![image](img/updated%20branch%20for%20jerry%20after%20merge.png)
- Jerry commits his changes to his branch and pushes them to the central repository.
![image](img/updated%20branch%20for%20jerry%20after%20merge.png)
- If there are any conflicts (e.g., overlapping edits in `index.html`), Jerry resolves them using Git's conflict resolution tools.
![image](img/jerry's%20pull%20request%20merged.png)


---

## Summary

This workflow demonstrates how Git helps multiple developers collaborate on a project simultaneously. It highlights the importance of:
- Creating separate branches for features,
- Using commits for progress tracking,
- Reviewing and merging changes via pull requests,
- Keeping branches updated to avoid and resolve conflicts.

Git enables smoother teamwork by keeping changes organized, reviewed, and conflict-free.