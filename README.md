# Prerequesites
- Install Ansible
- `ansible-galaxy install nickjj.docker`
- `ansible-galaxy install geerlingguy.security`
- `ansible-galaxy install geerlingguy.firewall`
- `ansible-galaxy install dev-sec.os-hardening`
- `ansible-galaxy install geerlingguy.ruby`
- Create `hosts` file with your server endpoints. You can rename `hosts.example`
- Create `deployer` user as scaleway is using root user `ansible-playbook -i hosts create-deployer-user.yml`
- Update port in hosts as ssh port became `2865`
- Copy `traefik.yml.example` and rename it to `traefik.yml`, update the content to match your domain name
- Add an `.passwd-s3fs` that you can find in your S3 like provider account (see s3fs documentation)
- `ansible-playbook -i hosts ansible-playbook.yml`


## Tips

- Unmount properly: `fusermount -uz /home/debian/homecloud_storage/`
- Run dropbox container: `docker run -d --restart=always --name=dropbox -v /home/debian/dropbox_backup:/dbox/Dropbox -e DBOX_UID=xxx janeczku/dropbox`
- error "User does not have connect privileges" `delete db, put installed=false in config.php of nextcloud, start db, restart nextcloud`
- `DELETE FROM oc_bruteforce_attempts WHERE ip = ‘aaa.bbb.ccc.ddd’;`
- Start at given task: ` ansible-playbook -i hosts ansible-playbook.yml --start-at-task="docker compose up"`