# Setting Up a DA Node for 0g.ai Network

## Prerequisites

**Before setting up the DA Node, ensure you have the following:**

Operating System: Ubuntu 20.04 or later (64-bit).

**Hardware Requirements:**

CPU: Quad-Core processor (2.5 GHz or higher).

RAM: 16 GB or higher.

Storage: SSD with at least 500 GB of available space.

Network: High-speed internet connection with a stable IP.

## Step 1: System Update

First, update your system packages to the latest version:

```
sudo apt-get update && sudo apt-get upgrade -y
```

Reboot the system if any kernel updates were installed:

```
sudo reboot
```

## Step 2: Install Dependencies
Install necessary dependencies including curl, git, docker, and docker-compose:

```
sudo apt-get install curl git docker.io docker-compose -y
```

## Step 3: Set Up Docker

Ensure Docker is running:

```
sudo systemctl start docker
sudo systemctl enable docker
```

Verify the installation:

```
docker --version
```

## Step 4: Clone the DA Node Repository

Clone the official DA Node repository to your local machine:

```
git clone https://github.com/0g-ai/da-node.git
cd da-node
```

## Step 5: Configuration

Configure the node using the provided configuration files. Open the .env file and adjust the parameters according to your network and node preferences:

```
nano .env
```

Important Parameters:

DA_NODE_NAME: Choose a unique name for your DA Node.

DA_NODE_PORT: Default is 26656. Change it if necessary.

PERSISTENT_PEERS: Add persistent peers for better connectivity.

Save and exit the file after making changes.

## Step 6: Start the Node

Start your DA Node using Docker Compose:

```
docker-compose up -d
```

This command will start the node in detached mode.

## Step 7: Check Node Status

To ensure your DA Node is running correctly, check the logs:

```
docker-compose logs -f
```

Look for messages that indicate successful synchronization with the network.

## Step 8: Monitoring and Maintenance

Regularly monitor your node’s performance and logs to ensure it remains in sync with the network. For automated monitoring, consider setting up Prometheus and Grafana.

## Step 9: Security Considerations

Firewall Setup: Ensure only necessary ports are open to the public.

Backup: Regularly back up your node’s data directory.

Updates: Keep your node software up to date with the latest releases.

## Step 10: Troubleshooting

If your node encounters issues, here are some common troubleshooting steps:

Syncing Issues: Verify that your peers are correctly configured.

Performance Lag: Ensure your hardware meets the recommended requirements.

Docker Issues: Restart Docker and re-run docker-compose up -d.
