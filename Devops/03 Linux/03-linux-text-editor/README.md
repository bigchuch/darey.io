# Linux Text Editors

A Linux text editor is a software application specifically designed for creating, modifying, and managing text files on a Linux-based operating system. Text editors play a crucial role in the Linux environment, providing a means for users to interact with and manipulate plain text files, configuration files, scripts, and other text-based documents.

There are various text editors available in the Linux ecosystem, each with its own set of features and user interface. Let's dive in to the use of some text editors.

---

## VIM Text Editor

The Linux Vim text editor, short for "Vi Improved," is a powerful and versatile text editing tool deeply ingrained in the Unix and Linux ecosystems. Vim builds upon the foundation of the original Vi editor, offering an extensive set of features, modes, and commands that empower users to manipulate text efficiently. 

While Vim has a steeper learning curve compared to simpler editors like Nano, its capabilities make it a favourite among tech professionals and anyone working extensively with text files.

---

### Working With VIM Editor

Let’s get our hands on Vim:

- **Open a new file** named `exercise.txt` using the following command:

    ```bash
    vim exercise.txt
    ```
    The command above creates a exercise.txt even if it doesn’t exist. Then it opens the file so that we can start writing into it. It’s just like opening up Notepad on Windows.

- **Enter Insert Mode** to edit the file.
	* Press `i` to enter Insert mode.
	* Type the following into the file:

    ```bash
    Hello, this is a Vim hands–on project.
    welcome to darey.io
    ```


- **Moving Around:** Navigate through the text using the arrow keys or h (left), j (down), k (up), and l (right).
- **Deleting a Character:** Press `esc` to exit `insert mode`. Position the cursor on a character you want to delete and press x.
- **Deleting a Line:** Press esc to ensure you’re in Normal mode. Move the cursor to a line and press `dd` to delete the entire line.
- **Undoing Changes:** Press u in Normal mode to undo the last change.
- **Saving Changes:** After editing, press esc, then type `:wq` and press Enter.
	*	**w** = write
	*	**q** = quit
- **Quitting Without Saving:** Press esc, then type `:q!` and press Enter.
    ![Vim](./img/vim%20editor%20opened%20.png)

    ![Vim](./img/saved%20filed%20with%20vim.png)



## Nano Text Editor

Among Linux text editors, Nano stands out as a user-friendly and straightforward tool, making it an excellent choice for users who are new to the command line or those who prefer a more intuitive editing experience.

Nano serves as a versatile and lightweight text editor, ideal for performing quick edits, writing scripts, or making configuration changes directly from the command line. Its intuitive command set simplifies text manipulation tasks, allowing users to navigate through files, insert or delete text, and save changes effortlessly.

Nano’s ease of use extends to its keyboard shortcuts, making it accessible even to those unfamiliar with intricate command sequences. With Nano, users can focus on the content of their text files without the distraction of a complex interface, making it a go-to choice for a wide range of users, from beginners to experienced Linux enthusiasts.


### Working With Nano Editor

- **Opening a File:** Named `nano_project.txt` using the command:
    ```bash
    nano nano_file.txt
    ```    

    ou’ll enter the Nano editor interface.

- **Entering and Editing Text:** Type a few lines into the file. Nano has a simple interface; you can start typing immediately.
- **aving Changes:** Save your changes by pressing Ctrl + O. Nano will prompt you to confirm the filename. Press Enter.
- **Exiting Nano:** Press Ctrl + X. If there are unsaved changes, Nano will prompt you to save.
- **pening an Existing File:** Opening an existing file(if avaliable) using the following command
    ```bash
    nano existing_file.txt
    ```
    ![Nano](./img/opening%20a%20file%20with%20nano1.png)

    ![Nano](./img/opening%20a%20file%20with%20nano.png)

    ![Nano](./img/saving%20nano%20edited%20file.png)




    Navigate through the file using arrow keys. Write data, then save the file content.



