# TUIN Labs — Techniki Usługowe Internetu

Lab exercises for the TUIN (Techniki Usługowe Internetu) course, built with [Containerlab](https://containerlab.dev/) and Docker.

Each lab provides a pre-configured network of lightweight Linux containers (a client workstation, web servers and a caching proxy) that students deploy on the lab VM and then explore interactively with command-line tools such as `curl` and `openssl`.

## Available Labs

| # | Branch | Topic | Status |
|---|--------|-------|--------|
| 1 | `lab1-http` | HTTP basics: requests, methods, content negotiation, caching | Released |
| 2 | `lab2-https` | HTTPS/TLS, traffic analysis, advanced caching, performance | Released |

Labs are released sequentially during the semester. When a lab becomes available, your instructor will let you know.

## Prerequisites

The labs are designed to run on a **Debian 12** virtual machine with Internet access, Docker and Containerlab.

## Quick Start

1. **Clone the repository** (first time only):

   ```bash
   cd ~
   git clone https://github.com/iplabs-it/TUIN-labs.git
   cd TUIN-labs
   ```

2. **Merge the lab branch** when your instructor announces it:

   ```bash
   git fetch
   git merge --no-edit origin/<labN-topic>
   ```

3. **Deploy the lab** using its bootstrap script:

   ```bash
   cd <lab_directory>
   ./bootstrap.sh deploy
   ```

4. **Connect to the client workstation**:

   ```bash
   ./bootstrap.sh client
   ```

5. **Destroy the lab** when done:

   ```bash
   ./bootstrap.sh destroy
   ```

## Getting the Next Lab

When the next lab is released, just fetch and merge:

```bash
cd ~/TUIN-labs
git fetch
git merge --no-edit origin/<labN-topic>
```

Each new lab adds or updates its own directory — your previous work is not affected. Labs 1 and 2 share the `http` directory: merging `lab2-https` updates it in place.

## Submission

The labs are documented in a report (PDF). The lab manual lists the questions and observations the report must cover; your instructor announces how and where to submit it.

## Useful Commands

| Action | Command |
|---|---|
| Deploy a lab | `./bootstrap.sh deploy` (in the lab directory) |
| Connect to the client | `./bootstrap.sh client` |
| Show lab status | `./bootstrap.sh status` |
| Destroy a lab | `./bootstrap.sh destroy` |
| List running containers | `docker ps` |
| Enter any container's shell | `docker exec -it clab-<lab>-<node> sh` |
| Live packet capture | `bash ../common/capture.sh clab-<lab>-<node> <iface>` |
