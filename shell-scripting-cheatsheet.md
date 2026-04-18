# 🧾 Shell Scripting Cheat Sheet (Bash)

---

# 🔹 1. Basic Script Structure

```bash
#!/bin/bash

echo "Hello World"
```

👉 `#!/bin/bash` → shebang (tells system to use bash)

---

# 🔹 2. Variables

```bash
name="Aravind"
echo $name
```

👉 No spaces around `=`
👉 Access using `$`

---

# 🔹 3. User Input

```bash
read -p "Enter your name: " name
echo "Hello $name"
```

---

# 🔹 4. If-Else Conditions

```bash
if [ "$name" == "Aravind" ]; then
    echo "Welcome"
else
    echo "User not recognized"
fi
```

👉 Space inside `[ ]` is mandatory (common mistake)

---

# 🔹 5. Numeric Conditions

```bash
num=10

if [ $num -gt 5 ]; then
    echo "Greater"
fi
```

👉 Operators:

* `-eq` → equal
* `-ne` → not equal
* `-gt` → greater
* `-lt` → less

---

# 🔹 6. Loops

### For loop

```bash
for i in 1 2 3 4 5
do
    echo $i
done
```

---

### While loop

```bash
count=1
while [ $count -le 5 ]
do
    echo $count
    ((count++))
done
```

---

# 🔹 7. Functions

```bash
greet() {
    echo "Hello $1"
}

greet Aravind
```

👉 `$1` → first argument

---

# 🔹 8. Arguments (VERY IMPORTANT)

```bash
echo $1
echo $2
echo $#
echo $@
```

👉 `$#` → number of arguments
👉 `$@` → all arguments

---

# 🔹 9. Exit Status

```bash
ls file.txt
echo $?
```

👉 `0` → success
👉 non-zero → failure

---

# 🔹 10. File Checks

```bash
if [ -f file.txt ]; then
    echo "File exists"
fi
```

👉 Common checks:

* `-f` → file exists
* `-d` → directory exists
* `-s` → not empty

---

# 🔹 11. Case Statement

```bash
read -p "Enter option: " opt

case $opt in
    start) echo "Starting";;
    stop) echo "Stopping";;
    *) echo "Invalid";;
esac
```

👉 Cleaner than multiple `if-else`

---

# 🔹 12. Redirect Output

```bash
echo "Hello" > file.txt
echo "World" >> file.txt
```

👉 `>` overwrite
👉 `>>` append

---

# 🔹 13. Command Substitution

```bash
date_today=$(date)
echo $date_today
```

👉 Store command output in variable

---

# 🔹 14. Useful Shortcuts

```bash
sleep 5
clear
history
```

---

# 🔹 15. Debugging

```bash
bash -x script.sh
```

👉 Shows step-by-step execution

---

# 🔥 Most Important for Interviews

Focus here:

```bash
if-else
loops
arguments ($1, $@)
file checks
exit codes ($?)
functions
```

---

# 🧠 Interview-Level Answers (This matters)

Instead of:
❌ “script runs commands”

Say:
✅ “Shell scripting helps automate repetitive tasks like deployments, backups, and monitoring by combining Linux commands with logic and control flow”

---

# 🔥 Real DevOps Script Examples (IMPORTANT)

---

## ✅ 1. Check if service is running

```bash
#!/bin/bash

service="nginx"

if pgrep $service > /dev/null
then
    echo "$service is running"
else
    echo "$service is not running"
fi
```

---

## ✅ 2. Disk usage alert

```bash
#!/bin/bash

usage=$(df / | grep / | awk '{print $5}' | sed 's/%//')

if [ $usage -gt 80 ]
then
    echo "Disk usage is high: $usage%"
fi
```

---

## ✅ 3. Backup script

```bash
#!/bin/bash

src="/data"
dest="/backup"

tar -czvf backup.tar.gz $src
mv backup.tar.gz $dest
```
