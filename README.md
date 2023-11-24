Certainly! Here's the content in Markdown format:

## Task-1: Create a User and Add File Path

```bash
sudo useradd -u 1140 -d /var/www/rose -m rose
```

- `sudo`: Execute a command with superuser (root) privileges.
- `useradd`: Create a new user in Linux/Unix-like systems.
- `-u 1140`: Specify the numeric user ID (UID) for the new user.
- `-d /var/www/rose`: Specify the home directory for the new user.
- `-m`: Create the user's home directory if it doesn't exist.
- `rose`: Username of the new user.

## Task-2: Create a Group and Attach a User

```bash
sudo groupadd nautilus_developers
sudo useradd pary
sudo usermod -aG nautilus_developers pary
```

- `groupadd`: Command to create a new group.
- `useradd`: Command to add a new user.
- `usermod -aG`: Add a user to a supplementary group.

## Task-3: Create a Linux User with Non-Interactive Shell

```bash
sudo useradd -s /bin/false mary
```

- `-s /bin/false`: Set the login shell to a non-interactive shell.

## Task-4: Linux User Without Home

```bash
sudo useradd -M raj
```

- `-M`: Do not create a home directory for the user.

## Task-5: Linux User Expiry

```bash
sudo useradd -m -d /home/kirsty -e 2021-04-15 kirsty
sudo chage -l kirsty
```

- `-e 2021-04-15`: Set the account expiration date.

## Task-6: Linux User Files

```bash
find /home/usersdata/ -type f -user siva -exec cp --parents {} /beta \;
```

- `find`: Search for files and directories.
- `-type f`: Search for files only.
- `-user siva`: Files owned by the user "siva."
- `-exec cp --parents {} /beta \;`: Copy the files to the /beta directory while preserving the directory structure.

## Task-7: Disable Root Login

```bash
# Edit SSH configuration file
sudo vi /etc/ssh/sshd_config

# Change PermitRootLogin to no
PermitRootLogin no

# Restart SSH service
sudo systemctl restart sshd
```

## Task-8: Linux Archives

```bash
# Create compressed archive
tar -czvf rose.tar.gz /data/rose

# Copy the archive to Storage Server
cp rose.tar.gz /home
```

## Task-9: Linux File Permissions

```bash
# Set permissions for /etc/hostname
sudo chown root:root /etc/hostname
sudo chmod 644 /etc/hostname
sudo setfacl -m u:ammar:--- /etc/hostname
sudo setfacl -m u:ryan:r-- /etc/hostname
```

## Task-10: Linux Access Control List

```bash
# Set ACL for /etc/hostname
sudo setfacl -m u:ammar:--- /etc/hostname
sudo setfacl -m u:ryan:r-- /etc/hostname
sudo getfacl /etc/hostname
```

## Task-11: Linux String Substitute

```bash
# Open XML file in vi
sudo vi /root/nautilus.xml

# Replace all occurrences of "Text" with "Echo-Location"
:%s/Text/Echo-Location/g

# Save and exit vi
:wq
```

## Task-12: Linux Remote Copying

```bash
# Copy file to remote server
scp /tmp/nautilus.txt.gpg banner@stapp03:/home/opt/
```

## Task-13: Cron Schedule Deny to Users

```bash
# Edit /etc/cron.allow
sudo vi /etc/cron.allow
# Add allowed user
jim

# Edit /etc/cron.deny
sudo vi /etc/cron.deny
# Add denied user
eric
```

## Task-14: Linux Run Levels

```bash
# Check current default runlevel
sudo systemctl get-default

# Change default runlevel to graphical.target
sudo systemctl set-default graphical.target
```

## Task-15: Linux Time Zones Settings

```bash
# List available timezones
timedatectl list-timezones

# Set the timezone to America/Lime
sudo timedatectl set-timezone America/Lime

# Verify the timezone
timedatectl
```

## Task-16: NTP Server Configuration

```bash
# Install NTP
sudo yum install ntp
sudo systemctl enable ntpd

# Add NTP server to configuration
sudo vi /etc/ntp.conf
# Add: server 3.pool.ntp.org

# Do not start/restart/stop NTP manually
```

## Task-17: Linux Firewall Configuration

```bash
# Add port 6400/tcp to public zone
sudo firewall-cmd --zone=public --add-port=6400/tcp --permanent

# Reload firewall
sudo firewall-cmd --reload

# List open ports
sudo firewall-cmd --list-ports
```

## Task-18: Linux Process Limits

### Using ulimit Command (temporary limit)

```bash
# Set soft limit
ulimit -u 1024

# Set hard limit
ulimit -Hu 2024
```

### Modifying /etc/security/limits.conf (persistent limit)

```bash
# Open limits.conf file
sudo vi /etc/security/limits.conf

# Add the following lines
nfsuser soft nproc 1024
nfsuser hard nproc 2024
```
