# okd-ansible-setup

This ansible playbook sets up OKD on a host machine. One of my clients wanted a demo on how to setup an OpenShift single node cluster on their development machine so they could play with it. I did not use CodeReady Containers because this setup provides good talking points on the different parts of the setup that CodeReady Containers takes care of behind the scenes. OKD makes install a little more interesting to demo.

## Setup 

Two virtual machines were created on my laptop. One to serve as the Ansible master and the other is the OKD host. The playbook performs the following steps:

1. Installs docker and enables it using systemctl.
2. Configures the insecure registry for docker.
3. Configures firewalld to allow ports to be used by OKD.
4. Installs OpenShift and the OpenShift client.
5. Because they wanted a developer type demo as well, it installs Maven and Git.
6. Creates a developer sandbox and clones a nodejs-ex project to demo how OpenShift creates a container and how the code can be updated by triggering builds from the OKD Console. 
