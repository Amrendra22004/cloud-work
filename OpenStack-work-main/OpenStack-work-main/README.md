# OpenStack-work

## Installing OpenStack in ubuntu using MicroStack 
```
sudo snap install microstack --beta
```
![Screenshot from 2025-03-02 20-56-07](https://github.com/user-attachments/assets/c31e37de-47f7-4659-9d4a-558100b039e1)

### 1. Initialize MicroStack
```
sudo microstack init --auto --control
```
This command:

* Sets up OpenStack services.
* Configures networking.
* Enables an internal bridge for virtual machines.

![Screenshot from 2025-03-02 21-06-43](https://github.com/user-attachments/assets/439a17ec-abc3-4af8-94e4-2fd1a2f9158b)

### 2. Verify OpenStack Services
```
sudo microstack status
```
![Screenshot from 2025-03-02 21-21-00](https://github.com/user-attachments/assets/2603095b-6070-4c7a-a41a-d505c91ad86f)

### 3. Access OpenStack Dashboard
Once initialized, you can access the Horizon web dashboard:

-> Find the dashboard IP address:
```
ip a | grep inet
```
for example:-
![Screenshot from 2025-03-02 21-33-02](https://github.com/user-attachments/assets/0ee295ae-5b23-4473-b0be-f2f9c65fa9bb)

-> for password 
```
sudo snap get microstack config.credentials.keystone-password
```

-Go to web browser and search this above IP address:
```
http://<your-ip>:80
```
![Screenshot from 2025-03-02 23-01-20](https://github.com/user-attachments/assets/44381f32-ebc1-40a3-8ab4-8cf9e7a955fe)

## Log in using the default credentials:

* Username: admin
* password: (from above)

![Screenshot from 2025-03-02 23-07-31](https://github.com/user-attachments/assets/02e6d20e-1275-418f-bc35-d1dbfeafe61e)
