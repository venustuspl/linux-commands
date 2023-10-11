Linux Commands Cheat Sheet

ls	Lists the content of a directory
alias	Define or display aliases
unalias	Remove alias definitions
pwd	Prints the working directory
cd	Changes directory
cp	Copies files and directories
rm	Remove files and directories
mv	Moves (renames) files and directories
mkdir	Creates directories
man	Displays manual page of other commands
touch	Creates empty files
chmod	Changes file permissions
./	Runs an executable
exit	Exits the current shell session
sudo	Executes commands as superuser
shutdown	Shutdowns your machine
htop	Displays processes and resources information
unzip	Extracts compressed ZIP files
apt, yum, pacman	Package managers
echo	Displays lines of text
cat	Prints file contents
ps	Reports shell processes status
kill	Terminates programs
ping	Tests network connectivity
vim	Efficient text editing
history	Shows a list of previous commands
passwd	Changes user password
which	Returns the full binary path of a program
shred	Overwrites a file to hide its contents
less	Inspects files interactively
tail	Displays last lines of a file
head	Displays first lines of a file
grep	Prints lines that match patterns
whoami	Outputs username
whatis	Shows single-line descriptions
wc	Word count files
uname	Displays OS information
neofetch	Displays OS and hardware information
find	Searches for files that follow a pattern
wget	Retrieves files from the internet

1. ls Command
   ls is probably the first command every Linux user typed in their terminal. It allows you to list the contents of the directory you want (the current directory by default), including files and other nested directories.

ls
It has many options, so it might be good to get some help by using the --help flag. This flag returns all the flags you can use with ls.

For example, to colorize the output of the ls command, you can use the following:

ls --color=auto
The colorized ls command.
The colorized ls command.
Now the ls command output is colorized, and you can appreciate the difference between a directory and a file.

But typing ls with the color flag would be inefficient; that’s why we use the alias command.

2. alias Command
   The alias command lets you define temporary aliases in your shell session. When creating an alias, you instruct your shell to replace a word with a series of commands.

For example, to set ls to have color without typing the --color flag every time, you would use:

alias ls="ls --color=auto"
As you can see, the alias command takes one key-value pair parameter: alias NAME="VALUE". Note that the value must be inside quotes.

If you want to list all the aliases you have in your shell session, you can run the alias command without argument.

alias
A list of aliases displayed in a fish shell.
The alias command. 3. unalias Command
As the name suggests, the unalias command aims to remove an alias from the already defined aliases. To remove the previous ls alias, you can use:

unalias ls 4. pwd Command
The pwd command stands for “print working directory,” and it outputs the absolute path of the directory you’re in. For example, if your username is “john” and you’re in your Documents directory, its absolute path would be: /home/john/Documents.

To use it, simply type pwd in the terminal:

pwd

# My result: /home/tom/Documents/linux-commands

5. cd Command
   The cd command is highly popular, along with ls. It refers to “change directory” and, as its name suggests, switches you to the directory you’re trying to access.

For instance, if you’re inside your Documents directory and you’re trying to access one of its subfolders called Videos, you can enter it by typing:

cd Videos
You can also supply the absolute path of the folder:

cd /home/tom/Documents/Videos
There are some tricks with the cd command that can save you a lot of time when playing around with it:

1. Go to the home folder
   cd
2. Move a level up
   cd ..
3. Return to the previous directory
   cd -

6) cp Command
   It’s so easy to copy files and folders directly in the Linux terminal that sometimes it can replace conventional file managers.

To use the cp command, just type it along with the source and destination files:

cp file_to_copy.txt new_file.txt
You can also copy entire directories by using the recursive flag:

cp -r dir_to_copy/ new_copy_dir/
Remember that in Linux, folders end with a forward slash (/).

7. rm Command
   Now that you know how to copy files, it’ll be helpful to know how to remove them.

You can use the rm command to remove files and directories. Be careful while using it, though, because it’s very difficult (yet not impossible) to recover files deleted this way.

To delete a regular file, you’d type:

rm file_to_copy.txt
If you want to delete an empty directory, you can use the recursive (-r) flag:

rm -r dir_to_remove/
On the other hand, to remove a directory with content inside of it, you need to use the force (-f) and recursive flags:

rm -rf dir_with_content_to_remove/
Info
Be careful with this — you can erase a whole day of work by misusing these two flags!

8. mv Command
   You use the mv command to move (or rename) files and directories through your file system.

To use this command, you’d type its name with the source and destination files:

mv source_file destination_folder/

mv command_list.txt commands/
To utilize absolute paths, you’d use:

mv /home/tom/BestMoviesOfAllTime ./
…where ./ is the directory you’re currently in.

You also can use mv to rename files while keeping them in the same directory:

mv old_file.txt new_named_file.txt 9. mkdir Command
To create folders in the shell, you use the mkdir command. Just specify the new folder’s name, ensure it doesn’t exist, and you’re ready to go.

For example, to make a directory to keep all of your images, just type:

mkdir images/
To create subdirectories with a simple command, use the parent (-p) flag:

mkdir -p movies/2004/ 10. man Command
Another essential Linux command is man. It displays the manual page of any other command (as long as it has one).

To see the manual page of the mkdir command, type:

man mkdir
You could even refer to the man manual page:

man man
The manual page of man.
The manual page of “man.” 11. touch Command
The touch command allows you to update the access and modification times of the specified files.

For example, I have an old file that was last modified on April 12th:

List command showing modifying dates of a set of files.
Old date.
To change its modification date to the current time, we need to use the -m flag:

touch -m old_file
Now the date matches today’s date (which at the time of writing was August 8th).

List command showing new date.
New date
Nonetheless, most of the time, you won’t use touch to modify file dates, but rather to create new empty files:

touch new_file_name 12. chmod Command
The chmod command lets you change the mode of a file (permissions) quickly. It has a lot of options available with it.

The basic permissions a file can have are:

r (read)
w (write)
x (execute)
One of the most common use cases for chmod is to make a file executable by the user. To do this, type chmod and the flag +x, followed by the file you want to modify permissions on:

chmod +x script
You use this to make scripts executable, allowing you to run them directly by using the ./ notation.
