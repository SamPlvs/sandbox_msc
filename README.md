Congrats ! You have won a GPU. 
What you need to do, next:

## Access to your container
Each student has been assigned to a [container](https://www.docker.com/what-container), which is a small machine hosted by the system and linked to the GPUs. You can access your container via a [secure network protocol](https://en.wikipedia.org/wiki/Secure_Shell) and your [port number](https://en.wikipedia.org/wiki/Port_(computer_networking)). Make sure you are connected to the Imperial network, using a [VPN](https://www.imperial.ac.uk/admin-services/ict/self-service/connect-communicate/remote-access/method/set-up-vpn/).

* connect to your container: `ssh -p <port number> root@bg-beast.bg.ac.uk`
* change your pasword: `passwd`
* go to your repository: `cd /data/user/<user name>`

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
A virtual environnment is like a small container where you can install all the packages you need for a project. You can create as many virtual environments as you like [with conda](https://conda.io/docs/user-guide/tasks/manage-environments.html)
* `conda install -n <name environment> python=x.x` 
* `source activate <name environment>`: to activate your environment.
* `source deactivate`: to deactivate your environment.

Install your packages (ex: pytorch): 
* `source activate <name environment>`
* `conda install pytorch torchvision cuda91 -c pytorch`: you are using CUDA 9.1. 

## Recover and run your code 
Install git and clone this repo: 
* `apt-get install git`
* `git clone https://github.com/a-pouplin/sandbox_msc.git`: you can clone your own repo, also from Bitbucket
* `cd sandbox_msc`
* `conda install matplotlib`: install the packages (here you only need pytorch and matplotlib with python 2)

Run the code: 
* `CUDA_VISIBLE_DEVICES=X python main.py`: with X={0,1,2,3}. If you want to use GPU_0: X=0 

Dowload your file with [scp](https://en.wikipedia.org/wiki/Secure_copy) (you can also use FileZilla): 
* `scp -r -P <port number> root@bg-beast.bg.ic.ac.uk:<path on beast> <path on your computer>`


## Miscellaneous
* Tutorial Tianhong: [here](https://docs.google.com/document/d/1LKHZkVa6_gN9ZUpsMOahxrDiHWWGks9_FCUOdyS1Fe4/edit)
* Instead of scp your file, you can use FileZilla : [here](https://filezilla-project.org/)





