
## Basic Commands

- `pwd`: present working directory (absolute path). = think, where am I?
- `whoami`: what user you are currently logged in as

- `ls`: list the contents of a directory
  - `ls -l`: Longlist format
  - `ls -al`: Longlist & show all files (include hidden)
  - `ls -h`: human-readable format
  - `ls /home/remy/documents`: show contents for that specific path
  
- `cd`: Change directory
  - `cd Desktop`: directory located inside this directory
  - `cd ./Desktop`: relative path - '.' (dot) = this current directory
  - `cd /home/remy/Desktop`: absolute path
  - `cd ~/Desktop`: relative path
  - `cd ..`: parent directory
  - `cd /`: change to root directory
  - `cd` or `cd ~`: change to user's home directory
  
- `clear`: clears the screen of any current commands or output

- `history`: lists terminal history of commands given 
  - `history -c`: clear terminal history
  - `.bash_history` or `$HISTFILE`: location of terminal history stored on drive
- `Up Arrow`: cycles back through previous commands given starting with the most recent
- `Ctrl + r`: reverse search history commands
- `--help` or `-h`: Basic help menu - lists options for the command and basic syntax

- `man`: basic manual for commands with common operators for its use
  - `man [command]`
  
- `info`: in-depth manual page with hyperlinks
  - `info [command]`
  
- `whatis`: one-line manual page of command
  - `whatis [command]`
  
- `Google`: When in doubt Google Dork It

## Basic Administration

- `sudo`: Superuser do OR substitute user do. Administrative privilege to operate as root (Admin) user.
  - `#`: root user
  - `sudo !!`: will run the previous command with sudo
  - `$`: standard user
- `shutdown`, `reboot`: shutdown or reboot the system
  - `shutdown`
  - `reboot`
- `apt`: advanced package tool - affectionately known as "apt"
  - `sudo apt install [package name]`
    - e.g. `sudo apt install terminator`
- `update`, `upgrade`: update system checks servers for latest patches and packages. Upgrading pulls updates from server and installs. The '-y' says ask me no questions and yes to any all install questions.
  - `sudo apt update && sudo apt upgrade -y`

## Chaining Commands

- `;` (semi-colon): commands not dependent on one another's success
  - `cd Documents; pwd; ls -l`: commands are not dependent on one another's success
- `&&` (ampersand): commands depend on success of the previous command
  - `cd Documents && pwd && ls -l`: commands depend on previous command execution success
  - `cd Documents && pwd; ls -l`: can be used together

## File Management

- `cp`: Copy (source, destination)
  - `cp [source file] [destination]` / `cp [source] [destination/newname]`
- `mkdir`: Make Directory
- `rm`: Remove files/folders
  - `rm -rf`: recursive force delete folder with contents
- `nano`: text editor
  - `Ctrl + O`: write out
  - `nano -l [filename]`: opens with line numbers
  - `Ctrl + X`: exit
  - `ALT + Shift + 3`: inside nano turns on line numbers
- `touch`: create files/update timestamps
  - `touch [filename]`
- `echo`: repeats input back to you on the terminal display
  - `echo Good Morning!`
- `cat`: concatenate - display file contents, create files
  - `cat [filename]` / `cat [file1] [file2]` / `cat -n [file]`: numbered lines

## Terminator Command Line Interface (CLI)

- `Ctrl-Shift-E`: Split the view vertically.
- `Ctrl-Shift-O`: Split the view horizontally.
- `Ctrl-Shift-W`: Close the view where the focus is on.
- `Ctrl-Shift-Q`: Exit terminator.
- `Ctrl-Alt-W`: Edit window title

## Advanced Commands

- `file`: Identify type of file by looking at file header information. Does not look at file extensions
  - `file [filename]`
- `less`: Less is more but more versatile. Display the contents of a page at a time use the spacebar, enter, or page to navigate
  - `less [filename]`
- `head`: Display first 10 lines of a file. Options allow to change the number of lines shown
  - `head -n 5 [file]`: display first five lines
- `tail`: Display last 10 lines of a file. Options allow to change the number of lines shown
  - `tail -n 5 [file]`: display last five lines
- `wc`: Calculate a file's word, line, character, or byte count
  - `wc -l [filename]`: calculate newlines      
  - `wc -w [filename]`: calculate word count
- `grep`: Global regular expression print (grep) - Search files for given pattern or word and see lines containing it
  - `grep -i "search term" [filename]`: ignore case
  - `grep -rnwi "search term" ~/Documents`: find within a directory of files
  - `-i`: case insensitive search 
  - `-w`: whole words
  - `-o`: only prints the matching parts of a line
  - `-E`: extended regex
  - `-r`: recursive through a directory
  - `-c`: count of lines found per filename
  - `-n`: print lines containing keywords

## Pipes

- `|`: Use to combine two or more commands with output from first command being used for input of next command
  - `cat [filename] | wc -l`: cats file and feeds into word count
  - `cat [filename] | grep -i "victory" | wc -w`

## Redirection

- `>`: Used for output redirection - single `>` overwrites specified destination
  - `echo this is a test > test.txt`
- `>>`: appends to specified destination
  - `cat [filename] >> test.txt`

## File Permissions

- `chmod`: change modification command 
  - `chmod +x [filename]`: add executable function
  - `chmod -x [filename]`: remove executable function
  - `chmod 777 [filename]`: change to read, write, execute for user, group, and others
  - `sudo chown -R $USER: [filename]`: change owner of specified file

## Other

- `2>/dev/null`: Device on Linux systems considered a vacuum/blackhole where standard error output can be directed to de-clutter a command's use
  - `find / -name [filename] 2>/dev/null`
- `$HISTFILE`: Variable assigned to the location of where Command Line history is saved on the hard disk. usually /home/user/.bash_history
  - `echo $HISTFILE`
- `xdg-open`: Opens a file or URL in the users preferred application (open image files or URLs from cmd line)
  - `xdg-open [file/or url]`
- `xargs`: Extended Argument deals with STDIN STDOUT issues. commonly seen in piped commands
  - `find -iname '*.log' | xargs rm`: remove all files that end in .log

## Linux File Structure

- `/`: The main or “root” directory contains the following directories/folders:
  - `/bin`: binary files used by the system
  - `/boot`: bootloader, kernel and other files needed for booting
  - `/dev`: device files
  - `/etc`: configuration files
  - `/home`: user home directories
  - `/lib`: shared libraries
  - `/media`: directory for external device mounts
  - `/mnt`: old directory for external device mounts
  - `/opt`: optional software
  - `/proc`: virtual directory used by the kernel for process management.
  - `/root`: root user’s home directory
  - `/sbin`: shared binary files
  - `/sys`: virtual directory used by kernel for data structures
  - `/tmp`: temporary directory
  - `/usr`: read-only user-specific files and binaries
  - `/var`: variable files, including logs and printer spool

### Relative Paths

- `cd ../../..`: You can be anywhere in the file system
- `cd ./Documents` or `cd Documents`: You are located in the Documents parent directory/folder

### Absolute Paths

- Always from the root `/` of the system
  - `/home/remy/Documents`
  - `/home/remy/Desktop`

### Notes

- Shortcut for `/home/username`: `~` (tilde)
  - `cd ~`  
  - `~/Documents`
- `.` (single period): this directory
- `..` (double period): Parent Directory to the current directory

## List of All Commands Covered

- `pwd`: where am I
- `whoami`: who am I
 &#8203;:citation[oaicite:0]{index=0}&#8203;
