Congrats ! You have won a GPU. What do you need to do, next:

## Access to your container
Each student has been assigned to a [container](https://www.docker.com/what-container), which is a small machine hosted by the system and linked to the GPUs. You can access your container via a [secure network protocol](https://en.wikipedia.org/wiki/Secure_Shell) and your [port number](https://en.wikipedia.org/wiki/Port_(computer_networking)). Make sure you are connected to the Imperial network, using a [VPN](https://www.imperial.ac.uk/admin-services/ict/self-service/connect-communicate/remote-access/method/set-up-vpn/).

* connect to your container: `ssh -p <port number> root@bg-beast.bg.ac.uk`
* change your pasword: `passwd`
* go to your repository: `cd /data/user/<user name>`


## Upgrade your container
Make sure you update the container, to be up-to-date: 
* `apt-get update`
* `apt-get upgrade`
* `apt-get install vim tmux bzip2 wget openssh-server`


## Download python with anaconda
You want to go to the root files, and download the last version of [anaconda](https://repo.anaconda.com/) using wget. Then, you need to compile the [bash file](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) obtained. 
* `cd ~`
* `wget https://repo.anaconda.com/archive/Anaconda3-5.2.0-Linux-x86_64.sh`
* `bash Anaconda3-5.2.0-Linux-x86_64.sh`

You have to make sure that the binaries files of anaconda is added to your path. You need to open your `~/.bashrc` file: 
* `vim ~/.bashrc`

At the end of your file, look for: `export PATH="/root/anaconda3/bin:$PATH"`. If it's not written, please add it. 
* `source ~/.bashrc`
* Launch Python: `python`

## Create your virtual environment
A virtual environnment .... You can create as many virtual environment as you want [with conda](https://conda.io/docs/user-guide/tasks/manage-environments.html)
* `conda install -n <name environment> python=x.x` 
* `source activate <name environment>`: to activate your environment.
* `source deactivate`: to deactivate your environment.

Install your packages (ex: pytorch): 
* `source activate <name environment>`
* `conda install pytorch torchvision cuda91 -c pytorch`: you are using CUDA 9.1. 

## Recover and run your code 
Install git and clone this repo: 
* ``
* ``

Run the code: 
* ``
* ``

Dowload your file with scp (you can also use FileZilla): 
* ``

# Miscellaneous
## Filezilla 
## tmux
## HPC




