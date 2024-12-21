# Common Terminal Commands

## Key Commands & Navigation

Before we look at some common commands, I just want to note a few keyboard commands that are very helpful:

- `Up Arrow`: Will show your last command
- `Down Arrow`: Will show your next command
- `Tab`: Will auto-complete your command
- `Ctrl + L`: Will clear the screen
- `Ctrl + C`: Will cancel a command
- `Ctrl + R`: Will search for a command
- `Ctrl + D`: Will exit the terminal

## Manual Command

On Linux and Mac, the `man` command is used to show the **manual** of any command that you can run in the terminal. So if you wanted to know more about the `ls` command, you could run:

```bash
  man ls
```

Unfortunately, if you are on Windows and using Git Bash, the `man` command is not included, however, you can just type the command that you want to know more about and then `--help` and you will get similar info:

```bash
  ls --help
```

You should be able to use the arrow keys or page up and down. When you are ready to exit, just press `q`.

## The `whoami` Command

The `whoami` command will show you the current user that you are logged in as.

```bash
  whoami
```

## The `date` Command

Another really simple one is the `date` command, which, surprise, will show you the current date and time.

```bash
  date
```

## File System Navigation

Commands to navigate your file system are very important. You will be using them all the time. You won't remember every single command that you use, but these are the ones that you should remember.

| Command                             | Description                                                                       |
| ----------------------------------- | --------------------------------------------------------------------------------- |
| pwd                                 | Lists the path to the working directory                                           |
| ls                                  | List directory contents                                                           |
| ls -a                               | List contents including hidden files (Files that begin with a dot)                |
| ls -l                               | List contents with more info including permissions (long listing)                 |
| ls -r                               | List contents reverse order                                                       |
| cd                                  | Change directory to home                                                          |
| cd [dirname]                        | Change directory to specific directory                                            |
| cd ~                                | Change to home directory                                                          |
| cd ..                               | Change to parent directory                                                        |
| cd -                                | Change to previous directory (which could be different than the parent of course) |
| find [dirtosearch] -name [filename] | Find location of a program                                                        |

Of course, you can group flags together. For example, if I want to see more info and view hidden files, I could do `ls -l -a` and even shorten it to `ls -la`.

## Opening a Folder or File

If you want to open a file or a folder in the GUI from your terminal, the command is different depending on the OS.

Mac - `open [dirname]`
Windows - `start [dirname]`
Linux - `xdg-open [dirname]`

You can open folders, files and even URLs

```bash
  open https://traversymedia.com
```

## Modifying Files & Directories

| Command                     | Description                                         |
| --------------------------- | --------------------------------------------------- |
| mkdir [dirname]             | Make directory                                      |
| touch [filename]            | Create file                                         |
| rm [filename]               | Remove file                                         |
| rm -i [filename]            | Remove directory, but ask before                    |
| rm -r [dirname]             | Remove directory                                    |
| rm -rf [dirname]            | Remove directory with contents                      |
| rm ./\*                     | Remove everything in the current folder             |
| cp [filename] [dirname]     | Copy file                                           |
| mv [filename] [dirname]     | Move file                                           |
| mv [dirname] [dirname]      | Move directory                                      |
| mv [filename] [filename]    | Rename file or folder                               |
| mv [filename] [filename] -v | Rename Verbose - print source/destination directory |

We can also do multiple commands at once with the `&&` operator:

```bash
cd test2 && mkdir test3
```

## Right angle bracket >

This symbol tells the system to output results into whatever you specify next. The target is usually a filename. You can use this symbol by itself to create a new file:

```bash
> [filename]
```

When you are done, hit `ctrl+D`

## The `cat` (concatenate) Command

The cat command is a very common command and allows you to create single or multiple files, view content of a file, concatenate files and redirect output in terminal or files.

The most common thing I use it for is to display the contents of a file:

```bash
  cat [filename]
```

You can also view the contents of multiple files:

```bash
  cat [filename] [filename]
```

You can also create a file using the `cat` command:

```bash
  cat > [filename]
```

This will open up a new file and you can start typing. When you are done, you can press `Ctrl + D` to save and exit.

You can also append to a file:

```bash
  cat >> [filename]
```

