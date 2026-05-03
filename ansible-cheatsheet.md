---

## 🔹 1. Basics

- Ansible is an **agentless automation tool**
- Uses **SSH + YAML (Playbooks)**

---

## 🔹 2. Inventory (Hosts File)

```ini
[web]
server1
server2

[db]
server3
````

---

## 🔹 3. Ad-Hoc Commands

### Ping all hosts

```bash
ansible all -m ping
```

### Run shell command

```bash
ansible all -m shell -a "uptime"
```

### Run command module

```bash
ansible all -m command -a "ls -l"
```

### Run on specific group

```bash
ansible web -m ping
```

---

## 🔹 4. File Operations

```bash
ansible all -m copy -a "src=file.txt dest=/tmp/file.txt"
ansible all -m file -a "path=/tmp/test state=directory"
```

---

## 🔹 5. Package Management

```bash
ansible all -m apt -a "name=nginx state=present"
```

---

## 🔹 6. Service Management

```bash
ansible all -m service -a "name=nginx state=started"
```

---

## 🔹 7. Playbooks

### Run playbook

```bash
ansible-playbook playbook.yml
```

### With inventory

```bash
ansible-playbook -i inventory playbook.yml
```

### Dry run (check mode)

```bash
ansible-playbook playbook.yml --check
```

### Verbose mode

```bash
ansible-playbook playbook.yml -vvv
```

---

## 🔹 8. Variables

### Define in playbook

```yaml
vars:
  package_name: nginx
```

### Pass at runtime

```bash
ansible-playbook playbook.yml -e "package_name=nginx"
```

---

## 🔹 9. Roles

```bash
ansible-galaxy init myrole
```

---

## 🔹 10. Facts (System Info)

```bash
ansible all -m setup
```

---

## 🔹 11. Inventory Commands

```bash
ansible-inventory --list
ansible-inventory --graph
```

---

## 🔹 12. Ansible Vault (Secrets)

```bash
ansible-vault create secrets.yml
ansible-vault edit secrets.yml
ansible-vault decrypt secrets.yml
```

---

## 🔹 13. Limit Execution

```bash
ansible-playbook playbook.yml --limit web
```

---

## 🔥 Most Important Commands

```bash
ansible all -m ping
ansible all -m shell
ansible-playbook
ansible-playbook --check
ansible-playbook -e
ansible-inventory
ansible-vault
```

