# Npontu A

# README

## Overview
Deploying a PHP Laravel web application with
MySQL database on physical bare servers using DevOps best practices.
The application code is stored in a Git repository. The goal is to automate
the deployment process and ensure that the application is highly
available, scalable, and secure.

* **Technologies used (e.g., PHP, Laravel, MySQL).**

## Deployment

### Prerequisites

* **Required tools ( Ansible, Docker).**


### Steps

#### Ansible Deployment

1. Install Ansible on the control machine.

# Installing Ansible

On Ubuntu or Debian systems:

* **Update the package list:**
sudo apt update
* **Install Ansible:**
sudo apt install ansible
* **Verify the installation:**
ansible --version

2. Run the playbook: `ansible-playbook -i inventory deploy.yml`
    

#### Docker Deployment

1. Build the Docker image: `docker build -t my-laravel-app .`
2. Run the container: `docker run -d -p 80:80 my-laravel-app`
    * Adjust port mappings as needed.

## Running Locally

### Prerequisites

* **Required tools ( PHP, Composer).**
* **Specify any local configuration steps.**

### Steps

1. Clone the repository: `git clone https://github.com/your-username/your-laravel-app.git`
2. Install dependencies: `composer install`
3. Create a database and configure `.env` file: 
4. Run the application: `php artisan serve`


# Grafana and Prometheus Deployment

This repository contains an Ansible playbook to automate the deployment of Grafana and Prometheus on a target server. Follow the instructions below to set up and run the applications locally.

## Prerequisites

- Ansible installed on the machine where you will run the playbook.
- A target server where Grafana and Prometheus will be deployed. Ensure the server is accessible and has internet access.

## Deployment Steps

1. Clone this repository to your local machine:

    ```bash
    git clone https://github.com/your-username/grafana-prometheus-ansible.git
    ```

2. Navigate to the repository:

    ```bash
    cd grafana-prometheus-ansible
    ```

3. Edit the inventory file (`inventory.ini`) to specify your target server's IP address or hostname.

    ```ini
    [your_servers]
    ansible_host= Npontu2 ip
    ```

4. Run the Ansible playbook:

    ```bash
    ansible-playbook -i inventory.ini grafana_prometheus_playbook.yml
    ```

5. Once the playbook execution is complete, Grafana and Prometheus should be installed and running on your target server.

## Accessing Grafana

- Open a web browser and navigate to `http://Npontu2 ip:3000`.
- Login with the default credentials: Username - `admin`, Password - `admin`.
- Follow the prompts to change the password and configure Grafana as needed.

## Accessing Prometheus

- Prometheus should be accessible at `http://Npontu2 ip:9090`.

## Local Development

If you want to run Grafana and Prometheus locally for development purposes, you can use Docker. Ensure you have Docker installed on your machine.

1. Pull and run Prometheus Docker container:

    ```bash
    docker run -p 9090:9090 prom/prometheus
    ```

2. Pull and run Grafana Docker container:

    ```bash
    docker run -p 3000:3000 grafana/grafana
    ```

3. Access Grafana at `http://localhost:3000` and Prometheus at `http://localhost:9090`.

## Additional Configuration

- Customize Grafana and Prometheus configurations by editing the `grafana.ini.j2` and `prometheus.yml.j2` templates, respectively.
- Adjust security settings and credentials based on your requirements.

## Troubleshooting

- If there are issues during the deployment, check the Ansible output for error messages.
- Review Grafana and Prometheus logs for any issues.





