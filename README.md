# elasticsearch-aws

Assumptions:
1. You already have a vpc and subnet created in your aws account
2. You already have a private key created
3. You already have a security group created
   1. Make sure you are able to SSH to elasticseach instance/instances
   2. Make sure Port 9200, 9300 are allowed between elasticsearch instances for internal communication.
4. You already have terraform(Preferabely v0.13.5) and ansible(Preferabely 2.9.13) installed

# Steps:
1. Edit terraform.tfvars(located inside terraform directory) and enter your details
2. Traverse to terraform directory and enter : 
   1. terraform plan -target=module.create-instance
   2. terraform apply -target=module.create-instance ( Type yes to confirm)
4. Once instance created traverse back to main directrory and edit ec2.ini and make changes as per your environment
5. Execute:
    ansible-playbook -i ec2.py playbooks/elasticsearch.yml
