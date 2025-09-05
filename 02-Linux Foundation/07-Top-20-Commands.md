# Top 20 Linux Commands

## 1. pwd
**What:** Prints the current working directory.  
**Why:** Useful to know your location in filesystem.  
**How:**
1. pwd
/home/ubuntu

2. ls

What: Lists files & directories.
Why: To see contents of folder.
How:
ls -l
ls -a

3. cd

What: Change directory.
Why: To move around the filesystem.
How:
cd /var/log
cd ..

4. touch

What: Creates an empty file.
Why: Useful to make new files quickly.
How:

touch notes.txt

5. cat

What: Displays file content.
Why: Quick way to read files.
How:

cat notes.txt

6. nano / vi

What: Command-line text editors.
Why: To edit configuration or text files.
How:

nano notes.txt
vi notes.txt

7. mkdir

What: Make directory.
Why: To organize files into folders.
How:

mkdir projects

8. rmdir

What: Remove empty directory.
Why: To delete unused folders.
How:

rmdir projects

9. rm

What: Remove files or directories.
Why: To delete unwanted files.
How:

rm file.txt
rm -r foldername

10. cp

What: Copy files or directories.
Why: To duplicate data.
How:

cp file.txt backup.txt
cp -r folder1 folder2

11. mv

What: Move or rename files.
Why: Organize or rename files easily.
How:

mv file.txt /tmp/
mv oldname.txt newname.txt

12. find

What: Search files and directories.
Why: To quickly locate files.
How:

find /home -name "notes.txt"

13. grep

What: Search text inside files.
Why: To filter logs or config files.
How:

grep "error" /var/log/syslog

14. head

What: Show first 10 lines of a file.
Why: Preview file quickly.
How:

head notes.txt

15. tail

What: Show last 10 lines of a file.
Why: Useful for monitoring logs.
How:

tail -f /var/log/syslog

16. chmod

What: Change file permissions.
Why: To control who can read/write/execute.
How:

chmod 755 script.sh

17. chown

What: Change file owner.
Why: To assign correct ownership.
How:

sudo chown ubuntu:ubuntu notes.txt

18. ps

What: Show running processes.
Why: Monitor applications.
How:

ps aux

19. kill

What: Terminate processes.
Why: Stop stuck or unwanted programs.
How:

kill -9 1234   # process ID

20. man

What: Displays manual pages.
Why: Get help for any command.
How:
man ls
man grep


✅ These 20 commands are the foundation of Linux.
