# uninstall-test

Assumptions:
  - Local machine should have boto installed
  - boto config is set up with an IAM user who has sufficient permissions
  - Did not create a new VPC, rather used a functiont to fetch the VPC ID from us-east-1c subnet
  - Web will be running on an Ubuntu machine
  - Everywhere http protocol is followed - no security certs, hence no https
  - Web service running on port 80

1) Create two webserver instances
  1.b) Create a security group
    1.b.1) SSH - 22 (everywhere)
    1.b.2) HTTP - 80 (everywhere)
    1.b.3) fails if sg with same name already exists - no handler
  1.c) Create ec2 key pair for ssh keys
    1.c.1) Takes current user's (local system) pub key as the EC2 key-pair's public key 
  1.c) Choose instance type (t2.micro - free) and AMI
  1.d) Choose VPC settings (if required - like spinning instance in a particular AZ)
  1.e) Volume config (magnetic - cheaper)
  1.f) Tagging of instance

2) As part of boot-strapping, configure instances and install python, git, nginx
3) Wait for instances to come in running state

--------------------------- USE NGINX DOCKER IMAGE AND BE DONE WITH ALL THIS ------------------------------------

{
  // Commneted out part!! It depend on the directory where codebase is risiding
  #4) Nginx configuration (create a default page and then use it as nginx.conf)
  #5) Checkout git repo to /var/www (or any alias)
  #6) Restart nginx and check that port 80 service is responding
}

------------------------------------------------------------------------------------------------------------------

7) ELB Setup
8) RDS Setup

