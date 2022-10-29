## Ansible basic Commands with aws ubuntu instance
Exploring ansible commands with aws ubuntu

### Commands needed
1. Create an ubuntu instance and expose port 3000 with the inbound security group

2. aws: to get all instance to with the tag Name: Project and Value: udacity, run the below command and update the inventory file
```
aws ec2 describe-instances \
\
        --query 'Reservations[*].Instances[*].PublicIpAddress' \
      --filters "Name=tag:Project,Values=udacity" \
      --output text >> inventory
```

3. Ansible commands to create, copy and run nodejs application using pm2 commands
```
 ansible-playbook main.yml -i inventory --private-key < your ansible pen key e.g ansible_key_server.pem>
```

4. visit your ip address with port 3000 to see your application 

