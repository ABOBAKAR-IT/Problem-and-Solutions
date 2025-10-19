# 🧑‍💻 Create Ubuntu User and Disable Root SSH Access

This guide explains how to create a new user named **ubuntu**, give it **sudo** privileges, and **disable SSH access for the root** user.

---

## 🚀 Steps

### 1. Create a new user
```bash
adduser ubuntu
```
👉 It will ask you to set a password and some optional information (press Enter to skip the optional fields).

### 2. Add the user to the sudo group
```bash
usermod -aG sudo ubuntu
```
👉 This allows the ubuntu user to run commands with sudo.

### 3. Verify that the user is in the sudo group
```bash
groups ubuntu
```
✅ You should see something like:
ubuntu : ubuntu sudo

### 4. Disable SSH access for the root user
Edit the SSH configuration file:
```bash
sudo nano /etc/ssh/sshd_config
```
Find these lines and modify them as follows:
```bash
PermitRootLogin no
PasswordAuthentication yes
```

👉 This disables root SSH login and allows password login for normal users (like ubuntu).
### 5. Restart the SSH service
```bash
sudo systemctl restart ssh
```

