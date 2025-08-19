# Ultimate Arch Linux Command Mega-Sheet

200+ Commands – Beginner → Intermediate → Advanced → Dev/Admin → Fun

---

## 📖 Linux & GNU Basics
- Linux: Kernel by Linus Torvalds (1991)
- GNU/Linux: Kernel + GNU tools (bash, coreutils, compilers)
- Kernel: Core that talks to hardware
- Shell: Command interpreter (bash, zsh, fish)
- Terminal: Window to type commands
- Distro: Linux flavor (Arch, Ubuntu, Fedora, Debian)
- Package Manager: Install, update, remove software
- FOSS: Free and Open Source Software

---

## 🟢 Beginner – Navigation & Files

**Navigation**
```
pwd          # Print current working directory
ls           # List files in current directory
ls -la       # List all files including hidden, with details
cd folder    # Change directory to 'folder'
cd ..        # Move up one directory
cd ~         # Go to home directory
tree         # Show directory tree
```

**Files & Folders**
```
mkdir myfolder              # Create a new directory
rmdir myfolder              # Remove empty directory
touch file.txt              # Create empty file
cp file.txt copy.txt        # Copy file
mv file.txt new.txt         # Move or rename file
rm file.txt                 # Delete file
rm -r folder                # Delete folder and contents
ln -s /path/file link_name  # Create symbolic link
```

**Viewing Files**
```
cat file.txt          # Display file content
less file.txt         # View file with scrolling
more file.txt         # View file page by page
head file.txt         # Show first 10 lines
tail file.txt         # Show last 10 lines
tail -f log.txt       # Follow live updates of file
wc -l file.txt        # Count number of lines
```

**Disk & System Basics**
```
df -h         # Show disk usage in human-readable format
du -sh folder # Show folder size
lsblk         # List block devices
whoami        # Show current user
id            # Show user ID and groups
uptime        # Show system uptime
uname -r      # Show kernel version
```

---

## 🟡 Intermediate – Users, Permissions, Packages, Processes

**Users & Permissions**
```
chmod 755 file          # Change permissions of a file
chown user:group file   # Change file owner and group
groups                  # Show groups of current user
sudo command            # Execute command as admin
su - user               # Switch to another user
```

**Package Management (Arch)**
```
sudo pacman -Syu        # Update system
sudo pacman -S package  # Install package
sudo pacman -R package  # Remove package
sudo pacman -Ss package # Search package in repos
sudo pacman -Qe         # List explicitly installed packages
sudo pacman -Qi package # Show package info
yay -S package          # Install from AUR
yay -R package          # Remove AUR package
yay -Syu                # Update system + AUR packages
```

**Processes & Monitoring**
```
ps aux                  # List running processes
top                     # Interactive system monitor
htop                    # Better system monitor (install first)
kill 1234               # Kill process by PID
pkill process_name      # Kill process by name
pgrep firefox           # Get PID of process by name
nice -n 10 command      # Run process with modified priority
renice -n 5 -p 1234     # Change priority of running process
```

**Networking**
```
ping google.com         # Test network connectivity
ip a                    # Show network interfaces
ip link set eth0 up     # Bring interface up
ip link set eth0 down   # Bring interface down
curl ifconfig.me        # Show public IP
wget url                # Download file from URL
scp file user@host:~    # Copy file to remote host
ssh user@host           # Connect to remote host
netstat -tulnp          # Show open ports and connections
ss -tulnp               # Modern alternative to netstat
traceroute google.com   # Trace network route
```

**Disk Management**
```
mount /dev/sdb1 /mnt    # Mount partition
umount /mnt             # Unmount partition
fdisk -l                # List partitions
parted -l               # Show partitions (GPT support)
mkfs.ext4 /dev/sdb1     # Format partition to ext4
```

---

## 🔴 Advanced – Bash, Scripting, Logs, Security

**Bash & Scripting**
```
alias ll='ls -la'         # Create shortcut
!!                        # Repeat last command
!42                       # Repeat command #42 in history
history                   # Show command history
grep "word" file.txt      # Search text in file
find / -name "file"       # Find file in filesystem
locate file.txt           # Fast search for file
xargs command             # Apply command to list of items
for i in {1..5}; do echo $i; done  # Loop example
while read line; do echo $line; done < file.txt
```

**Cron Jobs**
```
crontab -e                      # Edit cron jobs
crontab -l                      # List cron jobs
0 0 * * * /home/user/script.sh  # Run script daily at midnight
```

**Logs & Debugging**
```
journalctl -xe            # System logs
dmesg | less              # Boot messages
tail -f /var/log/syslog   # Live system log
dmesg | grep usb          # Filter kernel messages
```

**Networking & Security**
```
iptables -L               # Show firewall rules
ufw status                # Check firewall status
ufw allow 22              # Allow SSH
ufw deny 80               # Block HTTP
nmap -sP 192.168.1.0/24   # Ping scan local network
tcpdump -i eth0           # Capture packets on interface
```

**File Management Advanced**
```
rsync -av src/ dest/             # Sync folders
dd if=/dev/sda of=disk.img       # Clone disk
tar -czvf archive.tar.gz folder  # Compress folder
tar -xzvf archive.tar.gz         # Extract folder
zip file.zip file1 file2         # Create zip
unzip file.zip                   # Extract zip
```

**Kernel & System Info**
```
uname -r                   # Kernel version
lsb_release -a             # Distro info
lscpu                      # CPU info
lsblk                      # Block devices
df -h                      # Disk usage
free -h                    # Memory usage
uptime                     # System uptime
```

---

## 🚀 Development & Containers

**Git & Dev Tools**
```
git clone repo_url          # Clone repository
git status                  # Show repo status
git add .                   # Stage changes
git commit -m "msg"         # Commit changes
git push                    # Push changes
git pull                    # Pull latest changes
make                        # Run makefile
gcc program.c -o program    # Compile C program
python3 script.py           # Run Python script
```

**Docker & Containers**
```
docker ps                   # List running containers
docker images               # List Docker images
docker run hello-world      # Run test container
docker exec -it container_id bash # Open shell in container
docker stop container_id    # Stop container
docker rm container_id      # Remove container
```

---

## 🎉 Fun & Easter Eggs
```
cowsay "Linux is awesome"   # Display message in ASCII cow
fortune | cowsay            # Random quote with cow
sl                          # Steam locomotive animation
yes "Arch is the best"      # Print repeatedly until Ctrl+C
```

**Misc Useful Commands**
```
watch -n 1 command          # Repeat command every second
tldr command                # Simplified examples of command
cut -d',' -f1 file.csv      # Extract CSV column
systemctl status service    # Check service status
systemctl start service     # Start service
systemctl stop service      # Stop service
systemctl enable service    # Enable service at boot
systemctl disable service   # Disable service at boot
```

---

## 🎯 Tips
- Tab = autocomplete  
- Ctrl+C = cancel command  
- Ctrl+R = search history  
- On Arch → read the wiki daily  
- Break, fix, repeat → learn Linux  

**if you need more detail tetorial**: https://linuxjourney.com/ 

