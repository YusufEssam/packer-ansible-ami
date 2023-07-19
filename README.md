# packer-ansible-ami

Builds AWS AMI images for Ubuntu versions 22.04 containing customisations for use in our infrastrcuture using Packer with shell and ansible-local provisioners types. The reason for this is for implementing the idea of immutable infrastructure.


## Source code structure
```bash
.
├── ansible
│   ├── group_vars    
│   ├── ntp-vars  
│   ├── playbook.yml
│   ├── requirments.yml
│   ├── roles 
├── packer_ami.json
├── packer_vars.json
└── scripts
    └── ansible-installation.sh

```
## Requirements
* An AWS account with an Access Key for your user.

## How to use
* Clone the repository.

* You should define the AWS credentials, vpc region, instance type and ssh username in variables section. These values are in turn derived from packer_vars.json file where we can define any other required variables.

* You can validate your packer_ami.json file by using the below command
```bash
packer validate packer_ami.json

```
* Once the validation is successful,  you can build the AMI using below command

```bash
packer build -var-file=packer_vars.json packer_ami.json

```

## Contributing

Pull requests are welcome. 

