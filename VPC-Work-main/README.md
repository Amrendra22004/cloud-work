# VPC-Work
## Here is the process of creating VPC in AWS with 2 public and private subnet
![photo_6107379375801486380_x](https://github.com/user-attachments/assets/feeb8ef0-e750-4948-b039-0cb66e11321b)

### 1. Create a VPC
![image](https://github.com/user-attachments/assets/f237fd4d-644d-4e30-94ff-e829be2556b7)


### 2. Add Subnets
![image](https://github.com/user-attachments/assets/5846dae2-22a5-4456-be00-209e4321e6b1)


### 3. Create an Internet Gateway (IGW)
![image](https://github.com/user-attachments/assets/8f050131-0a41-4e6b-82d3-36f5842596cd)


### 4. Set Up Route Tables
![image](https://github.com/user-attachments/assets/5f517a59-edef-447a-ae04-4c6eaec806b3)

--> Attach Internet gateway to public subnet route table
![image](https://github.com/user-attachments/assets/279b9245-6463-4964-8473-2239b34d19aa)

-> subnet associations

![image](https://github.com/user-attachments/assets/99e4dc47-b39c-4a97-9432-23c5dfef7c4f)

### 5. Configure Security Groups

![image](https://github.com/user-attachments/assets/d2500fe0-c8ab-44dc-8ab8-c80f2aa93b64)

## over all resource map of VPC
![image](https://github.com/user-attachments/assets/47a4ed2f-f5df-4186-8045-2daa1e714d3f)

### launch an EC2 Instances in any subnet(public and private -subnet) of this VPC:-
![image](https://github.com/user-attachments/assets/f60a5422-3595-4722-8430-c85474bcc2b9)

![image](https://github.com/user-attachments/assets/b1af9f61-0d51-422e-a061-98619832aa2b)
![image](https://github.com/user-attachments/assets/34fb8f2b-222b-4910-a5b1-bc0598b4d2c7)
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

![image](https://github.com/user-attachments/assets/20e7231a-5941-4c77-9658-4826a1e79d96)

### 6. Adding Virtual private gateway and attach it with this VPC:-
![image](https://github.com/user-attachments/assets/a75f002d-60bc-47c9-a498-727d12de02fe)

--> edit routes in route tables of private subnet :-
![image](https://github.com/user-attachments/assets/39f13e5b-0e86-4ff9-98ab-c584dee71df2)






