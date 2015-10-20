# Create a Swarm Cluster on DigitalOcean using Ansible

After cloning repo, create a droplet on DigitalOcean to act as your admin node. You will use this node post-deployment to use docker-machine and docker-compose. Add the public IP of the droplet to the `hosts` file under the admin group.

Generate an API Token from DigitalOcean and pass that and the number of Swarm Nodes you would like:

```$ ansible-playbook -i hosts -e API_TOKEN=<your_token_here> -e NODE_COUNT=2 deploy.yml```

This will install docker, docker-machine and docker-compose on the admin node. Additionally it will create a swarm-master and 2 swarm-nodes, ready to go for deployment with docker-compose.
