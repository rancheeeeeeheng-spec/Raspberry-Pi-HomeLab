# Raspberry Pi Setup

## Introduction

The Raspberry Pi serves as the foundation of the HomeLab infrastructure. Before deploying containerized applications or network services, the operating system must be installed, configured, and secured to provide a stable environment for hosting services.

This document outlines the initial setup process, including operating system installation, remote administration, system updates, and baseline configuration. The objective is to create a lightweight, secure, and maintainable Linux server capable of supporting multiple Docker-based applications.

---

# Operating System Selection

Raspberry Pi OS Lite was selected as the operating system for this project.

Unlike the Desktop edition, Raspberry Pi OS Lite does not include a graphical user interface (GUI). This reduces system resource usage and allows more CPU and memory to be allocated to infrastructure services.

### Advantages

- Lightweight installation
- Lower memory usage
- Faster boot times
- Reduced background processes
- Optimized for server workloads
- Better resource utilization

Using a minimal operating system also encourages familiarity with Linux command-line administration, an essential skill in systems administration and DevOps.

---

# Initial Installation

The operating system was installed onto the storage device using the official Raspberry Pi imaging utility.

During installation, several initial configuration options were enabled to simplify deployment.

These included:

- Hostname configuration
- SSH enablement
- User account creation
- Regional settings
- Wireless configuration (if required)

After installation, the Raspberry Pi successfully booted into Raspberry Pi OS Lite and was connected to the local network.

---

# Remote Administration

Rather than connecting a monitor, keyboard, and mouse to the Raspberry Pi after installation, the HomeLab is managed entirely through Secure Shell (SSH).

SSH enables administrators to securely access the Linux terminal remotely over the local network.

Benefits include:

- Remote administration
- Secure encrypted communication
- Command-line access
- File management
- Software installation
- System monitoring

Using SSH reflects common industry practices where servers are typically administered remotely.

---

# System Configuration

Following installation, several basic configuration tasks were completed to prepare the operating system for hosting infrastructure services.

These tasks included:

- Updating installed packages
- Upgrading system software
- Configuring the system hostname
- Verifying network connectivity
- Confirming remote access
- Preparing the operating system for Docker installation

Performing these steps before deploying applications helps establish a stable and consistent operating environment.

---

# System Updates

Keeping Linux packages updated is an important part of maintaining a secure infrastructure.

Regular updates provide:

- Security patches
- Bug fixes
- Performance improvements
- Improved hardware compatibility
- Updated software dependencies

Routine maintenance reduces security risks while ensuring long-term system stability.

---

# Static Network Configuration

Infrastructure services require a consistent network identity so that client devices can reliably communicate with them.

For this reason, the Raspberry Pi was configured to use a static network configuration rather than relying entirely on dynamically assigned addresses.

Using a static configuration provides several advantages:

- Consistent service availability
- Reliable remote administration
- Stable service endpoints
- Simplified infrastructure documentation
- Easier troubleshooting

Future services such as DNS filtering, monitoring, and automation depend on predictable network connectivity.

---

# Directory Organization

To improve maintainability, project files are organized into a structured directory hierarchy.

The HomeLab separates:

- Docker Compose files
- Application configuration
- Documentation
- Repository metadata

Maintaining a consistent directory structure simplifies service deployment, future upgrades, and version control.

---

# Security Considerations

Although the HomeLab operates within a private environment, several security best practices were incorporated during the initial setup.

These include:

- Secure remote administration using SSH
- Minimal operating system installation
- Principle of least privilege
- Regular system updates
- Separation between operating system and application containers

As the project expands, additional security measures such as VPN access, HTTPS encryption, and centralized authentication will be introduced.

---

# Lessons Learned

The initial setup highlighted the importance of establishing a stable operating system before deploying infrastructure services.

Using Raspberry Pi OS Lite demonstrated that a graphical interface is unnecessary for server administration and that command-line management provides greater flexibility and efficiency.

The setup process also reinforced fundamental Linux administration concepts including remote access, package management, system maintenance, and network configuration.

---

# Future Improvements

Future enhancements to the Raspberry Pi environment include:

- Automated operating system updates
- Scheduled system backups
- External SSD migration
- Log management
- Resource monitoring
- Performance optimization
- Backup and disaster recovery planning

These improvements will increase reliability while preparing the HomeLab for additional services.

---

# Conclusion

The Raspberry Pi provides the foundational platform upon which the entire HomeLab infrastructure is built. A properly configured operating system ensures that future services can be deployed consistently while maintaining security, reliability, and ease of administration.

Establishing a solid Linux environment before deploying Docker containers creates a scalable foundation that supports continued experimentation and long-term infrastructure growth.
