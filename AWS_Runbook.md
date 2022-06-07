# Route 53
## Add an existing domain to the Route 53
1. Register you domain with any of the domain providers, like freenom/godaddy
2. Get the A record/C name
3. Mention that in Route 53
4. get the public IP and DNS names from route 53 and mention them in domain provider records. 

# EC2
## Lost private key
**Amazon EC2 doesn't keep a copy of your private key; therefore, if you lose a private key, there is no way to recover it**. If you lose the private key for an instance store-backed instance, you can't access the instance; you should terminate the instance and launch another instance using a new key pair. If you lose the private key for an EBS-backed Linux instance, you can regain access to your instance.

you have to create an AMI image from existing EC2 instance and create another instance out of it.

## Reset passwords and SSH keys on EC2 instances
https://docs.aws.amazon.com/systems-manager/latest/userguide/automation-ec2reset.html

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/TroubleshootingInstancesConnecting.html#replacing-lost-key-pair

## Add/Remove public key?
The public keys are located in the `.ssh/authorized_keys` file on the instance.
To add or replace a key pair, you must be able to connect to your instance. If you've lost your existing private key or you launched your instance without a key pair, you won't be able connect to your instance and therefore won't be able to add or replace a key pair.

## Add SSH Key to EC2 instances with Ansible – Automated
https://www.middlewareinventory.com/blog/ansible-ec2-ssh-key/