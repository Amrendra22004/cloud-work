# Terraform-work

### Introduction
Terraform is a popular Infrastructure as Code (IaC) tool developed by HashiCorp, and it’s widely used for provisioning, managing, and automating infrastructure across various cloud providers
(e.g., AWS, Azure, Google Cloud) and on-premises environments.


## Installation  (Linux)

### 1. Update the System:
```
sudo apt update && sudo apt upgrade -y
```

### 2. Install Dependencies:
```
sudo apt install -y gnupg software-properties-common curl
```

### 3. Add the HashiCorp GPG Key:
```
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
```

### 4. Add the HashiCorp Repository:
```
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
```

### 5. Install Terraform:
```
sudo apt update
sudo apt install terraform -y
```
-> Verify Terraform
```
terraform -version
```
![Screenshot from 2025-04-30 18-02-06](https://github.com/user-attachments/assets/20e378fc-e764-49e5-b603-3aa8eb9018ee)


------------------------------------------------------------------------------------------------------
## AWS CLI installation 
```
sudo snap install aws-cli --classic
```

-------------------------------------------------------------------------------------------------------

## AWS setup

### 1. IAM (Identify and Access management)
**-> Go to user groups in IAM -> Create a User Group

![Screenshot from 2025-04-30 18-08-34](https://github.com/user-attachments/assets/104b00b9-af00-4402-920b-99128e0bb308)

==Give it Above permissions==

**-> Create User

**-> Attach it with user Group of step 1

![Screenshot from 2025-04-30 18-13-01](https://github.com/user-attachments/assets/56ab9220-2c4a-4596-89f0-87abf413acf7)

**-> Create Access key

![Screenshot from 2025-04-30 18-20-15](https://github.com/user-attachments/assets/f7cb0947-264f-433b-aa9b-722d86d807cb)

**-> Select AWS CLI
**-> so access key has been created now use this in AWS CLI

![Screenshot from 2025-04-30 18-23-05](https://github.com/user-attachments/assets/72a44326-a7ca-459e-abe6-6446cebbf602)

-----------------------------------------------------------------------------------------------------------------------
## Configure AWS(in terminal):
```
aws configure
```
-> Manually Adding AWS Credentials
-
```
aws_access_key_id = YOUR_ACCESS_KEY
aws_secret_access_key = YOUR_SECRET_KEY
region = ap-south-1
```
- skip the output one using enter key.
-> Writing the Terraform Configuration File
-
```
mkdir terraform-ec2 && cd terraform-ec2
```
-> let's create a EC2 instance through code: - 
Create a file named ***main.tf***, and add the following configuration:

``` for example
provider "aws" {
    profile = "default"
    region  = "ap-south-1"
}

resource "aws_instance" "web" {
    ami           = "ami-0e35ddab05955cf57"
    instance_type = "t2.micro"

    tags = {
        Name = "My-Instance"
    }
}
```
use command 
```
nano main.tf
```
or if you have vs code
```
code main.tf
```
![Screenshot from 2025-04-30 18-30-42](https://github.com/user-attachments/assets/22991a21-ff45-496c-9dda-582704da4dd1)

## Initializing and Applying Terraform

we need to initialize Terraform first !!
```
terraform init
```
![Screenshot from 2025-04-30 18-36-33](https://github.com/user-attachments/assets/7f28ae79-815e-4652-a13d-284eb619ed9e)

-> Check the Execution Plan
by Running
```
terraform plan
```
![Screenshot from 2025-04-30 18-37-59](https://github.com/user-attachments/assets/e15871d9-43a1-4be6-9bfd-c31d8d294ed0)

-> Deploy your EC2 instance:
```
terraform apply -auto-approve
```
![Screenshot from 2025-04-30 18-55-31](https://github.com/user-attachments/assets/d69c5c49-5540-4f4f-a676-715ebded5526)

### In AWS console
-> Instance has been created !!

![Screenshot from 2025-04-30 18-57-16](https://github.com/user-attachments/assets/6a1e9687-689f-401f-91a2-3d39fd10dee0)

-> Now Destroying the Infrastructure
```
terraform destroy -auto-approve
```
![Screenshot from 2025-04-30 19-13-26](https://github.com/user-attachments/assets/b1c4ddb6-9e57-4228-bc62-de0c83aa79d7)

-> In AWS

![Screenshot from 2025-04-30 19-14-33](https://github.com/user-attachments/assets/ea8cc293-5cb9-4ed4-b603-536bc2abd486)








