# Born2beRoot

## Description
**Born2beRoot** is a project where I created a virtual machine and configured it to meet strict system administration requirements. The project focuses on security, server management, and setting up essential services like SSH, firewalls, and user management.

Throughout this project, I learned the fundamentals of virtualization, server setup, and applying strict security policies, including encryption and secure user access. I used Debian as the base operating system and configured the machine to run without a graphical interface, focusing purely on command-line tools.

## Features
- A virtual machine created using VirtualBox that meets security guidelines.
- Two encrypted partitions using LVM.
- SSH server running on port 4242, with root access disabled for security.
- Custom password policy:
  - Passwords expire every 30 days.
  - Minimum password length is 10 characters, with specific complexity requirements.
  - Warnings are issued 7 days before password expiration.
- UFW (or Firewalld for Rocky) firewall configured, allowing only port 4242.
- Configured `sudo` with enhanced security settings:
  - Limited to 3 incorrect attempts.
  - Logs all sudo actions in `/var/log/sudo/`.
  - Custom error messages for failed sudo commands.
- User account management:
  - A user with my login name who belongs to the `sudo` and `user42` groups.
  - Password policy applied to all users, including the root account.
  
### Monitoring Script
I developed a `monitoring.sh` script that displays critical system information every 10 minutes:
- Architecture and kernel version.
- Number of physical and virtual processors.
- Available RAM and disk space.
- CPU usage.
- Date and time of the last reboot.
- LVM status.
- Number of active connections and users.
- IP address and MAC address.
- Number of `sudo` commands executed.

The script runs at startup and broadcasts the information to all terminals using the `wall` command.

## Bonus Features
I also added the following bonuses:
- Set up a WordPress website with lighttpd, MariaDB, and PHP.
- Installed FTP service.

## Requirements
- VirtualBox for virtualization.
- Debian as the operating system.
- Knowledge of SSH, UFW/Firewalld, LVM, and bash scripting.

## External Functions
The project uses various system tools and services such as `ssh`, `sudo`, `ufw` (for Debian), and more.

## License
This project is licensed under the MIT License.
