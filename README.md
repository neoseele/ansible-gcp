# ansible-gcp

> Trying out ansible with gcp intergration

## Installation

```sh
brew install ansible
pip install apache-libcloud
```

## Configuration

```sh
cd ~/projs
git clone git@github.com:neoseele/ansible-gcp.git
ln -s ~/projs/ansible-gcp/.ansible.cfg ~/.ansible.cfg
```

## Tests

```sh
## ping

cd ~/projs/ansible-gcp/
ansible -i inventory tag_ssh -m ping
...
centos-7 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
...
```

```sh
## playbook: rootpw

ansible-playbook -i inventory playbooks/rootpw.yaml -C

PLAY [tag_ansible-test] *****************************************************************************

TASK [Gathering Facts] ******************************************************************************
ok: [centos-7]

TASK [user] *****************************************************************************************
changed: [centos-7]

PLAY RECAP ******************************************************************************************
centos-7                   : ok=2    changed=1    unreachable=0    failed=0
```
