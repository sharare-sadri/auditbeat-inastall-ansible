# Ansible Role: auditbeat

[![Build Status](https://travis-ci.org/apolloclark/ansible-role-auditbeat.svg?branch=master)](https://travis-ci.org/apolloclark/ansible-role-auditbeat)

Ansible Role to install and configure Elastic auditbeat for:
- linux
- Ubuntu 18.04 Bionic LTS
- Ubuntu 16.04 Xenial LTS
- Debian 10 Buster
- Debian 9 Stretch
- RHEL 8 UBI
- RHEL 7 UBI
- CentOS 7
- Amazon Linux 2

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `vars/main-7.2.yml`).
You can overload the variables by creating a dictionary called "auditbeat", ex:

    auditbeat:
      version: 7.3.0

## Dependencies

None.

## Example Playbook

    - hosts: all
      roles:
        - apolloclark.auditbeat

## Testing

```sh
# run all tests, against all supported OSes
./travis_tests.sh

# Execute

to run ansible playbook, there are three ways to run it by installation_type parameter
Redhat
Debian
Linux
with these three above value, you can run the main playbook.
if you put the value of installation_type to Rehhat the install-Redhat playbook on task directory would be run for Redhat package
if you put the value to Debian the install-Debian would be run for Debian package
and if you put the value to linux the  install-linux would be run without apt installtion and with binary file.

ansible-playbook -i ~/ansible-inventory/inventory.yml  -l hostname  main.yml -e installation_type=linux 


# install dependencies, setup pipenv
pip install --user pipenv
pipenv install -r test-requirements.txt --python 2.7

# run all test scenarios, defaults to Ubuntu 18.04 Bionic
pipenv run molecule test --all

# run a single test scenario
pipenv run molecule test --scenario=[default]

# build a specific environment, for manual debugging
pipenv run molecule converge
docker exec -it auditbeat-ubuntu_bionic /bin/bash
    cat /etc/os-release
    ps aux
    systemctl status auditbeat
    apt-get install -y net-tools curl nano
    ss -tlu | netstat -tunlp
    curl localhost:8080
    cd /var/log/auditbeat
```

## License

MIT / BSD

## Author Information

This role was created in 2017 by [Apollo Clark](https://www.apolloclark.com/)


