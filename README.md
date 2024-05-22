# 📢📢📢 Attention all Docker 🐳 Beginners & Professionals! 🎯
# 💻 Unlock the power of SSH with this Ubuntu image, perfect for testing and development! 🛠️

## 🚨 Please note: This image is designed for educational and testing purposes 📚 🧪 ONLY! It is NOT SUITABLE for production environments! 🚫

This Docker image is built on Ubuntu 22.04 and comes pre-installed with an SSH server, enabling seamless creation of SSH-accessible containers. You can effortlessly configure access using SSH keys or by utilizing a default username and password.

## Step 1: Create Authentication SSH-Keygen Keys.
```
ssh-keygen -t rsa -f ~/.ssh/ansible_id_rsa_key -b 4096 -C "This is used for ansible" -N ""
ls -alsh ~/.ssh/
```
## Step 2: Pull docker image
```
docker pull ibraransaridocker/ubuntu-ssh-enabled:latest
```
## Step 3: Set variables to run the docker container.
### Change 👇 variables(containername, username, password & port) according to your need.
```
container_name=server_1
ssh_user=ibrar_ansari
ssh_pass=your_secure_password
ssh_port=2023
container_image=ibraransaridocker/ubuntu-ssh-enabled:latest
key_path=~/.ssh/ansible_id_rsa_key.pub
```
## Step 5: Run docker container.
```
docker run -itd --name=$container_name -p $ssh_port:22 -e SSH_USERNAME=$ssh_user -e PASSWORD=$ssh_pass -e AUTHORIZED_KEYS="$(cat $key_path)" $container_image
```
## Step 6: Test SSH connection 
### Get Node IP:
```
hostname=$(hostname -I | awk '{print $1}')
```

### Pem Key Method:
```
ssh -i ~/.ssh/ansible_id_rsa_key -p $ssh_port $ssh_user@$hostname
```
### Password Method:
```
ssh -p $ssh_port $ssh_user@$hostname
```

### 💼 Connect with me 👇👇 😊

- 🔥 [**Youtube**](https://www.youtube.com/@DevOpsinAction?sub_confirmation=1)
- ✍ [**Blog**](https://ibraransari.blogspot.com/)
- 💼 [**LinkedIn**](https://www.linkedin.com/in/ansariibrar/)
- 👨‍💻 [**Github**](https://github.com/meibraransari?tab=repositories)
- 💬 [**Telegram**](https://t.me/DevOpsinActionTelegram)
