# Raspberry Pi HomeLab

A self-hosted HomeLab built on a Raspberry Pi to learn Linux, Docker, networking, infrastructure monitoring, and modern system administration.

This project documents the complete journey of designing, deploying, and managing a modular HomeLab using open-source technologies. Every service is containerized using Docker and documented to demonstrate practical infrastructure skills and engineering best practices.

---

## Project Goals

This HomeLab was created to gain hands-on experience with:

- Linux system administration
- Docker & Docker Compose
- Infrastructure monitoring
- DNS services
- Networking fundamentals
- Self-hosted applications
- Infrastructure documentation
- Git & GitHub workflows

The objective is to simulate a small-scale production environment while building practical skills relevant to System Administration, DevOps, and Cloud Engineering.

---

## Technology Stack

| Category | Technology |
|----------|------------|
| Operating System | Raspberry Pi OS Lite |
| Container Platform | Docker |
| Container Management | Portainer |
| Dashboard | Homepage |
| DNS Filtering | Pi-hole |
| Monitoring | Uptime Kuma |
| IoT Messaging | Mosquitto MQTT *(Planned)* |
| Automation | Node-RED *(Planned)* |
| Home Automation | Home Assistant *(Planned)* |
| Password Manager | Vaultwarden *(Planned)* |
| Remote Access | WireGuard *(Planned)* |
| Version Control | Git & GitHub |

---

## Current Progress

### Completed

- Raspberry Pi Setup
- SSH Configuration
- Docker
- Docker Compose
- Portainer
- Homepage
- Pi-hole
- Uptime Kuma

### In Progress

- Documentation
- Infrastructure Expansion

### Planned

- Mosquitto MQTT
- Node-RED
- Home Assistant
- Vaultwarden
- WireGuard
- Reverse Proxy
- HTTPS
- Automated Backup Strategy

---

## Repository Structure

```text
Raspberry-Pi-HomeLab/
│
├── compose/              # Docker Compose files
├── configs/              # Service configurations
├── docs/                 # Technical documentation
│   ├── 01-Project-Overview.md
│   ├── 02-Hardware.md
│   ├── 03-Network-Architecture.md
│   ├── 04-Raspberry-Pi-Setup.md
│   ├── 05-Docker.md
│   ├── 06-Portainer.md
│   ├── 07-Homepage.md
│   └── 08-Pi-hole.md
│
├── README.md
├── CHANGELOG.md
└── LICENSE
```

---

## Documentation

Detailed documentation is available in the **docs/** directory.

| Document | Description |
|----------|-------------|
| Project Overview | Project objectives and architecture |
| Hardware | Hardware selection and design decisions |
| Network Architecture | Infrastructure and networking design |
| Raspberry Pi Setup | Operating system preparation |
| Docker | Containerization platform |
| Portainer | Container management |
| Homepage | Centralized service dashboard |
| Pi-hole | DNS filtering service |

---

## Design Principles

The HomeLab follows several guiding principles:

- Modular architecture
- Infrastructure as Code
- Containerized services
- Open-source technologies
- Clear documentation
- Security-conscious design
- Scalable infrastructure
- Continuous learning

---

## Roadmap

Upcoming milestones include:

- Deploy MQTT broker
- Deploy Node-RED
- Deploy Home Assistant
- Deploy Vaultwarden
- Configure WireGuard VPN
- Implement HTTPS
- Reverse Proxy
- Automated backups
- Infrastructure monitoring enhancements
- Multi-node experimentation

---

## Learning Outcomes

This project demonstrates practical experience with:

- Linux
- Docker
- Docker Compose
- DNS
- Networking
- Infrastructure Monitoring
- Git
- GitHub
- Technical Documentation
- Self-hosting

---

## License

This project is released under the MIT License.

---

## Acknowledgements

This HomeLab would not be possible without the excellent open-source community and projects including Raspberry Pi, Docker, Portainer, Pi-hole, Homepage, and Uptime Kuma.

---

**This repository is maintained as an ongoing learning project. Documentation and infrastructure will continue to evolve as additional services are deployed.**