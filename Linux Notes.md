## LINUX TERMINAL (Opened via Ctrl + Alt + T)
UPDATING LINUX: sudo apt update -> sudo apt upgrade | sudo apt update && sudo apt upgrade - updates and upgrades <br>
Put sudo before a single command to do each in admin mod 
su makes you the super user and allows you to do multiple commands in admin 

<br> apt-get downloads an advanced packaging tool or utility
<br> apt-get install wireshark is an example of how it works 
<br> yum or yellowdog updater instals deletes and updates and maanages RPM packages 
<br> Linux uses either yum or apt-get 

tar - Tape Archive (Easy to script into a backup schedule) 
rsync - Allows syncing files between storage devices , Instant synchronization or scheduled 

<br> ip address view interface addresses 
<br> ip route views the IP routing table 
<br> ip address add 192.168.121.241/24 dev eth0 coonfigures the IP address of an interface 

code | Opens visual studio code

<br> df or Disk Free displays info about available space on a file system and also connects a public share drive to a user’s works
<br> df -h view human readable values of freedom space

<br> grep or Global Regular Expression Print finds text in a file 
<br> grep PATTERN/Textname [FILE] searches many files at once too 
<br> grep deez auth.log

dig (Domain Information Groper) - Detailed domain info (Add dig to Windows)

http://www.ics.org/downloads/bind

<br> ps shows a list of current processes (and Process ID or PID)
<br> -ps -e | more views all processes
<br> Similar to the Windows Task Manager
<br> top or table of processes views CPU, RAM, and resource utilizations and it's like the task manager for linux
<br> It also verifies file system integrity after a power outage, and just a summary of overall load

<br> cat or concatenate
<br> cat file1.txt file2.txt concatenates or links two files together in a series 
<br> cat file1.txt file2.txt > both.txt gives the concatenated files a name

You can then use the controls below to do stuff with that

There's many options and you can refresh manually using enter

find . -name "file.txt"

<br> *.txt finds all files of the file extension. and . goes in the current directory

man | brings the manual for help for specific utilities, May be online. You can use grep on the manual.
<br> whatis [command] explains a command

<br> ls | Lists files in current directory | Red is an archive file and blue is a directory 
<br> ls -l | more gives a longer input (q or ctrl+c to exit) 
<br> ls -la | shows hidden files as well 

<br> pwd |  print working directory Tells you what directory you’re currently in | pwd -P does actual physical path

mkdir foldername | Makes a new folder in home | mkdir /directories/foldername
<br> cd | using it alone navigates to home | cd directory goes to certain directories
<br> rm file.txt | removes a file
<br> rm -r directory | directory removes directory 
<br> cp file.txt file2.txt | copies file and names the copy "file2.txt"

touch file | makes new file

mv file.txt file2.txt | Renames file to file2 | having -v after mv will let you know

<br> chmod | changes mode of a system file item 
<br> chmod [mode] [file.txt] | for mode, it's formatted rwx 

7 - Read, Write, & Execute (rwx) 
<br> 6 - Read & Write (rw-) 
<br> 5 - Read & execute (r-x) 
<br> 4 - Read only (r--) <
<br> 3 - Write and Execute (w-x) 
<br> 2 - Write only (-w-) 
<br> 1 - Execute only (--x)
<br> 0 - None (---) 
<br> 1st digit = user, 2nd = group, 3rd = others

<br> so chmod 744 would allow rwx for users, r-- for group, and r-- for others OR -rwxr--r-- 
<br> the first - would determine if it's a directory or not (would be d if it is a directory)

This is applied to one specific file

chmod a-w first.txt means all users have no writing to first text
<br> chmod u+x script.exe means the owner of the file can execute the file

- disables and + enables

chown [OWNER:GROUP] file changes the ownership of a file (Ex: chown professor script.sh)

You need sudo for these commands

mv example.txt ~/directory | moves a file to a directory (also works for folders)

<br> nano file.txt | makes new text file for editing (full screen, easy to install, is on most linux stuff)
<br> sudo apt install curl - makes installing easier

You open terminals on the right
