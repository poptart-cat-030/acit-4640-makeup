# 4640-makeup-lab

## Getting Started

## Generate an SSH key pair
1. Run the following command:
```
ssh-keygen -t ed25519 -f ~/.ssh/aws -C "makeup-lab"
```
### Add public key to AWS
1. Navigate to the `scripts` folder of the project directory (ex: `<insert_some_path_here>/acit-4640-makeup/scripts`)
2. Run the following command to execute the upload key script
```
./upload_ssh_key ~/.ssh/aws.pub
```
We are passing in the `aws.pub` public key we made earlier as an argument into the script `upload_lab_key` for it to add the key to our AWS account.

### Creating Infrastructure using Terraform
1. Navigate to the `terraform` folder of the project directory (ex: `<insert_some_path_here>/acit-4640-makeup/terraform`)
2. Run the following command to initialize the directory:
```
terraform init
```
3. See what kinds of steps terraform would make to create the infrastructure described in the terraform file using the following command:
```
terraform plan
```
4. Create the infrastructure as described by the output of the `terraform plan` command using the following command:
```
terraform apply
```

### Configuring Infrastructure using Ansible
1. Navigate to the `ansible` folder of the project directory (ex: `<insert_some_path_here>/acit-4640-makeup/ansible`)
2. Run the following command to check the syntax of your playbook file (ex: playbook file named `playbook.yml`):
```
ansible-playbook playbook.yml --syntax-check
```
After running the command, if your playbook syntax is valid then you should see something like: "playbook: playbook.yml"
<br><br>
3. Once there are no syntax errors, run the following command to execute the tasks within the playbook:
```
ansible-playbook run playbook
```
4. Execute the playbook using the following command:
```
ansible-playbook -i inventory/aws_ec2.yml playbook.yml
```

### Victory Screenshot
Screenshot of us visiting the HTML document being served by our Ubuntu EC2:

### Remove public key from AWS
1. Navigate to the `scripts` folder of the project directory (ex: `<insert_some_path_here>/acit-4640-makeup/scripts`)
2. Run the following command to execute the remove key script
```
./remove_ssh_key ~/.ssh/aws.pub
```
We are passing in the `aws.pub` public key we made earlier as an argument into the script `remove_lab_key` for it to remove the key from our AWS account.