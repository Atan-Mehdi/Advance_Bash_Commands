# Advanced Bash Commands

Welcome to the repository for advanced Bash commands! This guide provides explanations and examples for commonly used Bash commands, along with additional details about specific options and terminologies.

## Table of Contents

- [File and Directory Operations](#file-and-directory-operations)
- [File Permissions](#file-permissions)
- [Text Processing](#text-processing)
- [File Management](#file-management)
- [Viewing and Filtering](#viewing-and-filtering)
- [Scripting and Automation](#scripting-and-automation)
- [Additional Commands](#additional-commands)
- [Contributing](#contributing)

## File and Directory Operations

- **`pwd`**  
  Display the present working directory path.

- **`ls`**  
  List directories and files in a folder.

- **`ls -R`**  
  List subdirectories recursively.  
  `-R`: Recursive listing of directories and their contents.

- **`ls -t`**  
  List files sorted by modification time.  
  `-t`: Sort by modification time, newest first.

- **`ls -l`**  
  List files with permissions, modification date, and size.  
  `-l`: Long listing format, including file permissions, number of links, owner, group, size, and modification date.

- **`ls -lt`**  
  List files sorted by modification time with time included.  
  `-lt`: Combines `-l` (long format) and `-t` (time sorting).

- **`ls -la`**  
  List all items including hidden items.  
  `-a`: List all files, including hidden ones (those starting with a dot).

- **`ls -lRa`**  
  Recursively list all items including hidden ones.  
  `-R`: Recursive listing.  
  `-a`: Include hidden files.

- **`ls -lr`**  
  List files in reverse order.  
  `-r`: Reverse the order of the sort.

- **`ls -s`**  
  List directories by size.  
  `-s`: Display file sizes in blocks.

- **`ls *.FILE_EXTENSION_NAME`**  
  List files with a specific extension.

- **`ls Zoo*`**  
  List files starting with "Zoo".

- **`ls ..`**  
  List directories and folders in the parent directory.

- **`cd`**  
  Change to a specified directory.

- **`cd ..`**  
  Move up one directory.

- **`cd ../../`**  
  Move up two directories.

- **`touch filename`**  
  Create an empty file.

- **`cat filename`**  
  View the contents of a file.

- **`cat > filename`**  
  Write to a file. Use `Ctrl + D` to save and exit, `Ctrl + C` to exit without saving.

- **`cat >> filename`**  
  Append to an existing file.

- **`mkdir dirname`**  
  Create a new directory.

- **`mkdir test && cd test`**  
  Create a new directory and navigate into it.

- **`mkdir -p path/to/dir`**  
  Create nested directories.  
  `-p`: Create parent directories as needed.

- **`mv source destination`**  
  Move or rename files or directories.

- **`cp source destination`**  
  Copy files or directories.

- **`cp -r source destination`**  
  Copy directories recursively.  
  `-r`: Recursively copy directories and their contents.

- **`rm filename`**  
  Remove a file.

- **`rm -r directory`**  
  Remove a directory and its contents.  
  `-r`: Recursively remove directories and their contents.

## File Permissions

- **`chmod ugo-rwx filename`**  
  Remove all permissions for user, group, and others.  
  `ugo`: User, group, others.

- **`chmod -R ugo+rwx directory`**  
  Recursively add read, write, and execute permissions to a directory.  
  `-R`: Recursively apply changes.

- **`chmod u+x filename`**  
  Add execute permission for the user.  
  `u+x`: User execute permission.

- **`chmod g+wx filename`**  
  Add write and execute permissions for the group.  
  `g+wx`: Group write and execute permissions.

- **`chmod u-x filename`**  
  Remove execute permission for the user.  
  `u-x`: User execute permission removal.

- **`chmod 664 filename`**  
  Set file permissions using octal notation: 6 (read and write) for user and group, 4 (read) for others.  
  `664`: Octal representation of file permissions.

- **`chmod 777 filename`**  
  Set full permissions (read, write, execute) for user, group, and others.  
  `777`: Octal representation of full permissions.

## Text Processing

- **`grep "pattern" filename`**  
  Search for lines containing a pattern.

- **`grep -c "pattern" filename`**  
  Count the number of lines containing a pattern.  
  `-c`: Count the number of matching lines.

- **`grep -h "pattern" filename`**  
  Search for a pattern without showing filenames (useful for multiple files).  
  `-h`: Suppress filenames in the output.

- **`grep -i "pattern" filename`**  
  Search for a pattern case-insensitively.  
  `-i`: Case-insensitive search.

- **`grep -n "pattern" filename`**  
  Search for a pattern and include line numbers.  
  `-n`: Display line numbers with matching lines.

- **`grep -w "pattern" filename`**  
  Match whole words only.  
  `-w`: Match the whole word.

- **`grep -o "pattern" filename`**  
  Print only the matched parts of a line.  
  `-o`: Only show the matched parts.

- **`grep -v "pattern" filename`**  
  Invert the match: show lines that do not contain the pattern.  
  `-v`: Invert the match.

- **`grep -A 5 "pattern" filename`**  
  Show 5 lines after the matching pattern.  
  `-A`: Number of lines to show after a match.

- **`grep -B 5 "pattern" filename`**  
  Show 5 lines before the matching pattern.  
  `-B`: Number of lines to show before a match.

- **`grep -C 5 "pattern" filename`**  
  Show 5 lines before and after the matching pattern.  
  `-C`: Number of lines to show around a match.

## Viewing and Filtering

- **`head filename`**  
  View the first 10 lines of a file.

- **`head -n 20 filename`**  
  View the first 20 lines of a file.  
  `-n`: Number of lines to display.

- **`tail filename`**  
  View the last 10 lines of a file.

- **`tail -n +25 filename | head -n 5`**  
  View lines 25 through 30 of a file.  
  `-n +25`: Start showing lines from line 25.  
  `| head -n 5`: Pipe the output to `head` to show the first 5 lines of the result.

- **`wc filename`**  
  Display line count, word count, and character count of a file.

## Scripting and Automation

- **`sed -n '/pattern/ p' filename`**  
  Print lines matching a pattern (using `-n` to suppress default output).  
  `-n`: Suppress automatic printing of pattern space.  
  `p`: Print lines that match the pattern.

- **`sed 's/pattern/replacement/' filename`**  
  Substitute the first occurrence of a pattern with a replacement.  
  `s/pattern/replacement/`: Substitution command.

- **`sed -i.bak 's/pattern/replacement/' filename`**  
  Edit a file in-place and create a backup with `.bak` extension.  
  `-i.bak`: Edit files in-place and save the original file as `.bak`.

- **`sed '3 s/old/new/' filename`**  
  Replace text on line 3.  
  `3`: Line number where substitution occurs.

- **`sed '3,5 s/old/new/' filename`**  
  Replace text from lines 3 to 5.  
  `3,5`: Range of lines for substitution.

- **`sed -n '3,/pattern/ p' filename`**  
  Print lines from line 3 until a pattern is matched.  
  `-n`: Suppress automatic printing.  
  `3,/pattern/`: Start from line 3 until the pattern is matched.

- **`awk '/pattern/{print $0}' filename`**  
  Print lines matching a pattern.

- **`awk '{gsub(/pattern/, "replacement")}{print}' filename`**  
  Substitute all occurrences of a pattern with a replacement.  
  `gsub(/pattern/, "replacement")`: Global substitution function in `awk`.

- **`awk 'BEGIN {print "Header"} {print} END {print "Footer"}' filename`**  
  Add text at the beginning and end of a file.  
  `BEGIN`: Code block executed before processing any lines.  
  `END`: Code block executed after processing all lines.

- **`awk -F "," '{print $1, $2}' filename`**  
  Print the first and second columns of a CSV file.  
  `-F ","`: Set field separator to comma.

- **`awk '{count[$2]++} END {print count["value"]}' filename`**  
  Count occurrences of a value in the second column.  
  `count[$2]++`: Increment count of each value in the second column.

- **`awk '{ if ($1 > 1598863888 ) {print $0} }' log.txt`**  
  Print lines where the first column is greater than a specific value.

## Additional Commands

- **`find /path -name "*.ext"`**  
  Find files with a specific extension.  
  `-name "*.ext"`: Match files with the specified extension.

- **`sort filename`**  
  Sort lines of a file.

- **`uniq filename`**  
  Remove duplicate lines from a file.

- **`diff file1 file2`**  
  Compare two files line by line.


## Contributing

Feel free to contribute to this repository by opening issues or submitting pull requests. Your contributions help improve this guide and make it more useful for others.


