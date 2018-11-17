# Prerequesites
- Install Ansible
- `ansible-galaxy install nickjj.docker`
- `ansible-galaxy install geerlingguy.security`
- `ansible-galaxy install geerlingguy.firewall`
- `ansible-galaxy install dev-sec.os-hardening`
- `ansible-galaxy install geerlingguy.ruby`
- Create `hosts` file with your server endpoints. You can rename `hosts.example`
- `ansible-playbook -i hosts ansible-playbook.yml`


## Tips

- Unmount properly: `fusermount -uz /home/debian/homecloud_storage/`
- Run dropbox container: `docker run -d --restart=always --name=dropbox -v /home/debian/dropbox_backup:/dbox/Dropbox -e DBOX_UID=xxx janeczku/dropbox`
- error "User does not have connect privileges" `delete db, put installed=false in config.php of nextcloud, start db, restart nextcloud`