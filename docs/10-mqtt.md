# Mosquitto MQTT

## Overview

Mosquitto MQTT is the messaging backbone of my Raspberry Pi HomeLab. It provides lightweight, publish/subscribe communication between IoT devices, Home Assistant, Node-RED, and future ESP32/M5Stick S3 projects.

---

## Objectives

- Learn MQTT messaging concepts
- Deploy Mosquitto using Docker Compose
- Secure the broker using username/password authentication
- Prepare a messaging infrastructure for future IoT projects
- Integrate with Home Assistant and Node-RED

---

## Architecture

```
ESP32 / M5Stick S3
        │
        ▼
+----------------+
| Mosquitto MQTT |
+----------------+
     │       │
     ▼       ▼
Node-RED   Home Assistant
```

---

## Directory Structure

```
homelab/
├── compose/
│   └── mqtt.yml
│
└── configs/
    └── mosquitto/
        ├── config/
        │   ├── mosquitto.conf
        │   └── passwordfile
        ├── data/
        └── log/
```

---

## Docker Compose

Container Name

- mosquitto

Image

- eclipse-mosquitto:2

Port

- 1883 (MQTT)

Volumes

- Configuration
- Data
- Logs

Restart Policy

- unless-stopped

---

## Configuration

Authentication

- Username/password enabled
- Anonymous access disabled

Persistence

- Enabled

Logging

- Docker stdout

---

## Security

Anonymous access is disabled.

Authentication is performed using a password file created with:

```bash
mosquitto_passwd
```

Only authenticated MQTT clients are allowed to publish or subscribe.

---

## Testing

Subscriber

```bash
docker exec -it mosquitto \
mosquitto_sub \
-h localhost \
-u homelab \
-P <password> \
-t test/topic \
-v
```

Publisher

```bash
docker exec -it mosquitto \
mosquitto_pub \
-h localhost \
-u homelab \
-P <password> \
-t test/topic \
-m "Hello HomeLab!"
```

Expected Result

```
test/topic Hello HomeLab!
```

---

## Troubleshooting

### Password file cannot be opened

Symptoms

```
Unable to open pwfile
```

Cause

Incorrect ownership or permissions.

Solution

```bash
sudo chown 1883:1883 passwordfile
```

---

### Broker continuously restarting

Cause

Password file missing.

Solution

Create the password file before starting the container.

---

### Authentication failed

Check

- Username
- Password
- passwordfile permissions
- mosquitto.conf

---

## Learning Outcomes

Through this project I learned:

- MQTT publish/subscribe architecture
- Docker volume mounting
- Container permissions
- Linux file ownership
- MQTT authentication
- Troubleshooting Docker containers
- Secure message broker deployment

---

## Future Improvements

- Enable MQTT over TLS
- Add ACL (Access Control Lists)
- Integrate Node-RED
- Connect Home Assistant
- Connect ESP32 devices
- Connect M5Stick S3
- Enable remote MQTT via VPN

---

## Status

✅ Completed

Date Completed

18 July 2026