# Ansible configuration<br>Hubot

This Ansible config for Hubot is just a sample, do not use in production!

```
                   ___,                 _    _       ___               _
                  /   |              o | |  | |     / (_)             | | o
  _  _  _        |    |   _  _    ,    | |  | |  _ |      __   _  _   | |     __,
 / |/ |/ |  |   ||    |  / |/ |  / \_| |/ \_|/  |/ |     /  \_/ |/ |  |/  |  /  |
   |  |  |_/ \_/|/\__/\_/  |  |_/ \/ |_/\_/ |__/|__/\___/\__/   |  |_/|__/|_/\_/|/
               /|                                                     |\       /|
               \|                                                     |/       \|

 # for bot :-) for what? for Hubot!

```

![Screen shot - Hubot](https://raw.githubusercontent.com/Remiii/remiii-ansible-ubuntu-hubot/master/_documentation/image/hubot-logo.png)<br>

This Ansible config provide a sample config for your Hubot on [Slack](https://slack.com)... because Hubot needs to be shipped on a server.

![Screen shot - Ansible](https://raw.githubusercontent.com/Remiii/remiii-ansible-ubuntu-hubot/master/_documentation/image/image1.png)<br>

![Screen shot - Slack](https://raw.githubusercontent.com/Remiii/remiii-ansible-ubuntu-hubot/master/_documentation/image/image2.png)<br>

## Introduction

Ubuntu server 14.04.

Users system:
- ubuntu or vargrant... (sudo) default user
- $user (sudo)

Mark: sample user `django`.

Off course, you also need a [Slack account](https://slack.com/signin)...

## Installation

Install Ansible with your package manager (apt, brew...).

## Setup vars


### Create and update `ansible_inventory_machinename` file

Create the `ansible_inventory_machine` file from the `.dist` file
```sh
$ cp ansible_inventory_machinename.dist ansible_inventory_machinename.dist
```

For exemple (is just a sample):
```
# ansible_inventory_machinename
machine ansible_ssh_host='127.0.0.1' ansible_ssh_port=10022
```

### Create and update `vars/myConfig.yml` file from the `.dist` file

Create the `vars/myConfig.yml` file
```sh
$ cp vars/myConfig.yml.dist vars/myConfig.yml
```

For exemple (is just a sample):
```
# pathToTheProject/vars/myConfig.yml
    ...
    rootPath: '~/git/remiii-ansible-ubuntu-hubot'
    hostname: 'vm1.local'
    publicIpAddress: '127.0.0.1'
    ...
```

### Add your public key

Add the folowing files in the `vars` directory:

- mySSHPublicKey.pub



## Run Ansible

Run Ansible

```sh
$ ansible-playbook -i ansible_inventory_machinename --private-key=~/.ssh/myFuckingPrivateKey.pem -u yourDefaultUser ./myConfig.yml
```

Sample command line for Vagrant:

```sh
$ ansible-playbook -i ansible_inventory_machinename --private-key=~/.vagrant.d/insecure_private_key -u vagrant ./myConfig.yml
```

Sample command line for AmazonEC2:

```sh
$ ansible-playbook -i ansible_inventory_machinename --private-key=~/.ssh/my-private-key.pem -u ubuntu ./myConfig.yml
```

- [Ansible doc](http://docs.ansible.com/guide_vagrant.html#running-ansible-manually)

## That's it! Happy Hubing ;-)

## Some docs on Hubot and Slack Adapter

- [Hubot](https://hubot.github.com)
- [Hubot on GitHub](https://github.com/github/hubot)
- [Hubot Slack Adapter on GitHub](https://github.com/tinyspeck/hubot-slack)

## Add some script to your Hubot

- [Hubot script catalog](https://hubot-script-catalog.herokuapp.com)

## License

Licensed under the MIT license (see LICENSE.md file)

## Author

* Rémi Barbe (aka Remiii)


