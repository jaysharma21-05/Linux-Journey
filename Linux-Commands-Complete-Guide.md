# 🐧 Linux Commands Complete Guide

> **Your comprehensive reference for mastering Linux command line**

![LINUX](https://img.shields.io/badge/LINUX-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![BASH](https://img.shields.io/badge/BASH-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white)
![TERMINAL](https://img.shields.io/badge/TERMINAL-4D4D4D?style=for-the-badge&logo=windows-terminal&logoColor=white)

---

## 📚 Table of Contents

- [🚀 First Time on Terminal](#-first-time-on-terminal)
- [👀 Files and Directories: View](#-files-and-directories-view)
- [📝 Files and Directories: Create, Delete, Move](#-files-and-directories-create-delete-move)
- [🔍 Searching Text](#-searching-text)
- [🃏 Wildcards](#-wildcards)
- [🛠️ Utility Commands](#️-utility-commands)
- [📦 Compress and Archive](#-compress-and-archive)
- [⬇️ Downloading and Packages](#️-downloading-and-packages)
- [⚙️ Services and Systemctl](#️-services-and-systemctl)
- [🌍 Environment Variables](#-environment-variables)
- [✂️ Text Processing](#️-text-processing)
- [👥 Users and Remote Access](#-users-and-remote-access)
- [🔒 Permissions](#-permissions)
- [💾 Memory and Disk Info](#-memory-and-disk-info)
- [🖥️ System Info](#️-system-info)
- [⚡ Process Management and Jobs](#-process-management-and-jobs)
- [🌐 Networking](#-networking)
- [🔌 System Control](#-system-control)
- [👤 User and Group Management](#-user-and-group-management)
- [⏰ Scheduling and Scripting](#-scheduling-and-scripting)
- [🔥 Firewall](#-firewall)

---

## 🚀 First Time on Terminal

### 📍 pwd – Show current working directory
```bash
pwd
```
Ye command aapko bataata hai ki aap filhal kis directory mein ho.

### 🙋 whoami – Show current logged-in user
```bash
whoami
```
Ye aapka current username display karta hai.

### 📅 date – Display system date and time
```bash
date
```
Current system ka date aur time show karta hai.

### 📂 ls – List files and directories
```bash
ls
ls -l   # detailed list
ls -a   # include hidden files
ls -lh  # human-readable sizes
```
Current directory ki files aur folders list karta hai.

### ⏱️ ls -lt – List files sorted by time
```bash
ls -lt
```
Files ko modification time ke basis pe sort karke dikhata hai (latest first).

### 🧹 clear – Clear the terminal screen
```bash
clear
```
Terminal screen ko saaf kar deta hai.

---

## 👀 Files and Directories: View

### 📄 cat – Show entire file content
```bash
cat filename.txt
```
Puri file ka content terminal mein display karta hai.

### 📖 less – View file with scroll
```bash
less filename.txt
```
File ko page by page dekhne ke liye. Press `q` to quit.

### 📃 more – View file page by page
```bash
more filename.txt
```
File ko page by page view karne ke liye.

### 🔝 head – Show first lines
```bash
head -5 filename.txt
```
File ki pehli 5 lines show karta hai.

### 🔚 tail – Show last lines
```bash
tail -5 filename.txt
tail -f logfile.txt  # follow mode for live logs
```
File ki last 5 lines dikhata hai.

### 🔤 sort – Sort file lines
```bash
sort filename.txt
sort -r filename.txt  # reverse order
sort -n numbers.txt   # numeric sort
```
File ke lines ko ascending order mein sort karta hai.

### 🎯 uniq – Show unique lines
```bash
sort filename.txt | uniq
```
Duplicate lines ko remove karke unique lines dikhata hai.

### 🔢 wc – Count lines/words/characters
```bash
wc -l filename.txt  # count lines
wc -w filename.txt  # count words
wc -c filename.txt  # count characters
```

---

## 📝 Files and Directories: Create, Delete, Move

### ✨ touch – Create empty file
```bash
touch newfile.txt
touch file1.txt file2.txt file3.txt
```
Nayi empty file create karta hai ya existing file ka timestamp update karta hai.

### 🗑️ rm – Delete file
```bash
rm filename.txt
rm -i filename.txt  # interactive mode (asks confirmation)
```
**Warning:** File permanently delete ho jaati hai!

### ✏️ vi – Edit file with Vi editor
```bash
vi filename.txt
```
Press `i` for insert mode, `Esc` then `:wq` to save and quit.

### 📝 nano – Edit file with Nano editor
```bash
nano filename.txt
```
Easy-to-use text editor. `Ctrl+O` to save, `Ctrl+X` to exit.

### 📁 mkdir – Create directory
```bash
mkdir newfolder
mkdir -p parent/child/grandchild  # create nested directories
```

### 🗂️ rmdir – Remove empty directory
```bash
rmdir foldername
```
Sirf empty directory hi delete kar sakta hai.

### 💥 rm -rf – Force delete directory
```bash
rm -rf foldername
```
**Danger Zone!** Folder aur uske saare contents ko forcefully delete karta hai.

### 🚶 cd – Change directory
```bash
cd /path/to/folder
cd ..              # go one level up
cd ~               # go to home directory
cd -               # go to previous directory
```

### 📋 cp – Copy files
```bash
cp source.txt destination.txt
cp file.txt /path/to/folder/
cp -r folder1 folder2  # copy directory recursively
```

### ✂️ mv – Move or rename files
```bash
mv oldname.txt newname.txt  # rename
mv file.txt /path/to/folder/  # move
```

### ✂️ split – Split file into chunks
```bash
split -l 3 filename.txt
```
File ko 3 lines ke chunks mein todta hai.

### 🔀 shuf – Shuffle lines randomly
```bash
shuf filename.txt
```
File ke lines ko randomly shuffle karta hai.

### 🔬 cmp – Compare two files
```bash
cmp file1.txt file2.txt
```
Check karta hai ki dono files identical hain ya nahi.

### 📊 diff – Show differences
```bash
diff -u file1.txt file2.txt
```
Dono files ke beech differences dikhata hai.

### 🔎 find – Search for files
```bash
find /path -name "filename.txt"
find . -type f -name "*.log"
find /home -user jaysharma
find . -size +100M  # files larger than 100MB
```
Specific file ko search karta hai system mein.

### 🔄 updatedb – Update file index
```bash
sudo updatedb
```
File database ko update karta hai `locate` command ke liye.

### 📍 locate – Quick file search
```bash
locate filename.txt
```
Fast search using indexed database.

---

## 🔍 Searching Text

### 🔎 grep – Search for text patterns
```bash
grep "word" filename.txt
grep -i "word" file.txt  # case insensitive
grep -r "word" /path/    # recursive search in directory
grep -n "word" file.txt  # show line numbers
grep -v "word" file.txt  # invert match (lines NOT containing word)
```
File mein specific word ya pattern search karta hai.

### 🔍 egrep – Extended grep with regex
```bash
egrep 'word1|word2' filename.txt
egrep '^Start' file.txt  # lines starting with "Start"
egrep 'End$' file.txt    # lines ending with "End"
```
Multiple patterns search karne ke liye regex support ke saath.

---

## 🃏 Wildcards

### ⭐ * – Match any characters
```bash
ls file*       # all files starting with "file"
ls *.txt       # all .txt files
ls *report*    # files containing "report"
```

### ❓ ? – Match single character
```bash
ls file?.txt   # file1.txt, fileA.txt, etc.
ls ???.log     # 3-character filenames with .log
```

### 📊 {} – Brace expansion
```bash
touch file{1..5}.txt  # creates file1.txt to file5.txt
mkdir folder{A,B,C}   # creates folderA, folderB, folderC
```

---

## 🛠️ Utility Commands

### 📜 history – Command history
```bash
history
history | grep "git"  # search history
!123  # run command number 123 from history
!!    # run last command
```
Previously used commands ka list dikhata hai.

### ❓ help – Built-in help
```bash
help cd
help export
```
Shell built-in commands ka help.

### 📖 man – Manual pages
```bash
man ls
man grep
man 5 passwd  # section 5 of passwd manual
```
Detailed documentation for commands.

### 📍 which – Show command location
```bash
which python
which java
```
Command binary ka path dikhata hai.

### 🧮 bc – Calculator
```bash
bc
echo "5 + 3" | bc
echo "scale=2; 10/3" | bc  # decimal precision
```
Command line calculator.

### 📅 cal – Calendar
```bash
cal
cal 2026
cal jan 2026
```
Calendar display karta hai.

### ⏱️ uptime – System uptime
```bash
uptime
```
System kitne time se running hai, ye dikhata hai.

### 🎥 script – Record terminal session
```bash
script session.txt
# do your work
exit  # stop recording
```
Terminal session ko file mein record karta hai.

### 🔗 alias – Create command shortcuts
```bash
alias ll='ls -ltr'
alias update='sudo apt update && sudo apt upgrade'
alias ..='cd ..'
```
Command shortcuts banata hai.

---

## 📦 Compress and Archive

### 🗃️ gzip – Compress files
```bash
gzip file.txt         # creates file.txt.gz
gzip -k file.txt      # keep original file
gzip -d file.txt.gz   # decompress
```

### 📬 gunzip – Decompress
```bash
gunzip file.txt.gz
```

### 📦 tar – Archive files
```bash
# Create archive
tar -czf archive.tar.gz folder/
tar -czvf archive.tar.gz file1 file2 file3

# Extract archive
tar -xzf archive.tar.gz
tar -xzvf archive.tar.gz -C /destination/path

# List contents
tar -tzf archive.tar.gz
```
**Flags:**
- `-c` = create
- `-x` = extract
- `-z` = gzip compression
- `-f` = file
- `-v` = verbose

### 🔐 zip – ZIP compression
```bash
zip archive.zip file1.txt file2.txt
zip -r archive.zip folder/  # recursive
```

### 🔓 unzip – Extract ZIP
```bash
unzip archive.zip
unzip -l archive.zip  # list contents
unzip archive.zip -d /path/  # extract to specific path
```

---

## ⬇️ Downloading and Packages

### 🌐 wget – Download files
```bash
wget https://example.com/file.zip
wget -O custom_name.zip https://example.com/file.zip
wget -c https://example.com/large_file.iso  # resume download
```

### 🌀 curl – Transfer data
```bash
curl https://api.github.com/users/jaysharma21-05
curl -o output.html https://example.com
curl -X POST -d "data=value" https://api.example.com
```
APIs aur web requests ke liye use hota hai.

### 📥 apt – Debian/Ubuntu package manager
```bash
sudo apt update              # update package list
sudo apt upgrade             # upgrade installed packages
sudo apt install package     # install package
sudo apt remove package      # remove package
sudo apt search package      # search for package
sudo apt autoremove          # remove unused dependencies
```

### 📥 yum/dnf – RHEL/CentOS/Fedora package manager
```bash
sudo yum install httpd
sudo dnf install nginx
sudo yum remove package
sudo dnf list available
sudo dnf list installed
```

### 🔍 rpm – RPM package queries
```bash
rpm -qa                    # list all installed packages
rpm -qa | grep httpd       # check if package installed
rpm -qi httpd              # package info
rpm -ql httpd              # list package files
```

---

## ⚙️ Services and Systemctl

### ▶️ systemctl start – Start service
```bash
sudo systemctl start apache2
sudo systemctl start nginx
```

### ⏸️ systemctl stop – Stop service
```bash
sudo systemctl stop apache2
```

### 🔄 systemctl restart – Restart service
```bash
sudo systemctl restart nginx
```

### ✅ systemctl enable – Auto-start on boot
```bash
sudo systemctl enable nginx
```

### ❌ systemctl disable – Disable auto-start
```bash
sudo systemctl disable apache2
```

### 📊 systemctl status – Check service status
```bash
systemctl status nginx
```

### 📜 systemctl list-units – List services
```bash
systemctl list-units --type=service --all
systemctl list-units --type=service --state=running
```

---

## 🌍 Environment Variables

### 📝 printenv – Show environment variables
```bash
printenv
printenv PATH
printenv HOME
```

### 🔧 export – Set environment variable
```bash
export VAR_NAME="value"
export JAVA_HOME=/usr/lib/jvm/java-11
export PATH=$PATH:/new/path
```
Current session ke liye variable set karta hai.

### 📑 Permanent variables
```bash
# Add to ~/.bashrc or ~/.bash_profile for permanent variables
echo 'export JAVA_HOME=/usr/lib/jvm/java-11' >> ~/.bashrc
source ~/.bashrc
```

---

## ✂️ Text Processing

### 🔩 awk – Pattern scanning
```bash
awk '{print $1}' file.txt  # print first column
awk -F',' '{print $2}' file.csv  # CSV with comma delimiter
awk '/pattern/ {print $0}' file.txt  # print lines matching pattern
awk 'NR==5' file.txt  # print line 5
```

### ✂️ cut – Cut sections
```bash
cut -c1-5 file.txt  # characters 1 to 5
cut -f1,3 -d',' file.csv  # fields 1 and 3 with comma delimiter
cut -d':' -f1 /etc/passwd  # extract usernames
```

### 🔄 sed – Stream editor
```bash
sed 's/old/new/' file.txt  # replace first occurrence
sed 's/old/new/g' file.txt  # replace all occurrences
sed -i 's/old/new/g' file.txt  # replace in-place
sed -n '5p' file.txt  # print line 5
sed '5d' file.txt  # delete line 5
sed -n '1,10p' file.txt  # print lines 1 to 10
```

### 🔄 tr – Translate characters
```bash
tr 'a-z' 'A-Z' < file.txt  # lowercase to uppercase
tr -d '0-9' < file.txt  # delete all digits
tr -s ' ' < file.txt  # squeeze multiple spaces to one
tr '[:punct:]' ' ' < file.txt  # replace punctuation with space
```

### 📉 truncate – Resize file
```bash
truncate -s 100M file.txt  # set file size to 100MB
truncate -s 0 logfile.txt  # empty file
```

### 📝 fold – Wrap text
```bash
fold -w 80 file.txt  # wrap lines at 80 characters
echo "ABCDE" | fold -w1  # each character on new line
```

---

## 👥 Users and Remote Access

### 🔄 su – Switch user
```bash
su username
su -  # switch to root
su - username  # switch with environment
```

### 🚀 sudo – Run as superuser
```bash
sudo command
sudo apt update
sudo systemctl restart nginx
sudo -i  # interactive root shell
```

### 🚀 exit – Exit shell
```bash
exit
```

### 🌐 ssh – Secure shell
```bash
ssh user@hostname
ssh user@192.168.1.100
ssh -p 2222 user@hostname  # custom port
ssh -i ~/.ssh/key.pem user@host  # use specific key
```

### 📤 scp – Secure copy
```bash
scp file.txt user@host:/path/  # copy to remote
scp user@host:/path/file.txt .  # copy from remote
scp -r folder/ user@host:/path/  # copy directory
```

---

## 🔒 Permissions

### 📊 ls -l – List permissions
```bash
ls -l
ls -lh  # human-readable sizes
```
Output: `-rwxr-xr--`
- First character: type (`-` = file, `d` = directory, `l` = link)
- Next 3: owner permissions (rwx)
- Next 3: group permissions (r-x)
- Last 3: others permissions (r--)

### ⚙️ chmod – Change permissions
```bash
# Numeric method
chmod 755 script.sh  # rwxr-xr-x
chmod 644 file.txt   # rw-r--r--
chmod 600 private.key  # rw-------

# Symbolic method
chmod u+x script.sh  # add execute for user
chmod g-w file.txt   # remove write for group
chmod o+r file.txt   # add read for others
chmod a+rwx file.txt  # all permissions for all
```
**Permission Numbers:**
- 4 = read (r)
- 2 = write (w)
- 1 = execute (x)

### 👤 chown – Change owner
```bash
sudo chown user file.txt
sudo chown user:group file.txt
sudo chown -R user:group folder/  # recursive
```

### 👥 chgrp – Change group
```bash
sudo chgrp groupname file.txt
sudo chgrp -R groupname folder/
```

---

## 💾 Memory and Disk Info

### 💧 free – Memory usage
```bash
free
free -h  # human-readable
free -m  # in MB
```

### 📊 top – Process monitor
```bash
top
htop  # better alternative (if installed)
```
Press `q` to quit, `k` to kill process, `M` to sort by memory.

### 💾 du – Disk usage
```bash
du -sh folder/  # size of folder
du -h --max-depth=1  # size of subdirectories
du -sh *  # size of all items in current directory
```

### 💿 df – Filesystem disk space
```bash
df -h  # human-readable
df -T  # show filesystem type
df -i  # inode usage
```

---

## 🖥️ System Info

### 🏷️ hostname – System name
```bash
hostname
hostname -I  # IP addresses
```

### ⚙️ lscpu – CPU info
```bash
lscpu
```

### 💻 arch – System architecture
```bash
arch
```

### 💾 lsblk – Block devices
```bash
lsblk
lsblk -f  # show filesystem
```

### 🔍 uname – System info
```bash
uname -a  # all info
uname -r  # kernel release
uname -m  # machine architecture
```

---

## ⚡ Process Management and Jobs

### 📊 ps – Show processes
```bash
ps
ps aux  # all processes
ps -ef  # full format
ps aux | grep nginx  # find specific process
```

### 🔍 pgrep – Find process by name
```bash
pgrep nginx
pgrep -u username  # processes by user
```

### ❌ kill – Terminate process
```bash
kill PID
kill -9 PID  # force kill
kill -15 PID  # graceful termination
```

### 💥 pkill – Kill by name
```bash
pkill httpd
pkill -u username  # kill user's processes
```

### 📋 jobs – List background jobs
```bash
jobs
jobs -l  # with PID
```

### ▶️ bg – Resume in background
```bash
bg
bg %1  # resume job 1
```

### ▶️ fg – Bring to foreground
```bash
fg
fg %1  # bring job 1 to foreground
```

### ⚡ nohup – Run immune to hangup
```bash
nohup ./script.sh &
nohup python app.py > output.log 2>&1 &
```
Process ko background mein run karta hai even after logout.

---

## 🌐 Networking

### 🌐 ifconfig – Network interfaces
```bash
ifconfig
ifconfig eth0  # specific interface
ip addr show  # modern alternative
```

### 📡 ping – Test connectivity
```bash
ping google.com
ping -c 4 192.168.1.1  # send 4 packets only
```

### 🔌 telnet – Test port
```bash
telnet 192.168.1.1 80
telnet example.com 22
```

### 📊 netstat – Network statistics
```bash
netstat -tuln  # listening ports
netstat -putan | grep 80  # check port 80
netstat -r  # routing table
ss -tuln  # modern alternative
```

### 🗺️ traceroute – Trace route
```bash
traceroute google.com
traceroute 8.8.8.8
```

---

## 🔌 System Control

### 🔄 reboot – Restart system
```bash
sudo reboot
sudo reboot now
```

### ⏻️ shutdown – Shutdown system
```bash
sudo shutdown now
sudo shutdown -h now  # halt
sudo shutdown -r now  # reboot
sudo shutdown +10  # shutdown in 10 minutes
sudo shutdown -c  # cancel shutdown
```

---

## 👤 User and Group Management

### ➕ useradd – Add user
```bash
sudo useradd username
sudo useradd -m username  # create home directory
sudo useradd -m -s /bin/bash username  # specify shell
```

### 🔑 passwd – Set password
```bash
sudo passwd username
passwd  # change your own password
```

### 👥 groupadd – Add group
```bash
sudo groupadd groupname
```

### 🏷️ id – Show user/group IDs
```bash
id
id username
id -u username  # UID only
id -g username  # GID only
```

### ➖ userdel – Delete user
```bash
sudo userdel username
sudo userdel -r username  # also remove home directory
```

### ➖ groupdel – Delete group
```bash
sudo groupdel groupname
```

### 👥 usermod – Modify user
```bash
sudo usermod -aG sudo username  # add to sudo group
sudo usermod -s /bin/zsh username  # change shell
```

---

## ⏰ Scheduling and Scripting

### ⏰ at – Schedule one-time task
```bash
at 10:30 PM
at> /path/to/script.sh
at> <Ctrl+D>

atq  # list scheduled jobs
atrm 1  # remove job 1
```

### ⏰ crontab – Schedule recurring tasks
```bash
crontab -e  # edit cron jobs
crontab -l  # list cron jobs
crontab -r  # remove all cron jobs
```
**Cron format:**
```
# ╭───────── minute (0-59)
# │ ╭──────── hour (0-23)
# │ │ ╭────── day of month (1-31)
# │ │ │ ╭──── month (1-12)
# │ │ │ │ ╭── day of week (0-7, 0=Sunday)
# │ │ │ │ │
# * * * * * command
```

**Examples:**
```bash
# Run every day at 3 AM
0 3 * * * /path/to/backup.sh

# Run every hour
0 * * * * /path/to/script.sh

# Run every 5 minutes
*/5 * * * * /path/to/monitor.sh

# Run Monday to Friday at 9 AM
0 9 * * 1-5 /path/to/weekday.sh
```

### 📜 bash – Run bash script
```bash
bash script.sh
./script.sh  # if executable (chmod +x)
```

### 📝 sh – Run sh script
```bash
sh script.sh
```

---

## 🔥 Firewall

### 🛡️ firewall-cmd – Firewall management
```bash
# List all rules
sudo firewall-cmd --list-all

# Open port
sudo firewall-cmd --add-port=8080/tcp --permanent
sudo firewall-cmd --reload

# Remove port
sudo firewall-cmd --remove-port=8080/tcp --permanent
sudo firewall-cmd --reload

# List open ports
sudo firewall-cmd --list-ports

# Add service
sudo firewall-cmd --add-service=http --permanent
```

### 🔥 ufw – Uncomplicated Firewall (Ubuntu)
```bash
sudo ufw enable
sudo ufw disable
sudo ufw status
sudo ufw allow 22
sudo ufw allow 80/tcp
sudo ufw deny 3306
sudo ufw delete allow 80
```

### 🔒 iptables – Advanced firewall
```bash
sudo iptables -L  # list rules
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
sudo iptables -A INPUT -s 192.168.1.100 -j DROP
```

---

## 🎯 Pro Tips & Shortcuts

### ⌨️ Keyboard Shortcuts
```bash
Ctrl + C  # Kill current process
Ctrl + Z  # Suspend process (use 'bg' or 'fg' to resume)
Ctrl + D  # Logout / Exit
Ctrl + L  # Clear screen (same as 'clear')
Ctrl + A  # Move cursor to beginning
Ctrl + E  # Move cursor to end
Ctrl + U  # Delete from cursor to beginning
Ctrl + K  # Delete from cursor to end
Ctrl + R  # Search command history
Tab      # Auto-complete
```

### 🔗 Command Chaining
```bash
command1 && command2  # Run command2 only if command1 succeeds
command1 || command2  # Run command2 only if command1 fails
command1 ; command2   # Run both regardless
command1 | command2   # Pipe output of command1 to command2
command &             # Run command in background
```

### 📤 Redirection
```bash
command > file.txt    # Redirect output (overwrite)
command >> file.txt   # Redirect output (append)
command 2> error.txt  # Redirect errors
command &> all.txt    # Redirect both output and errors
command < input.txt   # Use file as input
```

---

## 🎓 Quick Reference Summary

| Category | Key Commands |
|---|---|
| **Navigation** | `cd`, `pwd`, `ls` |
| **File Operations** | `cp`, `mv`, `rm`, `touch`, `mkdir` |
| **View Files** | `cat`, `less`, `head`, `tail` |
| **Search** | `find`, `grep`, `locate` |
| **Permissions** | `chmod`, `chown`, `chgrp` |
| **Process** | `ps`, `top`, `kill`, `jobs` |
| **Network** | `ping`, `ssh`, `scp`, `netstat` |
| **Package** | `apt`, `yum`, `dnf`, `rpm` |
| **System** | `systemctl`, `reboot`, `shutdown` |
| **Archives** | `tar`, `gzip`, `zip`, `unzip` |

---

## 🚀 Getting Started Guide

### For Beginners:
1️⃣ Start with: `pwd`, `ls`, `cd`, `mkdir`
2️⃣ Learn file operations: `touch`, `cat`, `cp`, `mv`, `rm`
3️⃣ Understand permissions: `ls -l`, `chmod`
4️⃣ Practice text viewing: `cat`, `less`, `head`, `tail`
5️⃣ Master search: `grep`, `find`

### For Intermediate:
6️⃣ Package management: `apt` or `yum`
7️⃣ Process management: `ps`, `top`, `kill`
8️⃣ Service control: `systemctl`
9️⃣ Network basics: `ping`, `ssh`, `scp`
🔟 Text processing: `awk`, `sed`, `grep`

### For Advanced:
1️⃣1️⃣ Shell scripting with Bash
1️⃣2️⃣ Cron jobs and automation
1️⃣3️⃣ Advanced networking
1️⃣4️⃣ Firewall configuration
1️⃣5️⃣ System performance tuning

---

## 📌 Notes

✅ **Always be careful with:** `rm -rf`, `dd`, `chmod 777`
⚠️ **Use sudo wisely** - It gives root privileges
📖 **Read man pages** - `man command` for detailed info
💾 **Backup regularly** - Better safe than sorry
⌨️ **Practice in VM** - Safe environment for learning

---

## 📚 Resources

- 📘 Official Linux Documentation
- 📺 [Linux Journey Website](https://linuxjourney.com/)
- 🎓 Practice labs and sandboxes
- 💻 Real-world projects

---

## 👤 Author

**Jay Sharma**
- GitHub: [@jaysharma21-05](https://github.com/jaysharma21-05)
- Focus: Cybersecurity | Linux Administration | Automation

---

## ⭐ Star This Repo!

Agar ye guide helpful lagi, toh please ⭐ **star** kar dena!

---

🐧 **Happy Learning! Keep Practicing Linux Commands!** 🚀

---

### 📝 License

Free to use for learning and reference purposes.

---

*Last Updated: January 2026*
