# 🔹 1. File & Directory Management

### List files

```bash
ls
ls -l
ls -a
```

👉 `-l` → detailed view
👉 `-a` → hidden files

---

### Change directory

```bash
cd /path/to/dir
cd ..
cd ~
```

---

### Create files & directories

```bash
touch file.txt
mkdir mydir
mkdir -p a/b/c
```

---

### Copy / Move / Delete

```bash
cp file1 file2
mv file1 file2
rm file.txt
rm -r mydir
rm -rf mydir
```

👉 ⚠️ `rm -rf` → dangerous (interviewers may ask)

---

# 🔹 2. File Viewing & Editing

```bash
cat file.txt
less file.txt
head -n 10 file.txt
tail -n 10 file.txt
tail -f logfile.log
```

👉 `tail -f` → real-time logs (VERY COMMON in DevOps)

---

# 🔹 3. Search & Text Processing

### Search files

```bash
find / -name file.txt
```

---

### Search inside files

```bash
grep "error" file.txt
grep -i "error" file.txt
grep -r "error" /var/log
```

---

### Combine commands (powerful)

```bash
ps -ef | grep tomcat
```

👉 Pipes (`|`) are important in interviews

---

# 🔹 4. Permissions (VERY IMPORTANT)

```bash
chmod 755 file.sh
chmod +x script.sh
```

👉 755 = owner (rwx), others (rx)

---

### Change ownership

```bash
chown user:group file.txt
```

---

👉 Interview question:
**“Explain chmod 777 vs 755”**

---

# 🔹 5. Process Management

```bash
ps -ef
top
htop
```

---

### Kill process

```bash
kill <pid>
kill -9 <pid>
```

👉 `-9` → force kill

---

# 🔹 6. Disk & Memory

```bash
df -h
du -sh *
free -m
```

👉 `df` → disk space
👉 `du` → directory size

---

# 🔹 7. Networking

```bash
ping google.com
ifconfig
ip a
netstat -tulnp
ss -tulnp
```

---

👉 VERY IMPORTANT:
Check which port is running:

```bash
netstat -tulnp | grep 8080
```

---

# 🔹 8. User Management

```bash
adduser username
passwd username
```

---

### Switch user

```bash
su - username
sudo su
```

---

# 🔹 9. Package Management (Ubuntu/Debian)

```bash
sudo apt update
sudo apt upgrade
sudo apt install nginx
sudo apt remove nginx
```

---

# 🔹 10. Archives & Compression

```bash
tar -cvf file.tar dir/
tar -xvf file.tar
tar -czvf file.tar.gz dir/
tar -xzvf file.tar.gz
```

---

# 🔹 11. System Info

```bash
uname -a
uptime
whoami
hostname
```

---

# 🔹 12. Logs (REAL-WORLD USE)

```bash
tail -f /var/log/syslog
journalctl -u nginx
```

👉 Debugging production issues

---

# 🔥 Most Important Commands (Focus These)

If interviewer tests you:

```bash
ls
cd
grep
find
chmod
ps
kill
df
du
tail -f
netstat / ss
```

---

# 🧠 Interview-Level Answers (Game Changer)

Instead of:
❌ “grep searches text”

Say:
✅ “grep is used to filter logs or files for specific patterns, often combined with pipes for real-time debugging”

---
