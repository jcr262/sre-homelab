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

## 2026-08-20

**Done**
- Docker installed from official repo (apt install docker is a different package)
- Rootless usage via docker group
- hello-world running

**Learned**
- Exited means stopped, not deleted — the container still holds its filesystem and logs
- One image, many containers: each `docker run` creates a new instance
- `docker rm` removes containers, `docker rmi` removes the image

**Next**
- nginx: a container that stays running. Ports, logs, `docker exec`
- Then Dockerfile and volumes

## 2026-08-23

**Done**
- nginx container: ports, logs, `docker exec`
- Volumes: host directory mounted into the container

**Learnerd**
- nginx image has no 'ps' - images ship only what the process needs
- Inside the container nginx is PID 1; on the host it's another PID. Same process, two namespaces
- If PID 1 dies, the container dies
- Without '-v', data lives in the continainer's write layer and dies with it
- With '-v', data outlives the container - same idea as a PVC
- K8s splits what Docker does with the one flag: PVC (request), PV (storage), StorageClass (provisioner)

**Next**
- Dockerfile: build my own image, see layers
- Then PostgreSQL

## 2026-09-07

**Done**
- After completing Kubernetes course, created new folder
- Created new namespaces for public and private APIs

**Learned**
- 'k apply' needs '-f' per file: '-f .' applues a whole directory
- When apply fails on args, nothing is applied - validation happens before touching the cluster
- `--dry-run` output includes empty `spec: {}` and `status: {}` — `status` should never be in a manifest, the cluster writes it


**Next**
- Deployment and Service, written by hand (Thursday, 1.5h)

## Schedule — Phase 1 (Sep 14 – Oct 11)

- Mon 8:30pm — 45 min
- Tue 6–10pm — Terraform course
- Thu 8:30pm — 45 min
- Sat 8:30pm — 1.5 h
- Sun 8:30pm — 1.5 h

Target: 20 of 20 sessions. Minimum session = 15 min (journal + commit).
Rule: never two misses in a row.

**Learned**

- Noticed improvement opportunities to follow plan.

## 2026-10-11

**Done**
- Cluster backup, 3/3 nodes Ready. Namespaces public and private applied.
- Deployment 'n-app' written by hand, 2 replicas, scheduled across w1 and w2

**Learned**
- selector.matchLabels must match template.metadata.labels
- Scheduer spreads replicas across nodes by default
- Pod name = deployment + replicaset hash + random stuff
- Each node owns a pod IP range (10.42.1.x, 10.42.2.x)

**Next**
- Service(Oct 18)
