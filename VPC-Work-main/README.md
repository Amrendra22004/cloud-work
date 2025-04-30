# VPC-Work
## Here is the process of creating VPC in AWS with 2 public and private subnet

### 1. Create a VPC
![Screenshot from 2025-04-30 19-36-47](https://github.com/user-attachments/assets/115e9576-122e-49a7-8cdc-f5e8947d321a)


### 2. Add Subnets
![Screenshot from 2025-04-30 19-37-27](https://github.com/user-attachments/assets/d78dc90f-0e7c-47e8-ba55-dbcf371d9b36)
![Screenshot from 2025-04-30 19-39-52](https://github.com/user-attachments/assets/d0440351-e675-4bfd-8f28-0ef435b025d7)


### 3. Create an Internet Gateway (IGW)
![Screenshot from 2025-04-30 19-42-22](https://github.com/user-attachments/assets/5390b819-e438-4f2f-8911-fecbbc3c760e)


### 4. Set Up Route Tables
![Screenshot from 2025-04-30 19-43-30](https://github.com/user-attachments/assets/f9cafdf4-d282-40c6-8f65-5c213bf51802)

--> Attach Internet gateway to public subnet route table
![Screenshot from 2025-04-30 19-44-09](https://github.com/user-attachments/assets/b5b32c07-367f-47db-9f8a-f8598e1cd9e3)


-> subnet associations
- add public subnet to public route table 
![Screenshot from 2025-04-30 19-45-11](https://github.com/user-attachments/assets/7f536298-cdd0-498f-b3ca-0b51d53072e9)

### 5. Configure Security Groups

![Screenshot from 2025-04-30 19-48-52](https://github.com/user-attachments/assets/ef113374-32bc-4bd7-962d-0f979e633f59)

## over all resource map of VPC
![Screenshot from 2025-04-30 19-49-46](https://github.com/user-attachments/assets/6fd04f40-a36e-420e-baf0-0f91c1f753db)

### launch an EC2 Instances in any subnet(public and private -subnet) of this VPC:-
![Screenshot from 2025-04-30 19-51-24](https://github.com/user-attachments/assets/0f57428e-3abd-4909-a1e4-87319172e527)
-edit network setting
![Screenshot from 2025-04-30 19-52-01](https://github.com/user-attachments/assets/e06dbde2-6251-4f44-bdfe-371dad22a8ec)
![image](https://github.com/user-attachments/assets/cee7460d-a4f1-4a6f-95de-81d9398dda59)

### ->Install Apache HTTP Server on EC2 Instances
```sh
sudo apt update
sudo apt install apache2 -y
```

#### ->Start and Enable Apache
```sh
sudo systemctl start apache2
sudo systemctl enable apache2
```
![Screenshot from 2025-04-30 20-01-42](https://github.com/user-attachments/assets/6a742c71-511e-4649-9610-f754ec4da7e8)










