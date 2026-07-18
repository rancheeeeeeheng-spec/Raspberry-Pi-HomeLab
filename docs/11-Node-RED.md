# 11. Node-RED

## 11.1 Introduction

### Purpose
- Introduce Node-RED as the automation engine used in the HomeLab.
- Explain how it connects different services without writing large amounts of code.
- Describe its role between MQTT and Home Assistant.

### Learning Objectives
- Understand flow-based programming.
- Deploy Node-RED using Docker.
- Connect Node-RED with Home Assistant.
- Connect Node-RED with Mosquitto MQTT.
- Build simple automations.

---

## 11.2 What is Node-RED?

### Definition
- Open-source flow-based programming platform.
- Originally developed by IBM.
- Browser-based editor.
- Uses drag-and-drop nodes instead of traditional programming.

### Key Features
- Visual programming
- MQTT support
- REST API support
- Home Assistant integration
- Large community node library

---

## 11.3 Why Node-RED?

### Benefits
- Rapid automation development
- Easy debugging
- Low-code approach
- Easy integration between multiple services
- Suitable for IoT applications

### Why it was selected
- Native MQTT support
- Excellent Home Assistant integration
- Runs efficiently on Raspberry Pi
- Docker deployment
- Large community support

---

## 11.4 Architecture

### Components

- Home Assistant
- Node-RED
- Mosquitto MQTT
- IoT Devices (ESP32 / M5Stick)
- Dashboard

### Workflow

ESP32
↓
Mosquitto MQTT
↓
Node-RED
↓
Home Assistant
↓
Dashboard

---

## 11.5 Docker Deployment

### Image

nodered/node-red:latest

### Container

- Persistent storage
- Restart policy
- Port mapping
- Time zone configuration

### Directory

configs/
└── nodered/
    └── data/

---

## 11.6 Home Assistant Integration

### Steps

- Install Home Assistant WebSocket nodes
- Generate Long-Lived Access Token
- Configure Home Assistant server
- Verify successful connection

### Authentication

- Long-Lived Access Token
- HTTP connection
- Server validation

---

## 11.7 MQTT Integration

### Broker

Mosquitto

### Authentication

- Username
- Password

### Test Topic

test/topic

### Testing

MQTT Publisher
↓

Node-RED MQTT Input
↓

Debug Node

---

## 11.8 First Automation

### Scenario

Home Assistant Helper

↓

State Changed

↓

Debug Node

### Result

- Trigger received
- Payload displayed
- Automation verified

---

## 11.9 Troubleshooting

Examples

- Home Assistant Disabled
- Missing Access Token
- Docker network mismatch
- Empty Entity List
- MQTT Authentication Failure

Explain

Problem

Cause

Solution

for each issue.

---

## 11.10 Learning Outcomes

By completing this chapter:

- Understand flow-based programming
- Deploy Node-RED in Docker
- Connect Home Assistant
- Connect MQTT
- Create automation flows
- Debug automation events

---

## 11.11 Future Expansion

Future projects

- ESP32 sensors
- Smart switch
- Motion detection
- Environmental monitoring
- Smart home dashboard
- AI-assisted automation