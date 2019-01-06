# packer-aws-logstash

Packer based project for provisioning a "Kafka" image using Ansible remote, 
and Serverspc, for AWS, or Virtualbox, with Elastic monitoring.

## Requirements

To use this project, you must have installed:
- [Packer](https://www.packer.io/downloads.html)
- [Ansible](http://docs.ansible.com/ansible/latest/intro_installation.html)
- [Serverspec](http://serverspec.org/)
- [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/installing.html)
- [jq](https://stedolan.github.io/jq/)

(Optional)
- [Virtualbox](https://www.virtualbox.org/wiki/Downloads)
- [Vagrant](https://www.vagrantup.com/downloads.html)

## Deploy to AWS, with Packer
```shell
git clone https://github.com/apolloclark/packer-aws-kafka
cd ./packer-aws-kafka/base
# create a keypair named "packer" or change lines 26, 27 in build_packer_aws.sh
./build_packer_aws.sh
```

## Deploy to Virtualbox, with Vagrant
```shell
git clone https://github.com/apolloclark/packer-aws-kafka
cd ./packer-aws-kafka/config
vagrant up
vagrant ssh
```

## Ansible

Ansible Roles:
- [geerlingguy.firewall](https://github.com/geerlingguy/ansible-role-firewall)
- [apolloclark.kafka](https://github.com/apolloclark/ansible-role-kafka)
- [apolloclark.zookeeper](https://github.com/apolloclark/ansible-role-zookeeper)
<br/><br/><br/>



## Log Files

*Logstash*
```
service logstash status | cat
/usr/share/logstash/bin/logstash --version
nano /etc/logstash/logstash.yml
nano /var/log/logstash/logstash-plain.log
tail -f /var/log/logstash/logstash-plain.log
```