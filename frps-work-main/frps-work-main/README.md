# frps-work
## Install FRP on your EC2 instance and localhost both:
```
wget https://github.com/fatedier/frp/releases/download/v0.58.1/frp_0.58.1_linux_amd64.tar.gz

```

![Screenshot from 2025-04-30 20-07-44](https://github.com/user-attachments/assets/58b04d52-3c15-47c9-af81-4889286534e3)

### -> Extract the downloaded FRP archive:
```
tar -xzf frp_0.58.1_linux_amd64.tar.gz
```

 - move to local folder (both for clent and server)
```
sudo mv frp_0.58.1_linux_amd64 /usr/local/frp
cd /usr/local/frp
```
# In EC-2 instance or server side:
 - Configure frps.ini: Edit the server configuration
```
sudo nano frps.ini
```

 - add this:
 ```
[common]
bind_port = 7000
token = your-secure-token
```
- make sure to add token (eg: - amrendra etc)

![image](https://github.com/user-attachments/assets/a709e91a-e30b-44e0-bcd1-3b80230c8872)

## Configure EC2 Security Group:
Go to the AWS EC2 console, select your instance, and edit the Security Group.
- Add inbound rules:
  - Type: Custom TCP, Port: 7000, Source: 0.0.0.0/0 (or restrict to your local IP for security).
  - Type: Custom TCP, Port: 8081, Source: 0.0.0.0/0 (for the forwarded service).
Save the rules.

### -> Run frps: Start the frp server:
```
./frps -c frps.ini
```

![Screenshot from 2025-04-30 20-14-19](https://github.com/user-attachments/assets/ba442e25-c649-4a50-8a71-baa4bebad262)


# Clent side or localhost
-> Configure frpc.ini: Edit the client configuration:
```
sudo nano frpc.ini
```
- add this:
```
[common]
server_addr = <EC2-Public-IP>
server_port = 7000
token = your-secure-token

[web]
type = tcp
local_ip = 127.0.0.1
local_port = 8080
remote_port = 8081
```
- make sure to add same token on server side and EC-2 public IPv4 don't just copy !!

![Screenshot from 2025-04-30 20-20-28](https://github.com/user-attachments/assets/cacc1577-7d2e-47d8-89c5-7353edcf0878)
  
### Run a Local Service (Optional): If no service is running on 127.0.0.1:8080, start a test web server:
```
python3 -m http.server 8080
```

![Screenshot from 2025-04-30 20-21-56](https://github.com/user-attachments/assets/d6089fd3-4524-4f14-8b47-469c2275b2d8)

- Run frpc: Start the frp client:
```
./frpc -c frpc.ini
```


- it will connect to server

![Screenshot from 2025-04-30 20-23-03](https://github.com/user-attachments/assets/3613333f-21d1-436f-9f81-2d1d7d6ca3c9)

(if not, check inbound rules of ec-2 instance Security Group step from above)

- now
   - From any device (e.g., your local machine or another computer), open a browser and navigate to:
     ```
     http://<EC2-Public-IP>:8081
     ```
for example:-
- ec-2 instence:

![Screenshot from 2025-04-30 20-24-47](https://github.com/user-attachments/assets/dbd8f80a-ee0b-42ed-93d7-74a37d22a44b)

- in browser

![Screenshot from 2025-04-30 20-24-07](https://github.com/user-attachments/assets/c799690f-3d0b-4be0-9516-c83120b290b0)

![Screenshot from 2025-04-30 20-26-48](https://github.com/user-attachments/assets/0a6c94e8-0419-4573-a332-e311c5f1b227)



     
