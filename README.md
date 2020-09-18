# Common Ubuntu VPS setup
## Setup
1. Install [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).
2. Run `ansible-galaxy install -r roles/requirements.ym` to install playbooks.
3. Edit [`hosts`](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html) file.

## Init.yml
**This is included in following playbooks.**
This playbook install common software:
- unzip
- curl
- wget
- Node
  - [pm2](https://pm2.keymetrics.io/)
- Docker
- pip

` ansible-playbook init.yml -extra-vars "hostlist=your.ip.or.group.name"`
## netease.yml
This playbook runs [UnblockNeteaseMusic](https://github.com/nondanee/UnblockNeteaseMusic) service. It will apply to `netease` group. The service is started by pm2 and run on `40404` port.

## ttrss.yml
This playbook runs [Awesome TTRSS](https://ttrss.henry.wang/). Its default address is `https://yourhostaddress:181` and default credentials are `admin` and `password`