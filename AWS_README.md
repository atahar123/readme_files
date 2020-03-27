# AWS Guide

How to set up your EC2:
- System to select: Ubuntu Server 18.04 LTS (HVM)
- Instance: t2.micro (it's not really free)
- Network: DevOpsStudent
- Subnet: DevOpsStudentSubnet
- Enable custom IP

- Don't add extra storage
- Two tags:
  1. "Name" atahar-eng54-ec2
  2. "Cohort" Eng54

- Add ports:
  - 80, 22, 8080, 443, 3000
  - Select "MY IP" for all
  - Add a description if you want

Download the key and then on the terminal, open up the folder it downloaded to .ssh:
```
mv /file_name/directory /destination/path
```

### To access the server
```bash
ssh -i <.pem_location> ubuntu@<ip_found_on_aws>
```
- The -i is the identity file
- The .pem_location is the exact location where the key is stored.
  - Example: ssh -i ~/.ssh/atahar-eng54.pem ubuntu@aws.ip.address.not.telling.you

### Files: Copy from your machine to AWS
```bash
scp -i path/to/key file/to/copy <user>@ec2-xx-xx-xxx-xxx:path/to/file
```
- Real life example:
```bash
scp -i ~/.ssh/atahar-eng54.pem -r app/ ubuntu@aws.ip.address:/home/ubuntu/
```
### Signing into the Jenkins console
- Enter the custom link from the Vagrantfile into the browser on port 8080
- When it prompts for the password:
  1. ssh into the VM
  2.
  ```bash
  sudo cat copy/and/paste/the/destination/name/jenkins/gives/you
  ```
