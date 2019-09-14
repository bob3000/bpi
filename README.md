# BPI

## Connect SSH

local

```sh
cat ~/.ssh/id_rsa.pub | nc -l 9000
```

remote

```sh
ssh-keygen -b 4096
nc <local_ip> 9000 >> ~/.ssh/authorized_keys
```

## Install software

```sh
apt update
apt install python3 python3-dev python3-pip python-apt libyaml-dev libssl-dev git
curl -sSL https://get.docker.com | sh
sudo usermod -aG docker pi
pip3 install ansible
mkdir -p ~/code && cd ~/code && git clone https://github.com/bob3000/bpi.git && cd bpi
export PATH=$PATH:$HOME/.local/bin
ansible-playbook main.yml
```
