# Home Assistant

## Overview

Home Assistant is the central automation platform within this HomeLab. It provides a unified interface to manage smart devices, monitor the home network, and create automations without relying on cloud services.

This deployment runs inside a Docker container on a Raspberry Pi 400.

---

# Objectives

- Build a self-hosted smart home platform
- Learn Home Assistant fundamentals
- Integrate IoT devices using MQTT
- Automate workflows using Node-RED
- Monitor HomeLab infrastructure
- Prepare for future ESP32 and M5Stick S3 projects

---

# Architecture

```
                 Home Assistant
                       │
      ┌────────────────┼────────────────┐
      │                │                │
  Pi-hole          MQTT Broker      Node-RED
      │                │                │
      └────────────────┼────────────────┘
                       │
                 ESP32 Devices
                       │
                  M5Stick S3
```

---

# Environment

| Item | Value |
|------|-------|
| Platform | Raspberry Pi 400 |
| OS | Raspberry Pi OS Lite |
| Container | Docker |
| Image | ghcr.io/home-assistant/home-assistant:stable |
| Network Mode | Host |
| Time Zone | Asia/Singapore |

---

# Docker Compose

```yaml
services:
  homeassistant:
    image: ghcr.io/home-assistant/home-assistant:stable
    container_name: homeassistant
    network_mode: host
    restart: unless-stopped

    volumes:
      - ../configs/homeassistant:/config
      - /etc/localtime:/etc/localtime:ro

    environment:
      TZ: Asia/Singapore
```

---

# Installation Steps

1. Create configuration directory

```bash
mkdir -p ~/homelab/configs/homeassistant
```

2. Create compose file

```
~/homelab/compose/homeassistant.yml
```

3. Deploy container

```bash
docker compose -f homeassistant.yml up -d
```

4. Verify container

```bash
docker ps
```

5. Open Web UI

```
http://<RASPBERRY_PI_IP>:8123
```

---

# Initial Configuration

- Created administrator account
- Configured location
- Set Asia/Singapore timezone
- Enabled metric units

---

# Verification

Container running

```bash
docker ps
```

Logs

```bash
docker logs homeassistant
```

Web Interface

```
http://<RASPBERRY_PI_IP>:8123
```

---

# Known Issues

## Bluetooth Warning

```
Missing NET_ADMIN and NET_RAW capabilities
```

This warning appears because Home Assistant attempts to initialise the Raspberry Pi Bluetooth adapter.

Bluetooth functionality is not required for the current HomeLab implementation and can safely be ignored.

---

# Future Integrations

- Mosquitto MQTT
- Node-RED
- ESP32
- M5Stick S3
- Zigbee Coordinator
- Matter Devices
- Grafana
- Prometheus

---

# Lessons Learned

- Home Assistant runs reliably in Docker using Host Network mode.
- Host networking allows automatic discovery of local devices.
- Persistent configuration is stored outside the container.
- Docker Compose simplifies deployment and maintenance.
- Home Assistant serves as the central automation hub for the HomeLab.

---

# References

Home Assistant Documentation

https://www.home-assistant.io/

Docker Installation Guide

https://www.home-assistant.io/installation/linux