# Amazon AWS EC2

* Signup on Amazon AWS https://aws.amazon.com/ 
* Under services choose/search EC2
* Click ```Launch instance```

## Amazon Machine Image
Ready to use OS/applications required for launching the instance. Choose the one most suitable to your needs. E.g. Ubuntu Server 18.04 LTS which is eligible in the free tier.

## Instance Type
There are different types of instances offered based on the different configurations of memory, storage, vCPUs, etc. Choose t2.micro, eligible in the free tier.

## Instance Details
Configuration of the instance. Proceed to the next step leaving the default values entered.
* Network
* Subnet
* IAM role

## Storage
Specify or add storage volumes in this step. Proceed next

## Tags
Provide a tag to your instance. 
* Click ```Add tag```
* In the key, mention ```Name```
* For the value, mention ```My Instance```

## Security Group
In this step we configure rules for allowing traffic to the instance.

* Security Group name <br>
  By default a name is already assigned. Change if you need/want to.
* SSH for port 22 is already added.
* Click ```Add Rule``` and add other rules
  * HTTP running on port 80
  * HTTPS running on port 443
  * Custom TCP Rule with port 8000 for running Django
* Similarly you may open up other ports for the service that you might need.
* Proceed to the final step by clicking ```Launch```

## Generating Key pair
In this step, one needs to generate a key ```.pem``` file. The public key is stored at AWS and private key is downloaded and stored locally on our system. This key pair allows us to connect to the instance. 
* Choose ```RSA```
* Provide any value to ```key pair name```
* Click ```Download key pair```
* Save this key pair (```.pem``` file) carefully as it will be needed everytime to connect (ssh) to the instance
* Click ```Launch instance```

## Instances
* List of instances, its state, and other details will be visible on the instance dashboard
* Select the desired instance to view its details like public IP, security group, etc.

## ssh into the EC2 instance
* Set permissions for the key pair ```.pem``` file or else one cannot cannot into the instance. 
* ```chmod 400 <keypairName>.pem```
* ```$ ssh -i <keypairName>.pem <username>@<publicIP>```
* Note: In this case the ```username``` will be ```ubuntu``` as Ubuntu was chosen as AMI.


## Refereces

* https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html

* https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/managing-users.html

* https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/get-set-up-for-amazon-ec2.html#create-a-key-pair

* https://dev.to/rmiyazaki6499/deploying-a-production-ready-django-app-on-aws-1pk3