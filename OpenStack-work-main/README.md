# OpenStack-work

## Installing OpenStack in ubuntu using MicroStack 
```
sudo snap install microstack --beta
```
![Screenshot from 2025-04-30 16-44-30](https://github.com/user-attachments/assets/02c54602-4696-4d0c-9fcb-902f47da84e7)


### 1. Initialize MicroStack
```
sudo microstack init --auto --control
```
This command:

* Sets up OpenStack services.
* Configures networking.
* Enables an internal bridge for virtual machines.

![Screenshot from 2025-04-30 17-02-40](https://github.com/user-attachments/assets/909ecdc1-8f0a-47a0-8c07-02b9c13991e4)


### 2. Verify OpenStack Services
```
sudo microstack status
```
![Screenshot from 2025-04-30 17-04-17](https://github.com/user-attachments/assets/85a67673-9160-48ab-8aa2-8a4cf4277340)


### 3. Access OpenStack Dashboard
Once initialized, you can access the Horizon web dashboard:

-> Find the dashboard IP address:
```
ip a | grep inet
```

-> for password 
```
sudo snap get microstack config.credentials.keystone-password
```

-Go to web browser and search this above IP address:
```
http://<your-ip>:80
```
![Screenshot from 2025-04-30 17-20-13](https://github.com/user-attachments/assets/c7fd595c-ec2e-4e41-a7db-d76dcd1b0b0e)


## Log in using the default credentials:

* Username: admin
* password: (from above)

![Screenshot from 2025-04-30 17-22-59](https://github.com/user-attachments/assets/d04cf32a-8dc5-4992-a4b4-e698bbad2dc2)

