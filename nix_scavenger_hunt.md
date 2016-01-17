# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:* 

/home/cabox/workspace

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?* 

LICENSE  README.md  challenge_files  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*

I see more information about each file in my directory instead of just the names of the files such as the size of the files and last modification date. From reading "A Survival Guide for Unix Newbies" it seems the results are also showing me about the permissions on each file and the owner and group (although I do not completely understand what all that means).

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://linux.die.net/man/)Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*

The 'l' command (long listing format) will instruct 'ls' command to display more information for any given output, not just the name of file.  The 'a' command displays any hidden files that are not shown by the 'ls' command alone. Hidden files include any with a '.' in front of the filename.  When I ran this command three new files showed up, named ".", "..", and ".git".  The 'h' command stands for human-readable, used in combination with the 'l' command will print the sizes of the files in human readable format (example- it shows me that the total size of my directory is 36k). (*I am using CA for this assignment and I tried to use the link in the instructions above to run the 'man' command but that link wasn't working so I just looked up this information on a different website instead of actually running the commands myself*)

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*

This is what showed up when I ran 'ls /':  bin  boot  dev  etc  fastboot  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*

I typed in 'cd /' to change to the root directory.  Then ran 'pwd' and the output simply is: /

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*

I typed in 'cd ~' then 'pwd' and the output: /home/cabox

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*

I was having trouble navigating to the 'challenge_files'  directory because I didn't really understand where I was, so from /home/cabox I typed in 'ls' to list files within that directory to better orient myself.  The file name "workspace" appeared, which I recognized from the beginning, I want to get to "/home/cabox/workspace"  so I ran 'cd workspace' then 'pwd' to make sure I got there. Then from here I could 'cd challenge_files'. Then I ran 'ls *.demo' which came up with 3 files:  2015_special_stuff.demo  cloaked-wookie.demo  scooter-double-mamba.demo                                            
(I do not know why my text keeps getting automatically italicized, sorry) 

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*

I ran 'cd ..' to move up one directory to: /home/cabox/workspace                                                                                              

* Press the up arrow on your keyboard. *What just happened?*

When I press the up arrow the 'pwd' command automatically appears

* Press the up arrow a few more times. *What do you see?*

If I press the up arrow more, it shows me the previous commands I have ran (the last one I had ran was 'pwd'). I can also push the down arrow aftre hitting up a few times to navigate and see all my previous commands

* Run the `history` command. *What do you see?*

I see a list of the history of all the commands I have used so far in order. 


### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*

Username: cabox

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*

No, it doesn't show any other users.

* How long has your system been running? Use `uptime` to see, and *paste the result here:*

02:42:05 up  1:43,  1 user,  load average: 0.00, 0.00, 0.00

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*

'ps aux' seems to list all processes and their status and resource usage.
a = show processes for all users
u = display the process's user/owner
x = also show all processes not attached to a terminal (I again couldn't run 'man' using codeanywhere and that link above wasn't working, so I found this information online on unix.stackexchange.com)

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*

Typing in 'top' shows processor activity in real time. Shows listing of the top (most intensive) CPU processes and provides an interactive interface for manipulating processes


### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*

Ran 'ls *credit*' Found 2 files: credit_cards.txt  credit_cards2.txt

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*

At the top of the file it said "Last updated: 01-15-2015"

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*

This file is located in the sub-directory "tmp".  File: ./tmp/modi_laboriosam.txt  
The command I used: find . -name modi_laboriosam.txt -type f

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*

Found 2 files: Britt-Erdman.user:O'Harachester, WA 37261                                                                          
Lissie-Strosin.user:Jewessfurt, WA 00816-7241
Command I typed: grep "WA" *.user

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*

Command: grep -r "Waldo" *
File: serial-numbers/eaque_molestiae.txt
Line: Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et
 est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.
 

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*

So I made sure I was in the challenge_files directory first by running 'pwd'.  Then I typed in 'ls > files.txt' and saw it created a new files.txt file.  Next I ran 'more files.txt' and it shows a long list of mostly '.user' files inside the 'files.txt' file.

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*

I see a list of files in the challenge_files directory, that I can then hit the 'spacebar' to page down through the files, so the results are being shown in paginated format.

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*

Earlier I found out my username is: cabox.  So I ran 'ps aux | grep cabox' and the results:

root       557  0.0  0.6  63876  3492 ?        Ss   00:59   0:00 sshd: cabox [priv]                                
cabox      559  0.0  0.2  64012  1492 ?        S    00:59   0:00 sshd: cabox@pts/0                                 
cabox      560  0.0  0.3  18144  2060 pts/0    Ss   00:59   0:00 -bash                                             
root       606  0.0  0.6  63876  3340 ?        Ss   03:15   0:00 sshd: cabox [priv]                                
cabox      608  0.0  0.2  64172  1540 ?        S    03:15   0:00 sshd: cabox@notty                                 
cabox      609  0.0  0.1  12916  1020 ?        Ss   03:15   0:00 /usr/lib/openssh/sftp-server                      
cabox      618  0.0  0.2  15520  1144 pts/0    R+   03:48   0:00 ps aux                                            
cabox      619  0.0  0.1   8816   772 pts/0    S+   03:48   0:00 grep --color=auto cabox

