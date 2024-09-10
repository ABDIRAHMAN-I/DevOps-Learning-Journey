


**File and Directory Management Commands**:

- **`ls`**: View the contents of the current directory.
    - **`ls -a`**: List all files and directories, including hidden files (files or directories starting with a dot (`.` will not appear with a regular `ls` command)).
    - **`ls -l`**: Provide detailed information about files and directories, including:
        - Permissions
        - Owner
        - Group
        - Size
        - Modification time
        - More
    - **`ls -R`**: List all files and directories recursively, including all subdirectories and their contents, to show the directory structure in detail. It’s useful for understanding the hierarchy and contents of directories in more detail.
- **`cp`**: Copies files or directories. Cannot copy directories. **`cp`** [file_you_want_to_copy] source destination
    - **`cp -r`** - copies **directories** and their contents from one location to another.  **`cp -r`** [directory_you_want_to_copy] source destination
- **`mv`**: Moves or renames files or directories. *rename: **`mv`** (old_filename) (new_filename)* / *move: **`mv`** (file_you_want_to_move) (directory_you_want_to move_it_to)*
- **`rm`**: Removes (deletes) files.
    - **`rm -r`:** used to remove (delete) directories.
    - **`rm -rf` /** - Deletes Everything. **extremely dangerous** and should never be run carelessly
    
    **`rm`**: Stands for "remove" and is used to delete files or directories.
    
    **`r`**: The recursive flag, meaning it will delete the directory and all of its contents, including subdirectories and their contents.
    
    **`f`**: The force flag, which suppresses warnings and forces the deletion of files, even if they are write-protected.
    
    **`/`**: The root directory, which is the top-level directory of the entire file system.
- **`mkdir` `[make_directory]`**: Creates a new directory.
    - **`mkdir -p [directory_path]`**: Create a directory and any necessary parent directories.
- **`rmdir`**: Removes an empty directory.
- **`touch`**: Creates an empty file or updates the timestamp of an existing file. ex:**`touch`** filename.txt.
This will create a new, empty file named filename.txt in the current directory. If the file already exists, it simply updates its last modified and last accessed timestamps without changing the content. You can also create multiple empty files at once by listing them after **`touch`**  file1.txt  file2.txt  file3.txt






