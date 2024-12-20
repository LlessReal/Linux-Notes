## LINUX TERMINAL (Opened via Ctrl + Alt + T)
UPDATING LINUX: sudo apt update -> sudo apt upgrade | sudo apt update && sudo apt upgrade - updates and upgrades <br>
Put sudo before a single command to do each in admin mod <br>
su makes you the super user and allows you to do multiple commands in admin <br>

apt-get downloads an advanced packaging tool or utility<br>
apt-get install wireshark is an example of how it works <br>
yum or yellowdog updater instals deletes and updates and maanages RPM packages <br>
Linux uses either yum or apt-get <br>

tar - Tape Archive (Easy to script into a backup schedule) <br>
rsync - Allows syncing files between storage devices , Instant synchronization or scheduled <br>

ip address view interface addresses <br>
ip route views the IP routing table <br>
ip address add 192.168.121.241/24 dev eth0 coonfigures the IP address of an interface <br>

code | Opens visual studio code

df or Disk Free displays info about available space on a file system and also connects a public share drive to a user’s works
df -h view human readable values of freedom space

grep or Global Regular Expression Print finds text in a file <br>
grep PATTERN/Textname [FILE] searches many files at once too <br>
grep deez auth.log <br>

dig (Domain Information Groper) - Detailed domain info (Add dig to Windows)

http://www.ics.org/downloads/bind

ps shows a list of current processes (and Process ID or PID)

Similar to the Windows Task Manager

-ps -e | more views all processes

top or table of processes views CPU, RAM, and resource utilizations and it's like the task manager for linux

It verifies file system integrity after a power outage

Process information (easy to find the highly utilized apps)

Summary of overall load (1, 5, and 15 mins)

cat or concatenate <br>
cat file1.txt file2.txt concatenates or links two files together in a series <br>
cat file1.txt file2.txt > both.txt gives the concatenated files a name <br>

nano file.txt is a full screen text editor (Included with many Linux distributions) easy to install

You can then use the controls below to do stuff with that

There's many options and you can refresh manually using enter

find . -name "file.txt"

*.txt finds all files of the file extension. and . goes in the current directory

man | brings the manual for help for specific utilities, which can be an online manual. You can use grep on the manual.

ls | Lists files in current directory | Red is an archive file and blue is a directory <br>
ls -l | more gives a longer input (q or ctrl+c to exit) <br>
ls -la | shows hidden files as well <br>

pwd |  print working directory Tells you what directory you’re currently in | pwd -P does actual physical path

mkdir foldername | Makes a new folder in home | mkdir /directories/foldername
cd | using it alone navigates to home | cd directory goes to certain directories
rm file.txt | removes a file

cp file.txt file2.txt | copies file and names the copy "file2.txt"

rm -r | directory removes directory | rm only does a file

touch file | makes new file

mv file.txt file2.txt | Renames file to file2 | having -v after mv will let you know

chmod | changes mode of a system file item <br>
chmod [mode] [file.txt] | for mode, it's formatted rwx <br>

7 - Read, Write, & Execute (rwx) <br>
6 - Read & Write (rw-) <br>
5 - Read & execute (r-x) <br>
4 - Read only (r--) <br>
3 - Write and Execute (w-x) <br>
2 - Write only (-w-) <br>
1 - Execute only (--x) <br>
0 - None (---) <br>

First digit is for user, 2nd is for group, 3rd is for others

so chmod 744 would allow rwx for users, r-- for group, and r-- for others
so -rwxr--r-- 

the first - would determine if it's a directory or not (would be d if it is a directory)

This is applied to one specific file

chmod a-w first.txt means all users have no writing to first text

chmod u+x script.exe means the owner of the file can execute the file

- disables and + enables

chown [OWNER:GROUP] file changes the ownership of a file (Ex: chown professor script.sh)

You need sudo for these commands
mv example.txt ~/directory | moves a file to a directory (also works for folders)

nano file.txt | makes new text file for editing

sudo apt install curl - makes installing easier

You open terminals on the right
