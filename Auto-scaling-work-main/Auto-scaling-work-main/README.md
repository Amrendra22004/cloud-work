# Auto-scaling-work

### AWS EC2 Auto Scaling

## 1. Create a VPC
![image](https://github.com/user-attachments/assets/15978fde-d7b7-468d-a7d5-b6a57b5f6c29)

## 2. Create a internet gateway then attach with this VPC
![image](https://github.com/user-attachments/assets/5a725e7c-a117-4752-89bd-f0cccd8b7a36)

## 3. create a public subnet 

1. Public subnet 1a
![image](https://github.com/user-attachments/assets/9028a225-ef17-48cf-ac7d-80ee4326442e)

2. Public subnet 1b
![image](https://github.com/user-attachments/assets/cd10900c-8299-4d10-a48b-1a648202c840)

![image](https://github.com/user-attachments/assets/13c3cd48-627e-4e72-bf82-0f8c209bac1d)

## 4. Route tables
![image](https://github.com/user-attachments/assets/87b370b7-7205-49c8-ad2c-4e8cb62d979a)

-> Subnet associations
![image](https://github.com/user-attachments/assets/4a7add92-70cf-4720-9d84-dfc5656da0bd)

-> Edit routes
![image](https://github.com/user-attachments/assets/b9b6d43b-f3a2-4c3b-aa03-856b5bff028e)

##### -----------------------Resource map--------------------------------------

![image](https://github.com/user-attachments/assets/41d8948f-1be7-4f7e-8a67-56643fefeec3)

## 5. Creating Target Groups

![image](https://github.com/user-attachments/assets/f0e7d13c-3032-4fff-ab7d-ae90c2ed976f)

![image](https://github.com/user-attachments/assets/71805db4-8a3a-4385-abf4-ae1b288e687c)

## 6. create Load balancers (Application Load Balancer)
![image](https://github.com/user-attachments/assets/9f51e63c-5559-46d8-852a-99a6b53f2e6d)
![image](https://github.com/user-attachments/assets/e429983a-4621-4656-b294-0c841187aa6d)

-> Security group for http
-> Attach target Group
![image](https://github.com/user-attachments/assets/c61df5fa-0870-4917-889c-48e896352eda)

### Summary
![image](https://github.com/user-attachments/assets/6ff2d7db-eb71-42d8-a008-e09501cc9e9a)
![image](https://github.com/user-attachments/assets/2b95ba19-58ef-4a72-b55a-bdfb5d59688b)


## 7. Create Auto Scaling group
-> Create launch template
-> name and description
-> Launch template contents

![image](https://github.com/user-attachments/assets/8cad4648-cb35-472c-a99e-3bc4ead35c38)

![image](https://github.com/user-attachments/assets/88d25973-add8-4756-9d4f-aedd32660271)

![image](https://github.com/user-attachments/assets/5fadedf9-24fa-4348-a90a-f08f8ab00ead)

-> Choose instance launch options 
![image](https://github.com/user-attachments/assets/42fe2fe1-5f48-4702-917e-cbbe24127d9d)

-> Attach to an existing load balancer
![image](https://github.com/user-attachments/assets/bd22846a-b7a3-4603-8e77-b901add9dfbf)

-> Configure group size and scaling
![image](https://github.com/user-attachments/assets/6c137ce7-75c5-4f56-9401-f25acecf8ee7)








