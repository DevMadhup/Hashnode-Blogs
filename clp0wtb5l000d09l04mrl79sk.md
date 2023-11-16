---
title: "Creating an EC2 instance on AWS using AWSCLI"
seoTitle: "Awscli"
datePublished: Wed Nov 15 2023 18:30:00 GMT+0000 (Coordinated Universal Time)
cuid: clp0wtb5l000d09l04mrl79sk
slug: creating-an-ec2-instance-on-aws-using-awscli
tags: cloud, aws, aws-cli, trainwithshubham

---

### <mark>Install AWSCLI</mark>

```plaintext
sudo apt update
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
```

<mark>Note</mark>: if unzip command not installed

> sudo apt install unzip

### <mark>Create Key pair</mark>

```plaintext
aws ec2 create-key-pair --key-name MyKeyPair
```

### <mark>Create Security Group to attach to ec2 instance</mark>

```plaintext
aws ec2 create-security-group --group-name=my-sg --description="My security group"
```

<mark>Note:</mark> Copy group-id

### <mark>Add inbound rule to security-group</mark>

```plaintext
aws ec2 authorize-security-group-ingress --group-id=sg-0732102fbf4ea2fe3 --protocol=tcp --port=443 --cidr=0.0.0.0/0
aws ec2 authorize-security-group-ingress --group-id=sg-0732102fbf4ea2fe3 --protocol=tcp --port=22 --cidr=0.0.0.0/0
aws ec2 authorize-security-group-ingress --group-id=sg-0732102fbf4ea2fe3 --protocol=tcp --port=80 --cidr=0.0.0.0/0
```

### <mark>Create instance</mark>

```plaintext
aws ec2 run-instances --image-id=ami-0fc5d935ebf8bc3bc --instance-type=t2.micro --region=us-east-1 --key-name=MyKeyPair --security-groups=my-sg
```

Check your ec2 dashboard and try to access your instance.

Congratulations 🎉

You have created an ec2 instance using AWSCLI.

Do follow me on Linkedin: [Linkedin-MadhupPandey](https://www.linkedin.com/in/madhup-pandey-0311821b3?trk=contact-info) for more such an interesting AWS services.