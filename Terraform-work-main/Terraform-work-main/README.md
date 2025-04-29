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

![Screenshot from 2025-02-22 23-31-35](https://github.com/user-attachments/assets/8c69e374-5ac3-4f59-876a-5bb91735f32c)

------------------------------------------------------------------------------------------------------
## AWS CLI installation 
```
sudo snap install aws-cli --classic
```

![Screenshot from 2025-02-23 22-15-44](https://github.com/user-attachments/assets/90e3e86a-68df-4a0b-b07a-1c1e38ef8bb4)
-------------------------------------------------------------------------------------------------------

## AWS setup

### 1. IAM (Identify and Access management)
**-> Go to user groups in IAM -> Create a User Group

![Screenshot from 2025-02-23 21-09-51](https://github.com/user-attachments/assets/ec1a65ce-0d9e-45e1-b300-bf09938111a4)

==Give it Above permissions==

**-> Create User

![Screenshot from 2025-02-23 21-13-52](https://github.com/user-attachments/assets/4067742d-24b5-4a48-a4d2-96689c740592)

**-> Attach it with user Group of step 1

![Screenshot from 2025-02-23 21-16-19](https://github.com/user-attachments/assets/d754ef20-24cd-4138-a9ea-d3c9ec03419e)

**-> Create Access key

![Screenshot from 2025-02-23 21-18-51](https://github.com/user-attachments/assets/7aef27c1-8dd7-4685-8035-df9ca84868aa)

**-> Select AWS CLI

![Screenshot from 2025-02-23 21-20-46](https://github.com/user-attachments/assets/f816a6e3-7da8-47d7-858d-b5b517205d18)

**-> so access key has been created now use this in AWS CLI

![Screenshot from 2025-02-23 22-06-40](https://github.com/user-attachments/assets/8f0db02e-f610-4d9f-a6ec-abc216c79ef3)

-----------------------------------------------------------------------------------------------------------------------
## Configure AWS:
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

resource "aws_instance" "UGO_Server" {
    ami           = "ami-0cbf43fd299e3a464"
    instance_type = "t2.micro"

    tags = {
        Name = "MyNCAAInstance"
    }
}
```
use command 
```
nano main.tf
```
![Screenshot from 2025-02-23 22-34-18](https://github.com/user-attachments/assets/4b7a10e5-b438-4a0c-922d-570bb3f57847)

## Initializing and Applying Terraform

we need to initialize Terraform first !!
```
terraform init
```
![Screenshot from 2025-02-23 22-39-18](https://github.com/user-attachments/assets/8082b54b-ba40-4c7e-b246-a19b1567455d)

-> Check the Execution Plan
by Running
```
terraform plan
```
![Screenshot from 2025-02-23 22-41-35](https://github.com/user-attachments/assets/bdb1203f-29d0-48b3-aa6b-ea4cf73e177e)

-> Deploy your EC2 instance:
```
terraform apply -auto-approve
```
![Screenshot from 2025-02-23 22-43-57](https://github.com/user-attachments/assets/990b6d33-54b3-495b-a006-973f53028024)

### In AWS console
-> Instance has been created !!

![Screenshot from 2025-02-23 22-47-23](https://github.com/user-attachments/assets/b5bec271-11ad-439b-a16c-95ab97a38b46)

-> Now Destroying the Infrastructure
```
terraform destroy -auto-approve
```
![Screenshot from 2025-02-23 22-52-19](https://github.com/user-attachments/assets/4408b8ef-5cac-4959-a05e-65f5bf2eb52e)

-> In AWS

![Screenshot from 2025-02-23 22-52-38](https://github.com/user-attachments/assets/9882c5f6-7d32-47da-b2c3-a85c4954a0d3)








