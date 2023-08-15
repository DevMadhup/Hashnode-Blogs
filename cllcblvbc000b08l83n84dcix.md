---
title: "Python Libraries for DevOps"
seoTitle: "python, json, yaml, python for devops"
seoDescription: "python, json, yaml, python for devops"
datePublished: Tue Aug 15 2023 13:09:25 GMT+0000 (Coordinated Universal Time)
cuid: cllcblvbc000b08l83n84dcix
slug: python-libraries-for-devops
tags: python, json, yaml, 90daysofdevops, trainwithshubham

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692099195963/f55bd1c1-b720-40ff-950b-78c1b0424752.png align="center")

### What is a JSON file?

* JSON is a **J**ava**S**cript **O**bject **N**otation, It is a lightweight data-interchange format.
    
* It is like plain text written in JavaScript Object Notation.
    
* Python has numerous libraries like `os`, `sys`, `json`, `yaml` etc that a DevOps Engineer uses in day-to-day tasks.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692099877012/30775580-e8cf-4606-86c1-f95b6be34f60.png align="center")

### What is a YAML file?

* YAML stands for Yet Another Markup Language. It is used to write a configuration file for the applications.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1692099786136/31adad21-b082-46e0-b60d-58fa3a88c78b.png align="center")

---

### Create a Dictionary in Python and write it to a JSON File.

```plaintext
import JSON 

#Create Dictionary 
data = {
    "name":"Madhup Pandey",
    "age":24,
    "Hobbies": ["DevOps","Cricket","Technology"]
}

#Writing to JSON file
with open(dump_data, "w") as jsonfile:
    json.dump(data, jsonfile)

#Printing message
print(f"Data has been converted into JSON file")
```

Here,

data, --&gt; is a python dictionary

with open(), --&gt; is a function to open a particular file and "w" is used to write in it.

json.dump(), --&gt; function used to write to a json file.

---

### Read a json file `services.json` kept in this folder and print the service names of every cloud service provider.

> ```plaintext
> output
> 
> aws : ec2
> azure : VM
> gcp : compute engine
> ```

```plaintext
import json

#Read json file
with open("services.json", "r") as jsonfile:
    cloud = json.load(jsonfile)

#Print cloud providers
print(f"aws :", cloud['services']['aws']['name'])
print(f"azure :", cloud['services']['azure']['name'])
print(f"gcp :", cloud['services']['gcp']['name'])
```

---

### Read YAML file using python, file `services.yaml` and read the contents to convert yaml to json.

```plaintext
import yaml
import json

with open("services.yml", "r") as yaml_file:
    yaml_data = yaml.safe_load(yaml_file)
    print(type(yaml_data))

with open("myfile.json", "w") as json_file:
    jsd = json.dump(yaml_data, json_file)
    print(jsd)
```