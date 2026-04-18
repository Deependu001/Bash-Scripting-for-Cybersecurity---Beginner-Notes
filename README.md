# Bash Scripting for Cybersecurity - Beginner Notes
Beginner-friendly Bash scripting notes for cybersecurity, covering fundamentals, automation, and practical use cases.

## 📌 Introduction
Bash (Bourne Again Shell) is a command-line interpreter used in Linux systems. It is widely used in cybersecurity for automation, reconnaissance, system monitoring, and exploitation tasks.

---

## ⚙️ Basic Script Structure

```bash
#!/bin/bash

# This is a comment
echo "Hello, Cybersecurity!"
```

- `#!/bin/bash` → Shebang (defines interpreter)
- `echo` → Prints output

---

## 📂 File Permissions

```bash
chmod +x script.sh
./script.sh
```

- `chmod +x` → Makes script executable
- `./script.sh` → Runs the script

---

## 🔤 Variables

```bash
name="Deependu"
echo "Hello $name"
```

Rules:
- No spaces around `=`
- Use `$` to access variable

---

## 📥 User Input

```bash
echo "Enter your name:"
read name
echo "Welcome $name"
```

---

## 🔢 Conditional Statements

### IF Statement

```bash
if [ $1 -eq 0 ]
then
    echo "Zero"
else
    echo "Not Zero"
fi
```

### IF-ELIF

```bash
if [ $1 -gt 10 ]
then
    echo "Greater than 10"
elif [ $1 -eq 10 ]
then
    echo "Equal to 10"
else
    echo "Less than 10"
fi
```

---

## 🔁 Loops

### FOR Loop

```bash
for i in 1 2 3 4 5
do
    echo "Number: $i"
done
```

### WHILE Loop

```bash
count=1
while [ $count -le 5 ]
do
    echo "Count: $count"
    ((count++))
done
```

---

## 📂 Working with Files

```bash
if [ -f "file.txt" ]
then
    echo "File exists"
else
    echo "File not found"
fi
```

Common Flags:
- `-f` → File exists
- `-d` → Directory exists

---

## 🔍 Useful Cybersecurity Commands in Scripts

### Check Open Ports

```bash
netstat -tuln
```

### Scan Target

```bash
nmap -sV target.com
```

### Check Running Processes

```bash
ps aux
```

---

## 🛠️ Functions

```bash
function greet() {
    echo "Hello $1"
}

greet "User"
```

---

## 📊 Exit Status

```bash
echo $?
```

- `0` → Success
- Non-zero → Error

---

## 🧪 Debugging Scripts

```bash
bash -x script.sh
```

---

## 🔐 Cybersecurity Use Cases

- Automating reconnaissance
- Log monitoring
- Brute-force scripting (ethical use only)
- File integrity checks
- System audits

---

## ⚠️ Best Practices

- Always validate input
- Use comments for clarity
- Avoid hardcoding sensitive data
- Run scripts with least privilege
- Test in safe environments

---

## 📌 Example: Simple Port Scanner Script

```bash
#!/bin/bash

echo "Enter target IP:"
read ip

for port in {1..100}
do
    timeout 1 bash -c "echo >/dev/tcp/$ip/$port" 2>/dev/null &&
    echo "Port $port is open"
done
```

---

## 📚 Conclusion

Bash scripting is a powerful tool in cybersecurity that helps automate repetitive tasks, making security operations faster and more efficient.

Start small, practice daily, and build your own automation tools 🚀