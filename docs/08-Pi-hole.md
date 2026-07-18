# Pi-hole

## Introduction

As more devices connect to modern networks, advertisements, trackers, and malicious domains generate unnecessary traffic while raising privacy and security concerns. Instead of relying on browser-based ad blockers, network-wide DNS filtering provides a centralized solution that protects every compatible device connected to the network.

Pi-hole was deployed as the first infrastructure service within the HomeLab to provide DNS-based filtering. By acting as the network's DNS server, Pi-hole blocks requests to known advertising, tracking, and malicious domains before a connection is established. This approach improves browsing performance, enhances privacy, and provides greater visibility into DNS activity across the network.

This document describes the purpose of Pi-hole, its role within the HomeLab, and the benefits of integrating DNS filtering into a self-hosted infrastructure.

---

# What is Pi-hole?

Pi-hole is an open-source DNS sinkhole that filters unwanted domain requests at the network level.

Instead of blocking advertisements within individual browsers, Pi-hole intercepts DNS queries and determines whether a requested domain should be allowed or blocked.

Pi-hole provides:

- Network-wide advertisement blocking
- Tracker blocking
- Malware domain filtering
- DNS query logging
- Custom blocklists
- DNS analytics
- Local DNS capabilities

Because filtering occurs before a connection is made, compatible client devices benefit without requiring additional browser extensions or software.

---

# Why Pi-hole?

Pi-hole was selected because it provides an effective and lightweight DNS filtering solution that complements the HomeLab's infrastructure objectives.

Key advantages include:

- Network-wide protection
- Improved browsing experience
- Reduced unnecessary network traffic
- Enhanced privacy
- Visibility into DNS activity
- Lightweight resource usage
- Simple Docker deployment

Deploying Pi-hole also introduces practical experience with DNS services, one of the most fundamental components of modern networking.

---

# Role Within the HomeLab

Pi-hole serves as the dedicated DNS filtering service for the HomeLab.

Its responsibilities include:

- Processing DNS requests
- Blocking known advertising domains
- Filtering tracking services
- Logging DNS activity
- Forwarding legitimate requests to upstream DNS providers
- Supporting future local DNS records

Pi-hole integrates with other infrastructure services while remaining independent through Docker containerization.

---

# Architecture

The DNS resolution process follows the workflow below.

```
             Client Device
                    │
              DNS Request
                    │
               Pi-hole Server
        ┌───────────┴───────────┐
        │                       │
   Blocked Domain         Allowed Domain
        │                       │
        ▼                       ▼
 Request Blocked        Upstream DNS Provider
                                │
                                ▼
                        DNS Response Returned
                                │
                                ▼
                           Client Device
```

Every DNS request passes through Pi-hole before reaching an upstream DNS provider. If the requested domain appears on a configured blocklist, the request is denied. Otherwise, the request is resolved normally.

---

# DNS Filtering Process

The filtering workflow consists of several stages.

### Step 1

A client device requests the address of a domain.

### Step 2

The request is sent to Pi-hole.

### Step 3

Pi-hole compares the domain against configured blocklists.

### Step 4

If the domain is blocked, Pi-hole prevents the connection.

### Step 5

If the domain is allowed, the request is forwarded to the configured upstream DNS provider.

### Step 6

The resolved address is returned to the client device.

This process is transparent to users and typically completes within milliseconds.

---

# Dashboard Features

Pi-hole provides a comprehensive web interface for monitoring DNS activity.

The dashboard includes:

- DNS query statistics
- Blocked query statistics
- Top requested domains
- Top blocked domains
- Client activity
- Query logs
- Blocklist management
- System status

These features provide valuable insight into network behavior and DNS usage.

---

# Integration with the HomeLab

Pi-hole integrates with several other HomeLab services.

## Homepage

Homepage provides centralized access to the Pi-hole administration interface.

This allows administrators to monitor DNS activity alongside other infrastructure services from a single dashboard.

---

## Uptime Kuma

Pi-hole is monitored using Uptime Kuma to verify service availability.

Monitoring includes:

- DNS service availability
- Web interface availability
- Infrastructure health monitoring

Centralized monitoring helps identify service interruptions before they impact users.

---

## Docker

Pi-hole operates inside its own Docker container.

Containerization provides:

- Service isolation
- Simplified updates
- Easy recovery
- Consistent deployment
- Persistent configuration through Docker volumes

This approach aligns with the modular design philosophy used throughout the HomeLab.

---

# Benefits to the HomeLab

Deploying Pi-hole provides several operational advantages.

### Privacy

Blocks many tracking domains before communication occurs.

### Security

Prevents access to numerous known malicious domains.

### Performance

Reduces unnecessary DNS traffic and unwanted content requests.

### Centralized Management

One DNS service protects multiple compatible client devices.

### Learning Opportunity

Provides practical experience with DNS, network services, and infrastructure monitoring.

---

# Best Practices

Several best practices are followed when maintaining Pi-hole.

- Keep blocklists updated
- Review DNS query logs regularly
- Remove obsolete blocklists
- Document configuration changes
- Monitor service availability
- Maintain Docker volume backups
- Update container images regularly

Following these practices improves reliability while maintaining effective DNS filtering.

---

# Lessons Learned

Deploying Pi-hole demonstrated how a lightweight DNS service can significantly improve both network visibility and user experience.

The project reinforced fundamental networking concepts including DNS resolution, upstream DNS forwarding, domain filtering, and centralized infrastructure management. It also highlighted the advantages of containerizing infrastructure services using Docker.

Integrating Pi-hole with Homepage and Uptime Kuma further demonstrated the benefits of combining multiple self-hosted services into a cohesive infrastructure platform.

---

# Future Improvements

Future enhancements planned for the Pi-hole deployment include:

- Local DNS records
- Conditional DNS forwarding
- Redundant DNS servers
- High-availability deployment
- Additional curated blocklists
- Improved DNS analytics
- Integration with future network services

These enhancements will improve resilience while expanding the HomeLab's networking capabilities.

---

# Conclusion

Pi-hole represents the HomeLab's first core infrastructure service and introduces practical experience with DNS management, network security, and centralized service administration.

By combining Pi-hole with Docker, Homepage, and Uptime Kuma, the HomeLab demonstrates how lightweight open-source technologies can be integrated into a reliable and scalable infrastructure. The deployment also establishes a strong networking foundation for future services such as automation, remote access, and home automation.