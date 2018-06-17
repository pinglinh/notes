## SSH

SSH is a tool to perform secure connections between 2 different shells.

Shell is a user interface for access to an operating system's services.

Load balancer splits traffic between multiple instances.

Autoscaling can spin up more instances when you need them or spin down when you no longer need them.

Memory usage
CPU utilisation

## Connecting to EC2 instance from the command line

1.  Create a connection using SSH (the command is given in the dashboard for EC2)
1.  Install NVM package manager:
  ```
  curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash
  ```
1.  Install node:
  ```
  nvm install 8.11.2
  ```
1.  Check node has been installed:
  ```
  node -e "console.log('Running Node.js ' + process.version)"
  ```
1. Install git:
  ```
  sudo yum install git
  ```
1. You can then clone a repo onto the instance
  ```
  git clone ______________
  ```
1. cd into that directory
