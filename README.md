# TP-R405
Automation project for the BUT RT. 
Deploys a LAMP infrastructure with several DNS servers, an Apache2 based load-balancer and several Web servers.

#### Requirements :
- Debian-based distribution with Virtual-Box
- Python3 with pipenv : `apt update && apt -y install python3-pip pipenv`
    - Current version is python3.10 ; update _Pipfile_ if another version is used
- Vagrant ; see [install page](https://developer.hashicorp.com/vagrant/downloads)
```
wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install vagrant
```

- _Recommended_ : Visual Studio Code with the YAML extension

#### How to use :
- `vagrant up` 
- `pipenv install && pipenv shell`
- `ansible-playbook setup_infra.yml`
- _vagrant ssh_ to test, e.g. `vagrant ssh lb-1`