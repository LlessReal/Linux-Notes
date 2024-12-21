## LINUX TERMINAL (Opened via Ctrl + Alt + T)
UPDATING LINUX: sudo apt update -> sudo apt upgrade | sudo apt update && sudo apt upgrade - updates and upgrades <br>
Put sudo before a single command to do each in admin mod 
su makes you the super user and allows you to do multiple commands in admin 

<br> code | Opens visual studio code

### Linux uses either yum or apt-get 
<br> apt-get downloads an advanced packaging tool or utility
<br> apt-get install wireshark | Instals wireshark 
<br> yum or yellowdog updater installs, deletes and updates and maanages RPM packages 
<br> sudo apt install curl - makes installing easier

## Help
<br> man | brings the manual for help for specific utilities, May be online. You can use grep on the manual.
<br> whatis [command] explains a command

<br> tar - Tape Archive (Easy to script into a backup schedule) 
<br> rsync - Allows syncing files between storage devices , Instant synchronization or scheduled 

<br> ip address view interface addresses 
<br> ip route | views the IP routing table 
<br> ip address add 192.168.121.241/24 dev eth0 coonfigures the IP address of an interface 

## System Info
<br> df or Disk Free shows info about available space on a file system and also connects a public share drive to a user’s works
<br> df -h view human readable values of freedom space
<br> dig (Domain Information Groper) - Detailed domain info (Add dig to Windows)

<br> ps shows a list of current processes (and Process ID or PID) (similar to Windows Task Manager)
<br> -ps -e | views ALL processes
<br> top or table of processes views CPU, RAM, and resource utilizations and it's like the task manager for linux
<br> It also verifies file system integrity after a power outage, and just a summary of overall load

<br> You can then use the controls below to do stuff with that
<br> There's many options and you can refresh manually using enter

## DIRECTORY
<br> find . -name "file.txt"
<br> *.txt finds all files of the file extension. and . goes in the current directory
### ls
<br> ls | Lists files in current directory | Red is an archive file and blue is a directory 
<br> ls -l | more gives a longer input (q or ctrl+c to exit) 
<br> ls -la | shows hidden files as well 

<br> pwd |  print working directory Tells you what directory you’re currently in 
<br> pwd -P | does actual physical path

## FILE MANAGEMENT
<br> mkdir foldername | Makes a new folder in home | mkdir /directories/foldername
<br> cd | using it alone navigates to home | cd directory goes to certain directories
<br> rm file.txt | removes a file
<br> rm -r directory | directory removes directory 
<br> cp file.txt file2.txt | copies file and names the copy "file2.txt"
<br> mv example.txt ~/directory | moves a file to a directory (also works for folders)
<br> mv file.txt file2.txt | Renames file to file2 | having -v after mv will let you know
<br> touch file | makes new file
<br> nano file.txt | makes new text file for editing (full screen, easy to install, is on most linux stuff)
### cat
<br> cat file1.txt file2.txt | concatenates or links two files together in a series (cat means concatenate)
<br> cat file1.txt file2.txt > both.txt | gives the concatenated files a name
### grep
<br> grep or Global Regular Expression Print finds text in a file 
<br> grep PATTERN/Textname [FILE] searches many files at once too 
<br> grep deez auth.log | Looks for "deez" in auth.log

### chmod (sudo needed for these commands)
<br> chmod [mode] [file.txt] | changes mode of a system file item  (for mode, it's formatted rwx)
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

<br> chmod a-w first.txt means ALL USERS have NO WRITING to first.txt
<br> chmod u+x script.exe means the OWNER of the file can EXECUTE the file
<br> Basically, - disables and + enables

chown [OWNER:GROUP] file changes the ownership of a file (Ex: chown professor script.sh)

<br> This is applied to one specific file

You open terminals on the right