This will open up the file and you can start typing. When you are done, you can press `Ctrl + D` to save and exit.

You can use it to show line numbers:

```bash
  cat -n [filename]
```

There are other uses as well, but as you can see, the `cat` command is very powerful.

## The `less` Command

The `less` command is used to view the contents of a file. It is similar to the `cat` command, but it allows you to scroll up and down.

```bash
  less [filename]
```

To exit the `less` command, just press `q`.

## The `echo` Command

The `echo` command is used to display messages, or to create and write to files. It is similar to the `cat` command, but it is used to display a single line of text.

```bash
  echo "Hello World"
```

You can also use it to create a file:

```bash
  echo "Hello World" > [filename]
```

You can also append to a file:

```bash
  echo "Hello World" >> [filename]
```

## The `nano` Command

The `nano` command is a text editor that is installed by default on most Linux distributions, MacOS and you can even use it with Git Bash on Windows. It is very similar to the `vim` editor, but it is much easier to use.

You can open an existing file to edit or create a new file and open it with:

```bash
  nano [filename]
```

When you're ready to exit, just hit `Ctrl + X` and then `Y` to save and `N` to not save.

## The `head` and `tail` Commands

The `head` command is used to output the first part of files. By default, it outputs the first 10 lines of each file. You can also specify the number of lines to output.

```bash
  head [filename]
```

You can also specify the number of lines to output:

```bash
  head -n 5 [filename]
```

The `tail` command is used to output the last part of files. By default, it outputs the last 10 lines of each file. You can also specify the number of lines to output.

```bash
  tail [filename]
```

You can also specify the number of lines to output:

```bash
  tail -n 5 [filename]
```

## The `grep` Command

The `grep` command is used to search for a text pattern in a file. It is very powerful and can be used to search for a string or regular expression in a file or set of files.

```bash
  grep [searchterm] [filename]
```

You can also search for a string in multiple files:

```bash
  grep [searchterm] [filename] [filename]
```

There are a lot more things that you can do with the `grep` command, but it's a but more advanced.

## The `find` command

The `find` command is extremely powerful and is used to find the location of files and directories based on conditions that you specify.

To start off by creating something to work with. Let's create 100 files in the current directory. This is one of those things that I talked about earlier where you can do certain things much faster than you could in the GUI. We already know that the `touch` command will create a file. It can also be used to create multiple files.

```bash
  touch file-{001..100}.txt
```

Now we have 100 .txt files in the current directory. Something that would have taken a lot longer to do in the GUI.

Let's do something very simple and find a specific file. The format looks like this:

```bash
  find [dirname] -name [filename]
```

Let's find the file called `file-001.txt`:

```bash
  find . -name "file-001.txt"
```

This will look in the current directory, which is represented with a dot.

We can look in other directories as well. Let's create a file in our home folder called test.txt

```
  touch ~/test.txt
```

To find that file:

```bash
  find ~/ -name "test.txt"
```

We can look for files that match a certain pattern as well. Let's find all files that start with `file-`:

```bash
  find . -name "file-*"
```

We can search for files that are empty:

```bash
  find . -empty
```

Let's append some text to the file `file-002.txt`. We could use the `cat` command, like I showed you earlier, but we can also use the `echo` command:

```bash
  echo "Hello World" >> file-002.txt
```

Now if we find the empty files again, we will see that `file-002.txt` is no longer empty:

```bash
  find . -empty
```

We can remove all of the files that we created with this command:

```bash
  find . -name "file-*" -delete
  rm -f file-* # This will also work
```

There is so much more that you can do with the `find` command, but it goes beyond the scope of this tutorial.

## File Compression

`tar` is a program for concatenating multiple files into one big file called a **tarball** and reversing this process by extracting the files from the tarball.

| Command                             | Description                |
| ----------------------------------- | -------------------------- |
| tar czvf [dirname].tar.gz [dirname] | Create tarball             |
| tar tzvf [dirname]                  | See what is in the tarball |
| tar xzvf [dirname].tar.gz           | Extract tarball            |

