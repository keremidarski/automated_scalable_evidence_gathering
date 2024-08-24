# Automated Scalable Digital Evidence Gathering

This project automates the gathering and analysis of digital evidence across various operating systems (Windows, Linux and MacOS) using [Velociraptor](https://docs.velociraptor.app/) and [GRR](https://grr-doc.readthedocs.io/en/latest/). The workflow is designed to be scalable and OS-agnostic, enabling quick and efficient deployment of forensic tools during an emergency.

### Key Features

- **OS-agnostic:** Supports Windows, Linux, and MacOS hosts.
- **Scalable:** Handles both small and large-scale deployments.
- **Automated Deployment:** Uses Ansible to automate the installation and configuration of forensic tools.
- **Containerization:** Uses Docker Compose for consistent and portable deployment of forensic servers.
- **Flexibility:** Supports deployment of either Velociraptor or GRR agents, or both.

## Usage

### Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/keremidarski/automated_scalable_evidence_gathering.git
   cd automated_scalable_evidence_gathering
   ```

2. **Configure the inventory:**
   - Update `ansible/hosts.ini` with the host details.

### Environment Preparation

1. **Prepare the environment on localhost:**
   ```bash
   ansible-playbook ansible/prep_environment.yml
   ```
   - This playbook installs Git, Docker, and Docker Compose on the localhost, ensuring the environment is ready for deployment.

### Deploy Velociraptor

1. **Deploy Velociraptor server and clients:**
   ```bash
   ansible-playbook ansible/deploy_velociraptor.yml
   ```
   - This playbook deploys the Velociraptor server on the localhost using Docker Compose and installs the Velociraptor clients on all hosts defined in the inventory.

### Deploy GRR

1. **Deploy GRR server and clients:**
   ```bash
   ansible-playbook ansible/deploy_grr.yml
   ```
   - This playbook deploys the GRR server on the localhost using Docker Compose and installs the GRR clients on all hosts defined in the inventory.

