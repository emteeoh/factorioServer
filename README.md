# factorioServer
Stop and start my factorio SE server when I play so that I'm not spending $150/month on 32G ram Digital Ocean droplets

# How
The basics are simple:
1) Terraform and Ansible playbooks are put into the repo
2) github actions are configured to terraform plan and apply, then run the playbook when there is a PR
3) figure out how I'm going to delete the host using the same mechanisms at the end of the gaming session

One of the main sticky points is that the game save and mods need to be stored on a virtual disk that is mounted by the game server VM, but is not the VM's primary disk. I need to be able to delete the VM without losing my game.

# Status
I've actually already done all the pieces. I just need to check in the code pieces to *this* repo, and figure out how to hook in a terraform destroy
