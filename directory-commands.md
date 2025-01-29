# Directory Management Commands Cheat Sheet

## `mkdir` (Make Directory)

*   **Purpose:** The `mkdir` command is used to create new directories.
*   **Basic syntax:** `mkdir directory_name`
    *   Creates a directory with the specified name in the current location.
*   **Important options:**
    *   `-p` or `--parents`: Creates parent directories if they do not exist. This is useful for creating a nested directory structure with a single command. For example: `mkdir -p folder1/folder2/folder3` will create `folder1`, `folder2`, and `folder3`, even if they did not exist before.
    *   `-v`: Verbose mode, shows the actions performed. For example: `mkdir -v new_folder` will show an output like `mkdir: created directory 'new_folder'`.
    *   `--help`: Shows a summary of available options for the command.
*   **Usage Considerations:**
    *   File and directory names can contain uppercase and lowercase letters, numbers, spaces, and special characters. However, it is good practice to avoid spaces and special characters to prevent problems with the shell.
    *   Spaces and special characters in names can be managed by using quotation marks or the escape character `\`. For example: `mkdir "name with spaces"` or `mkdir name\ with\ spaces`.
    *   If you try to create a directory within a non-existent one without using the `-p` option, you will get an error message.
    *   To create multiple directories simultaneously, you can do so with a single `mkdir` command, separating the names with spaces or using curly brace expansion: `mkdir folder/{sub1,sub2}`.

## `rmdir` (Remove Directory)

*   **Purpose:** The `rmdir` command is used to remove empty directories.
*   **Basic syntax:** `rmdir directory_name`
    *   Removes the specified directory only if it is empty.
*   **Important options:**
    *   `-p`: Removes parent directories if they are empty after removing the specified directory. Works similarly to `mkdir -p`, but in reverse.
    *   `-v`: Verbose mode, shows the actions performed. For example: `rmdir -v folder` will show an output like `rmdir: removed directory 'folder'`.
    *   `--help`: Shows a summary of available options for the command.
*   **Usage Considerations:**
    *   `rmdir` can only remove empty directories. If a directory contains files or other directories, `rmdir` will fail with an error message.
    *   To remove a non-empty directory, you must use the `rm -r` command.
    *   You can use quotation marks or the escape character `\` for names that contain spaces or special characters.
    *   The `-p` option is useful for deleting nested directory trees if all directories are empty.

## Comparison and Warnings

*   `mkdir` and `rmdir` are basic commands for managing directories from the command line.
*   Always use `--help` or the `man` command to further explore available options. For example: `man mkdir` or `mkdir --help`.
*   **Caution:** `rmdir` is safe because it only removes empty directories. To delete non-empty directories, use `rm -r` with extreme caution, especially if used with wildcards (globbing) like `*`.
