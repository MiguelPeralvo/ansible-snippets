#DESCRIPTION

Variation of the ec2 provisioning playbooks/roles examples provided by Allan Denot in:

[Blog](http://allandenot.com/devops/2015/01/31/provisioning-ec2-hosts-with-ansible.html)
[GitHub](https://github.com/adenot/blog-ansible-provision-ec2)

These modified playbooks are intended for practice and learning. They are not generic/robust enough for production usage.

#USAGE

1. Copy vars/main.yml.template into vars/main.yml
2. Edit the following variables of vars/main.yml to use your private aws resources: _ec2_keypair_, _ec2_security_group_, _vpc_subnet_id_.
3. Run it with the following syntax:

```
ansible-playbook -i hosts create_ec2.yml [variables override] 

###variables override
-e "variable1_to_override_name:variable1_to_override_name"
-e "variable2_to_override_name:variable2_to_override_name"
...
-e "variablen_to_override_name:variablen_to_override_name"
```

#EXAMPLES#
```
ansible-playbook -i hosts create_ec2.yml
ansible-playbook -i hosts create_ec2.yml -e "ec2_tag_Name=etherchainmlx3" -e "ec2_count_tag='name=etherchainmlx3'" -e "ec2_keypair="private_key" -e "ec2_security_group=sg-c43aa412" -e "vpc_subnet_id="subnet-3a3a7622"
```

