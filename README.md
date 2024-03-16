# Ansible Docker Compose Deployment

This Ansible project automates the deployment of Docker Compose projects on CentOS 9 hosts. It installs Docker & Docker Compose on the hosts and ensures that all necessary Python libraries are installed on the guest machines. 

## Project Structure

```
.
├── files
│   └── composetest
│       ├── app.py
│       ├── docker-compose.yml
│       ├── Dockerfile
│       └── requirements.txt
├── hosts
├── play_book.yml
└── roles
    └── install_docker
        └── tasks
            └── main.yml
```

- `files/`: Contains the Docker Compose project files.
- `hosts`: Inventory file specifying the hosts to be managed by Ansible.
- `play_book.yml`: Main Ansible playbook file.
- `roles/`: Directory containing Ansible roles.
    - `install_docker/`: Role responsible for installing Docker.

## Prerequisites

Ensure the following prerequisites are met before running this Ansible project:

- Ansible is installed on the control machine.
- SSH access to the CentOS 9 hosts from the control machine.
- Python installed on the CentOS 9 hosts.

## How to Use

1. Update the `hosts` file with the IP addresses or hostnames of the CentOS 9 hosts you want to deploy the Docker Compose project onto.

2. Ensure that the Docker Compose project files (`app.py`, `docker-compose.yml`, `Dockerfile`, `requirements.txt`) are placed in the `files/composetest` directory.

3. Review and customize the `play_book.yml` file if necessary.

4. Run the Ansible playbook using the following command:

   ```bash
   ansible-playbook -i hosts play_book.yml
   ```

## Additional Notes

- This playbook assumes CentOS 9 hosts. If deploying to different distributions or versions, modifications may be necessary.
- Ensure that Docker is compatible with the CentOS 9 version being used.
- Verify network connectivity and SSH access to the hosts before running the playbook.
