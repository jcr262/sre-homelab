# Lab Journal

## 2026-08-09

**Done**
- Multipass on KVM, 3 Ubuntu 24.04 VMs (cp, w1, w2)
- k3s cluster: 1 server, 2 server - all Ready
- Snapshots 'base' on all three nodes

**Learned**
- stdout/stderr as separate channels: why 'curl -f' matters before a pipe
- 'K3S_URL' presence is what makes the installer set up an agent instead of a server
- Snapshots are a restore point, not a save - VMs must be stopped first

**Next**
- Docker fundamentals: image vs container, layers, volumes

## 2026-08-11

**Done**
- Repo initialized: .gitignore, ReADME, journal

**Next**
- Docker: Dockerfile, volumes, 'docker exec'
