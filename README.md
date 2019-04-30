### What

This repo is designed to provide an automated pipeline for the creation of a scalable LAMP stack with a simple app (Drupal CMP) running on AWS via a cloudFormation template.

There are two CFN's here
1) lamp.yaml = a scalable LAMP stack running a multi AZ, ALB web server on one or more AWS Linux AMI's. once up you will be given the output of the APACHE webserver with a welcome message
2) lamp-drupal.yaml is my second script based on my learnings in and around the deployment of LAMP trying to find a simple app to show the benefit of the stack on AWS.

### How

   * Log into AWS
   * Head to CloudFormation
   * Select "upload a template to S3"
   * Specify Stack name
   * Add Allocated storage "5gb" is default
   * Select DB Class "db.t2.micro" is default
   * Add a "DBPassword"
   * Add a "DBUser"
   * Select EC2 instance type "t2.micro" is default
   * Select your EC2 Keypair name
   * Select your preference for MultiAZ
   * Select your SSH location config (access is open to 0.0.0.0/0)
   * Add some subnets (your current subnets should be listed)
   * Select your VPC ID (your current VPC's should be listed)
   * Select your desired web server capacity "1" is default
   * Add tags (if desired)
   * Add CloudWatch alarm ARN (id desired)

### Stack

   * EC2 (with "deletion in use" policy applied)
   * PHP
   * Apache
   * MySQL
   * Drupal

### Deployment requirements

   * An AWS account
   * A valid VPCid
   * AWS CLI access
   * A valid EC2 keypair
   * A Valid elastic IP
   * IAM permissions to launch the aforementioned components via CFN
   * An Existing EC2 Keypair to enable SSH to the instance

### TO DO

   * Automate notifications for stack status
   * Add webhooks for Slack notifications



If all works according to plan your should have a working Wordpress URL in the CFN outputs.

### Brief
###### Challenge:
Provide a Cloud formation template defining a redundant, secure and cost-effective LAMP stack within AWS.

###### Response:
Provide documentation describing your environment
Provide a link to a public git repository hosting the template (committing frequently so we can see how your solution progressed)

###### Stretch Goal:
Provide a small application that will run on the infrastructure (written in PHP that connects to the MySQL database)
Notes: Apache, PHP or MySQL not your thing? Feel free to swap any of these out for an alternate technology.