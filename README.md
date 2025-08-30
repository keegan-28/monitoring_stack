# WATCHTOWER - Raspberry Pi Monitoring Stack Deployment (Ansible)

> Includes: Docker, Grafana, InfluxDB, and Prometheus — all deployed via Docker Compose.

---

## Set up Passwordless SSH

From your **laptop**:

```bash
ssh-copy-id pi@<raspberrypi-ip>
```

Test it:

```bash
ssh pi@<raspberrypi-ip>
```

---

### Ubuntu/Debian:

```bash
sudo apt update
sudo apt install -y ansible
```

---

## Get docker role

```bash
ansible-galaxy install geerlingguy.docker -p roles/ 
```

---

## Run the Playbook

```bash
ansible-playbook -i inventory/hosts.yml playbook.yml
```

If using Vault:

```bash
ansible-playbook -i inventory/hosts.yml playbook.yml --ask-vault-pass
```