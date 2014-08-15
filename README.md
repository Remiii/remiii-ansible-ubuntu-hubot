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
Hubot.

This Ansible config provide a sample config for your Hubot on Slack... beacause Hubot needs to be shiped on a server.

![Screen shot - Ansible](https://raw.githubusercontent.com/Remiii/remiii-ansible-ubuntu-hubot/master/_documentation/image/image1.png)<br>
Ansible.

![Screen shot - Slack](https://raw.githubusercontent.com/Remiii/remiii-ansible-ubuntu-hubot/master/_documentation/image/image2.png)<br>
Slack.

## Introduction

Ubuntu server 14.04.

Users system:
- ubuntu or vargrant... (sudo) default user
- $user (sudo)

Mark: sample user `django`.

Off course, you also need a Slack account...

## Installation

Install Ansible with your package manager (apt, brew...).

## Setup vars

Setup the vars in `vars/myConfig.yml` and add `ansible_inventory_machinename` file.

For exemple (is just a sample):
```
# ansible_inventory_machinename
machine ansible_ssh_host='127.0.0.1' ansible_ssh_port=10022
```

Copy the config dist file `vars/myConfig.yml.dist`
```sh
$ cp vars/myConfig.yml.dist vars/myConfig.yml
```

```
# pathToTheProject/vars/myConfig.yml
    ...
    rootPath: '~/git/remiii-ansible-ubuntu-hubot'
    hostname: 'vm1.local'
    publicIpAddress: '127.0.0.1'
    ...
```

## Add vars files

Add the folowing files in the `vars` directory:

- mySSHPublicKey.pub

... TBD

## Run

* Ansible

```sh
$ ansible-playbook -i ansible_inventory_machinename --private-key=~/.ssh/myFuckingPrivateKey.pem -u yourDefaultUser ./myConfig.yml
```

Sample command line for Vagrant:

```
$ ansible-playbook -i ansible_inventory_machinename --private-key=~/.vagrant.d/insecure_private_key -u vagrant ./myConfig.yml
```

Sample command line for AmazonEC2:

```
$ ansible-playbook -i ansible_inventory_machinename --private-key=~/.ssh/my-private-key.pem -u ubuntu ./myConfig.yml
```

- [Ansible doc](http://docs.ansible.com/guide_vagrant.html#running-ansible-manually)

That's it! Happy Hubing ;-)


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