- -c : Creates Archive 
- -x : Extract the archive 
- -f : creates archive with given filename 
- -t : displays or lists files in archived file 
- -u : archives and adds to an existing archive file 
- -v : Displays Verbose Information 
- -A : Concatenates the archive files 
- -z : zip, tells tar command that creates tar file using gzip 
- -j : filter archive tar file using tbzip 
- -W : Verify a archive file 
- -r : update or add file or directory in already existed .tar file 

## The `history` Command

Used to display the history of commands that you have run.

```bash
  history
```

You can also use the `!` to run a command from the history.

```bash
  !100
```

This will run the command that is in the 100th position in the history.


# Pipelining and Redirection in the Terminal

## Pipelining

Pipelining is a powerful feature in the terminal that allows you to connect multiple commands together. The pipe (`|`) symbol is used to pass the output of one command as the input to another.

### What is Pipelining?

Pipelining allows the output of one command to be used as input for another command. This can help streamline workflows by allowing multiple operations to be performed without intermediate files.

### Syntax
```bash
command1 | command2 | command3
```

- `command1`: The first command, which generates some output.
- `command2`: The second command that receives the output of `command1` as input and processes it.
- `command3`: Another command that receives the output of `command2`.

### Examples

1. **Viewing file contents with `cat` and `grep`**
   ```bash
   cat file.txt | grep "keyword"
   ```
   - `cat file.txt` outputs the contents of `file.txt`.
   - `grep "keyword"` filters the output, displaying lines that contain "keyword".

2. **Listing files and searching for specific ones**
   ```bash
   ls -l | grep ".txt"
   ```
   - `ls -l` lists files with detailed information.
   - `grep ".txt"` filters the list to only show files with the `.txt` extension.

3. **Sorting the output of a command**
   ```bash
   ps aux | sort -k 3 -n
   ```
   - `ps aux` shows all running processes.
   - `sort -k 3 -n` sorts the output by the third column (CPU usage).

4. **Counting lines of output from a command**
   ```bash
   cat file.txt | wc -l
   ```
   - `cat file.txt` outputs the contents of `file.txt`.
   - `wc -l` counts the number of lines in the file.

### Benefits of Pipelining

- **Efficiency**: You can chain commands together, reducing the need for intermediate files.
- **Flexibility**: Multiple commands can be combined to perform complex tasks in a single line.
- **Clarity**: Using pipes can make your commands more readable and modular.

## Redirection

Redirection is the process of changing the default input/output behavior of commands. By default, commands read from standard input (keyboard) and write to standard output (screen). Redirection allows you to send input/output to files or other commands.

### Types of Redirection

1. **Output Redirection (`>`)**
   - Redirects the output of a command to a file, overwriting the file if it already exists.
   - Example:
     ```bash
     echo "Hello, World!" > output.txt
     ```
     - This writes the string "Hello, World!" to `output.txt`, overwriting the file if it exists.

2. **Append Output (`>>`)**
   - Appends the output of a command to a file instead of overwriting it.
   - Example:
     ```bash
     echo "Another line" >> output.txt
     ```
     - This appends "Another line" to `output.txt`.

3. **Input Redirection (`<`)**
   - Redirects input from a file to a command.
   - Example:
     ```bash
     sort < input.txt
     ```
     - This takes the contents of `input.txt` as input for the `sort` command.

4. **Error Redirection (`2>`)**
   - Redirects error messages to a file.
   - Example:
     ```bash
     ls non_existing_directory 2> error.txt
     ```
     - This writes the error message to `error.txt` if the directory doesn't exist.

5. **Redirecting Both Output and Error (`&>`)**
   - Redirects both standard output and error to a file.
   - Example:
     ```bash
     ls valid_dir invalid_dir &> output_and_error.txt
     ```
     - This writes both the output and errors to `output_and_error.txt`.

### Combining Redirection and Pipelining

You can combine redirection and pipelining to create more complex workflows. For example, you can use pipelining to process data and then redirect the output to a file.

Example:
```bash
ps aux | sort -k 3 -n > sorted_processes.txt
```
- This command lists all processes, sorts them by CPU usage, and saves the output to `sorted_processes.txt`.

### Conclusion

Pipelining and redirection are essential tools in the terminal that enable efficient data processing and manipulation. Pipelining allows you to chain commands, while redirection controls where input/output is sent. By combining both, you can streamline your workflows and make your terminal usage more powerful.


