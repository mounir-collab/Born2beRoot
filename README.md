*This project has been created as part of the 42 curriculum by <manzar>.*

# System Administration Project (Virtual Machine Setup)

## Description

This project consists of setting up and configuring a secure Linux virtual machine in accordance with strict system administration guidelines.  
The primary objective is to understand the fundamentals of operating systems, virtualization, user management, security policies, and network services.

The system is deployed inside a virtual environment and configured to follow best practices in terms of security, stability, and maintainability.  
This project provides hands-on experience with Linux system installation, service configuration, firewall management, and access control mechanisms.

## Project Overview

- Operating system installation and configuration
- Secure system hardening
- User and permission management
- Firewall and security policy enforcement
- Virtualization environment usage
- Service monitoring and system maintenance

## Operating System Choice

### Chosen OS: Debian GNU/Linux

Debian was selected for this project due to its stability, long-term support, and wide community adoption.

#### Advantages of Debian
- Extremely stable and reliable
- Large package repository
- Strong community documentation
- Lightweight and efficient
- Ideal for servers and production environments

#### Disadvantages of Debian
- Older package versions compared to rolling-release distributions
- Less frequent updates for cutting-edge software

### Debian vs Rocky Linux

| Criteria        | Debian                           | Rocky Linux                      |
|-----------------|----------------------------------|----------------------------------|
| Stability       | Very high                        | Very high                        |
| Package Manager | APT                              | DNF / YUM                        |
| Community       | Very large                       | Enterprise-focused               |
| Use Case        | Servers, education, general use  | Enterprise, RHEL compatibility   |
| Updates         | Conservative                     | Enterprise-grade                 |

## Security Framework Comparison

### AppArmor vs SELinux

| Feature        | AppArmor                         | SELinux                          |
|----------------|----------------------------------|----------------------------------|
| Complexity     | Simple and readable              | Complex but powerful             |
| Configuration  | Profile-based                    | Policy-based                     |
| Learning Curve | Easy                             | Steep                            |
| Default Usage  | Debian/Ubuntu                    | Red Hat-based systems            |

**Chosen:** AppArmor  
Reason: Easier configuration, sufficient security level, and native integration with Debian.

## Firewall Configuration

### UFW vs firewalld

| Feature        | UFW                              | firewalld                        |
|----------------|----------------------------------|----------------------------------|
| Ease of Use    | Very simple                      | More complex                     |
| Backend        | iptables / nftables              | nftables                         |
| Dynamic Rules  | Limited                          | Fully dynamic                    |
| Typical Usage  | Desktop / small servers          | Enterprise environments          |

**Chosen:** UFW  
Reason: Simplicity, clarity, and sufficient control for this project scope.

## Virtualization Platform

### VirtualBox vs UTM

| Feature         | VirtualBox                       | UTM                              |
|-----------------|----------------------------------|----------------------------------|
| Host Support    | Windows, Linux, macOS            | macOS (Apple Silicon focused)    |
| Performance     | Stable and reliable              | Optimized for ARM                |
| UI & Tools      | Mature and full-featured         | Modern and simple                |

**Chosen:** VirtualBox  
Reason: Cross-platform support, strong documentation, and full compatibility with project requirements.

## System Design Choices

### Disk Partitioning
- Separate partitions for `/`, `/home`, and `swap`
- Improved security and system resilience
- Prevents user data from affecting system stability

### User Management
- Non-root user created
- `sudo` configured with limited privileges
- Strong password policy enforced

### Security Policies
- SSH configured securely
- Root login disabled via SSH
- Firewall rules restricting unused ports
- AppArmor enabled

### Installed Services
- SSH
- Sudo
- UFW
- Monitoring and basic system utilities

## Instructions

### Requirements
- VirtualBox installed
- Debian ISO image

### Installation
1. Create a new virtual machine
2. Load Debian ISO
3. Follow guided installation
4. Configure partitions manually
5. Install base system only (no GUI)

### Compilation
Not applicable (system administration project)

### Execution / Usage
- Start the virtual machine from VirtualBox
- Connect using SSH:
bash : 
ssh username@ip_address

## Resources

### Documentation and References

The following resources were used to understand and implement the concepts required for this project:

- **Debian Official Documentation**  
  https://www.debian.org/doc/  
  Reference for system installation, package management, and system administration basics.

- **Linux Manual Pages (man pages)**  
  https://man7.org/linux/man-pages/  
  Used to understand commands such as `ssh`, `sudo`, `ufw`, `systemctl`, and user management utilities.

- **AppArmor Documentation**  
  https://gitlab.com/apparmor/apparmor/-/wikis/home  
  Reference for understanding mandatory access control and security profiles.

- **UFW Documentation**  
  https://help.ubuntu.com/community/UFW  
  Used to configure and manage firewall rules.

- **VirtualBox Official Documentation**  
  https://www.virtualbox.org/manual/  
  Reference for virtual machine creation and configuration.

### AI Usage 

Artificial Intelligence tools were used **only as a learning and assistance resource**, not to automate or directly perform system configuration.

AI was used for:
- Clarifying Linux system administration concepts
- Understanding differences between operating systems and security tools
- Structuring explanations and documentation sections
- Reviewing commands and configuration logic for correctness

AI was **not used** to:
- Generate automated installation scripts
- Bypass project constraints or evaluation rules
- Perform system configuration on the virtual machine

All system setup, configuration, and validation steps were performed manually by the student in accordance with the project requirements.

## Additional Sections

### Feature List

- Installation and configuration of a secure Linux virtual machine
- User and group management with restricted privileges
- Secure SSH access configuration
- Firewall configuration and network access control
- Mandatory access control enabled
- System services monitoring and management
- Basic system hardening and security policies

### Usage Examples

- Connect to the virtual machine using SSH:
bash :
ssh username@ip_address

## Technical Choices

Operating System: Debian GNU/Linux for its stability and strong community support

Virtualization: VirtualBox for cross-platform compatibility and mature tooling

Firewall: UFW for simplicity and clear rule management

Security Module: AppArmor for readable and profile-based access control

User Management: Non-root user with controlled sudo privileges

System Configuration: Minimal installation without graphical interface to reduce attack surface