# Bash Scripting Cheat Sheet

## Shebang

* `#!/bin/bash`: This line should be the first line in a bash script to specify the interpreter.

## Comments

* `# This is a comment.`: Use `#` to add comments to your code; these are ignored by the interpreter.

## Variables

* `variable_name=value`: Assigns a value to a variable. Do not use spaces before or after the equals sign (`=`).
* `echo $variable_name`: Displays the value of a variable. The `$` is necessary to access the value.
* `echo ${variable_name}`: Alternative syntax for displaying a variable, useful in specific cases.
* `unset variable_name`: Removes a variable.
* `export variable_name`: Makes a local variable available to sub processes (environment variable).
* `export variable_name=value`: Creates an environment variable and assigns it a value.
* In Bash, variables are treated as strings, thus mathematical calculations need a specific syntax.
* Variable names: must contain only alphanumeric characters or underscores `_`, and they are case-sensitive.

## Strings and Quoting

* `"string with spaces"`: Double quotes allow variable substitution and interpretation of special characters.
* `'literal string'`: Single quotes prevent variable substitution and interpretation of special characters, treating everything literally.
* `\`: The backslash is used to escape special characters.

## Script Arguments

* `$1, $2, ... $9`: Contain the positional arguments passed to the script.
* `$#`: Contains the total number of arguments passed to the script.
* `$@`: Contains all arguments passed to the script as an array separated by spaces.
* `$*`: Similar to `$@`, but in some contexts may behave differently (not covered in detail in the sources).

## Input/Output Commands

* `echo "text"`: Prints text to standard output.
* `echo -n "text"`: Prints text without a trailing newline.
* `> file`: Redirects the output of a command to a file, overwriting it.
* `>> file`: Redirects the output of a command to a file, appending it to the existing content.
* `2> file`: Redirects errors of a command to a file.
* `2>> file`: Redirects errors of a command to a file, appending them to existing content.
* `< file`: Redirects input from a file to a command.

## if statement

* `if [ condition ]`: Starts an if block. A space is needed between the brackets and the condition.
* `then`: Executes commands if the condition is true.
* `elif [ condition2 ]`: Adds an alternative condition.
* `else`: Executes commands if the condition is false.
* `fi`: Ends the if block.

## Numeric Comparison Operators (used with if)

* `-eq`: Equal to.
* `-ne`: Not equal to.
* `-gt`: Greater than.
* `-ge`: Greater than or equal to.
* `-lt`: Less than.
* `-le`: Less than or equal to.

## String Comparison Operators (used with if)

* `==`: Compares if two strings are identical.
* `!=`: Compares if two strings are different.

## for Loops

* `for variable in list`: Starts a for loop with variable taking on the values in the list.
* `do`: Executes commands in the loop.
* `done`: Ends the for loop.

## Exit Status

* `exit 0`: Indicates success.
* `exit 1` (or other number other than 0): Indicates an error.
* `$?`: Contains the exit status of the last executed command.

## Other useful commands

* `shift`: Moves the positional arguments by one, removing `$1`.
* `grep`: Searches for patterns inside files or the output of a command.
    * `grep "^[A-Za-z]*$"`: Example of grep that verifies if a string contains only letters.
* `chmod`: Modifies permissions of files and directories.
* `which`: Shows the absolute path of a command.

## Arrays

* `FILES="item1 item2 item3"`: Example of how to create an array.
