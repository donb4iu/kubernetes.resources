# Kubernetes the hard way

Kubernetes (K8S) is one of the most popular container orchestration tools available nowadays. It is available on all major cloud providers, which makes it easy to create a k8s cluster with a few clicks.

However, I believe is it important to learn how to install k8s from scratch, you can learn a lot just from the installation process. I am going to walk through how to install k8s from scratch in a development enviroment, using Linux container. Installation is further automated with Ansible. 

&nbsp;

Table of contents
--
- [Prerequisite](#prerequisite)
- [Getting Started](#getting-started)
- [Installing the Client Tools]()
- [Provisioning Compute Resources]()
- [Provisioning the CA and Generating TLS Certificates]()
- [Generating Kubernetes Configuration Files for Authentication]()
- [Generating the Data Encryption Config and Key]()
- [Bootstrapping the etcd Cluster]()
- [Bootstrapping the Kubernetes Control Plane]()
- [Bootstrapping the Kubernetes Worker Nodes]()
- [Configuring kubectl for Remote Access]()
- [Provisioning Pod Network Routes]()
- [Deploying the DNS Cluster Add-on]()
- [Smoke Test]()
- [Cleaning Up]()


&nbsp;


Prerequisite
--

- [LXC/LXD](https://github.com/sayems/lxc.resources)
- [Ansible](https://github.com/sayems/ansible.resources)


&nbsp;

Getting Started
--

##### Clone this github repo:
```bash
git clone https://github.com/sayems/kubernetes.resources.git
```

Navigate to ```k8s-the-hard-way``` directory 
```bash
$ cd kubernetes.resources/k8s-the-hard-way
```

### Start Linux Container

Now run the following command to start the Linux Container:
```bash
ansible-playbook playbook.yml
```
Now, wait for ```Linux``` container to be ready. This might take a while to complete.


### Login into Linux Container

 After the LXD box has started you can login to the Linux Container to  verify that it is running..
 
```
lxc exec loadbalancer bash
lxc exec controller-1 bash
lxc exec controller-2 bash
lxc exec controller-3 bash
lxc exec worker-1 bash
lxc exec worker-2 bash
lxc exec worker-3 bash
```
Now, ```exit``` from Linux Container by executing ```exit``` command in the terminal.


##### Test Ansible Connectivity

```bash
ansible -m ping all
```
```
192.168.199.11 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
192.168.199.22 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
192.168.199.31 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
192.168.199.21 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
192.168.199.12 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```


&nbsp;

[top](#table-of-contents)

&nbsp;


Installing the Client Tools
--

### Install CFSSL

The `cfssl` and `cfssljson` command line utilities will be used to provision a [PKI Infrastructure](https://en.wikipedia.org/wiki/Public_key_infrastructure) and generate TLS certificates.

You can install `cfssl` and `cfssljson` with Homebrew by running the following command:
```
brew install cfssl
```

### Install kubectl

The kubectl command line utility is used to interact with the Kubernetes API Server. 

You can install ```kubectl``` with Homebrew by running the following command:

```
brew install kubernetes-cli
```

&nbsp;

[top](#table-of-contents)

&nbsp;



Provisioning Compute Resources
--




&nbsp;

[top](#table-of-contents)

&nbsp;



Provisioning the CA and Generating TLS Certificates
--





&nbsp;

[top](#table-of-contents)

&nbsp;



Generating Kubernetes Configuration Files for Authentication
--




&nbsp;

[top](#table-of-contents)

&nbsp;



Generating the Data Encryption Config and Key
--




&nbsp;

[top](#table-of-contents)

&nbsp;



Bootstrapping the etcd Cluster
--




&nbsp;

[top](#table-of-contents)

&nbsp;


Bootstrapping the Kubernetes Control Plane
--




&nbsp;

[top](#table-of-contents)

&nbsp;



Bootstrapping the Kubernetes Worker Nodes
--




&nbsp;

[top](#table-of-contents)

&nbsp;



Configuring kubectl for Remote Access
--




&nbsp;

[top](#table-of-contents)

&nbsp;



Provisioning Pod Network Routes
--




&nbsp;

[top](#table-of-contents)

&nbsp;



Deploying the DNS Cluster Add-on
--




&nbsp;

[top](#table-of-contents)

&nbsp;



Smoke Test
--




&nbsp;

[top](#table-of-contents)

&nbsp;



Cleaning Up
--




&nbsp;

[top](#table-of-contents)

&nbsp;
