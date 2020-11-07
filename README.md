# elasticsearch-aws

Assumptions:
1. You already have a vpc and subnet created in your aws account
2. You already have a private key created
3. You already have a security group created
4. You already have terraform and ansible installed

Steps:
1. Edit terraform.tfvars and enter your details
2. terraform plan -target=module.create-instance
3. terraform apply -target=module.create-instance
4. edit ec2.ini and make changes as per your environment
5. ansible-playbook -i ec2.py playbooks/elasticsearch.yml
