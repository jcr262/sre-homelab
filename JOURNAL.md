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

## 2026-08-18

**Done**
- Repo initialized: .gitignore, ReADME, journal
- Renamed branch to main, set as global default
- Configured git identity with GitHub noreply email
- SSH key (ed25519) generated and added to GitHub
- Remote connected, first push done

**Learned**
- `git add` stages, `git commit` snapshots what's staged — two steps on purpose
- The commit message is free text; `add` is a convention, not a command
- Public key is meant to be shared; the private one never leaves the machine

**Next**
- Docker: Dockerfile, volumes, 'docker exec'
