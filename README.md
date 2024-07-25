# Automated Digital Evidence Gathering and Analysis

This project aims to automate the gathering and analysis of digital evidence across various operating systems (Windows, Linux, MacOS) using tools like Velociraptor and GRR. The workflow is designed to be scalable and OS-agnostic, facilitating quick and efficient deployment of forensic tools during an emergency.

### Key Features

- **OS-agnostic:** Works with Windows, Linux, and MacOS hosts.
- **Scalable:** Handles both small and large numbers of hosts.
- **Automated Deployment:** Uses Ansible to automate the installation and configuration of forensic tools.
- **Containerization:** Uses Docker to ensure consistency and portability of forensic tools.
- **Flexibility:** Supports deployment of either Velociraptor or GRR agents, or both, depending on the requirements.

## Usage

### Setup

1. **Clone the repository:**
   ```bash
   git clone <your-repo-url>
   cd project-root
   ```

2. **Configure the inventory:**
   - Update `ansible/hosts` with the host details.

3. **Install Docker on all hosts:**
   ```bash
   ansible-playbook ansible/install_docker.yml
   ```

### Deploy Velociraptor

1. **Deploy Velociraptor server and agents:**
   ```bash
   ansible-playbook ansible/deploy_velociraptor.yml
   ```

2. **Deploy only Velociraptor agents to connect to an existing server:**
   - Update `ansible/deploy_velociraptor_agents.yml` with the correct `server_url`.
   ```bash
   ansible-playbook ansible/deploy_velociraptor_agents.yml
   ```

### Deploy GRR

1. **Deploy GRR server and agents:**
   ```bash
   ansible-playbook ansible/deploy_grr.yml
   ```

2. **Deploy only GRR agents to connect to an existing server:**
   - Update `ansible/deploy_grr_agents.yml` with the correct `server_url`.
   ```bash
   ansible-playbook ansible/deploy_grr_agents.yml
   ```

### Deployment Playbooks

- **Install Docker:** Installs Docker on all specified hosts.
  ```bash
  ansible-playbook ansible/install_docker.yml
  ```

- **Deploy Velociraptor server and agents:** Deploys Velociraptor server on localhost and agents on all hosts.
  ```bash
  ansible-playbook ansible/deploy_velociraptor.yml
  ```

- **Deploy GRR server and agents:** Deploys GRR server on localhost and agents on all hosts.
  ```bash
  ansible-playbook ansible/deploy_grr.yml
  ```

- **Deploy only Velociraptor agents to an existing server:**
  - Update `ansible/deploy_velociraptor_agents.yml` with the correct `server_url`.
  ```bash
  ansible-playbook ansible/deploy_velociraptor_agents.yml
  ```

- **Deploy only GRR agents to an existing server:**
  - Update `ansible/deploy_grr_agents.yml` with the correct `server_url`.
  ```bash
  ansible-playbook ansible/deploy_grr_agents.yml
  ```

