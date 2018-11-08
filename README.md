# Prerequesites
- Install Ansible
- `ansible-galaxy install nickjj.docker`
- `ansible-galaxy install geerlingguy.security`
- `ansible-galaxy install geerlingguy.firewall`
- `ansible-galaxy install dev-sec.os-hardening`
- `ansible-galaxy install geerlingguy.ruby`
- Create `hosts` file with your server endpoints. You can rename `hosts.example`
- `ansible-playbook -i hosts ansible-playbook.yml`
