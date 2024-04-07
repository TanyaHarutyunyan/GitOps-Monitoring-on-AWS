# GitOps Monitoring on AWS

***

## Description

Automated deployment of Node Exporter, Prometheus and Grafana on AWS EC2 using GitOps principles, Ansible and Docker.

***

## Getting Started

### Cloning the Project Repository
Clone the repository via:
* ssh: `git clone git@github.com:TanyaHarutyunyan/GitOps-Monitoring-on-AWS.git`
* https: `git clone https://github.com/TanyaHarutyunyan/GitOps-Monitoring-on-AWS.git`

### Prerequisites
Before getting started, ensure you have the following prerequisites:

* **DockerHub account** to push and then pull and run images. Here is [How to create Docker Hub account](https://docs.docker.com/docker-id/)
* **AWS account** to deploy on EC2 instance. Here is [How to create AWS account](https://docs.aws.amazon.com/SetUp/latest/UserGuide/setup-AWSsignup.html)

### Setting Up GitHub Secrets
To securely store sensitive information, set up the following secrets in your GitHub repository:

* **DOCKERHUB_USERNAME**: DockerHub username
* **DOCKERHUB_TOKEN**: Access token for DockerHub account. Here's [How to generate DockerHub access token](https://docs.docker.com/security/for-developers/access-tokens/).
* **AWS_ACCESS_KEY**: Access key for the AWS account. Here's [How to generate DockerHub access token](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_root-user_manage_add-key.html).
* **AWS_SECRET_KEY**: Access key for the AWS account. AWS_SECRET_KEY will be generated with AWS_ACCESS_KEY.
* **SSH_PRIVATE_KEY**: Private SSH key for accessing your EC2 instances. Here's [How to generate SSH key pair](https://docs.aws.amazon.com/servicecatalog/latest/adminguide/getstarted-keypair.html).

### Updating project variables
Update the project roles' variables and .github/workflow's env variables to align with the specific requirements.

### Deployment
Execute staging, commit, and push workflow to trigger GitHub Action.

### Testing
Access Node Exporter, Prometheus and Grafana via `http://ec2_public_ip_address:port` in any web browser.