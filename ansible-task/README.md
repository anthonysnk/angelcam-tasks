# Steps

## Install Ansible in macbook

```bash
brew install ansible
```

## Run docker compose tu run ubuntu

```bash
ssh-keygen -f ~/Ansible-Task/id_rsa
docker-compose up
```

## Run Playbook

```bash
# ansible-vault create ./secrets/secret_vars.yml
# Create new password example: 12345
# write secrets
ansible-playbook -i ./playbooks/inventory.ini --ask-vault-pass ./playbooks/playbook.yml
```
