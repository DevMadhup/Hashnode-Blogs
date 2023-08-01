---
title: "Python Data Types and Data Structures for DevOps"
seoDescription: "Devops, Python for Devops, Automation with Python, Python"
datePublished: Tue Aug 01 2023 15:41:07 GMT+0000 (Coordinated Universal Time)
cuid: clksgv15e000y0amebev5b4hg
slug: python-data-types-and-data-structures-for-devops
tags: python, automation, devops, 90daysofdevops, trainwithshubham

---

## **List:**

* A list is an ordered collection of items.
    
* Elements in a list are enclosed in square brackets `[ ]`.
    
* Lists are mutable, meaning you can add, remove, or modify elements after creation.
    
* Lists can contain duplicate elements.
    

### Hands-on Example for List:

```plaintext
# Creating a list
fruits_list = ["apple", "banana", "orange", "apple", "grape"]

# Modifying the list
fruits_list[0] = "kiwi"
fruits_list.append("watermelon")

# Displaying the list
print(fruits_list)
```

Output:

```plaintext
['kiwi', 'banana', 'orange', 'apple', 'grape', 'watermelon']
```

In the example, we create a list of fruits and modify it by changing the first element to "kiwi" and adding "watermelon" to the end of the list.

## **Tuple:**

* Tuple is an ordered collection of items.
    
* Elements in a tuple are enclosed in parentheses `( )`.
    
* Tuples are immutable, meaning that once created, you cannot modify, add, or remove elements.
    
* Tuples can contain duplicate elements.
    

### Hands-on Example for Tuple:

```plaintext
# Creating a tuple
fruits_tuple = ("apple", "banana", "orange", "apple", "grape")

# Trying to modify the tuple (will raise an error)
# fruits_tuple[0] = "kiwi"

# Displaying the tuple
print(fruits_tuple)
```

Output:

```plaintext
('apple', 'banana', 'orange', 'apple', 'grape')
```

In the example, we create a tuple of fruits, and when we try to modify it, we encounter an error because tuples are immutable.

## **Set:**

* The Set is an unordered collection of unique items.
    
* Elements in a set are enclosed in curly braces `{ }`.
    
* Sets are mutable, meaning you can add or remove elements after creation.
    
* Sets do not allow duplicate elements.
    

### Hands-on Example for Set:

```plaintext
# Creating a set
fruits_set = {"apple", "banana", "orange", "apple", "grape"}

# Adding elements to the set
fruits_set.add("kiwi")

# Displaying the set
print(fruits_set)
```

Output:

```plaintext
{'kiwi', 'banana', 'apple', 'grape', 'orange'}
```

In the example, we create a set of fruits, and you can see that duplicate elements are automatically removed from the set. We also add "kiwi" to the set.

To summarize:

* Lists are ordered and allow duplicates. They are mutable, so you can modify them after creation.
    
* Tuples are ordered and allow duplicates. However, they are immutable, so you cannot change their elements after creation.
    
* Sets are unordered and do not allow duplicates. They are mutable, so you can add or remove elements after creation.
    

---

## Create below Dictionary and use Dictionary methods to print your favourite tool just by using the keys of the Dictionary

```plaintext
fav_tools = {
    1: "Linux",
    2: "Git",
    3: "Docker",
    4: "Kubernetes",
    5: "Terraform",
    6: "Ansible",
    7: "Chef"
}

# Ask the user to enter the key
user_key = int(input("Enter the key of your favorite tool (1-7): "))

# Use dictionary method to retrieve the value
favorite_tool = fav_tools.get(user_key)

# Check if the key exists in the dictionary
if favorite_tool is not None:
    print(f"Your favorite tool is: {favorite_tool}")
else:
    print("Invalid key. Please enter a key between 1 and 7.")
```

In this script, the user is prompted to enter a key (1 to 7) corresponding to their favourite tool. The `get()` method is then used to retrieve the value associated with the entered key from the `fav_tools` dictionary. If the key exists, it will print the favourite tool; otherwise, it will show an error message for an invalid key.

When you run the script and input a valid key, it will print your favourite tool based on the key entered. For example:

```plaintext
Enter the key of your favorite tool (1-7): 3
Your favorite tool is: Docker
```

If you enter an invalid key (e.g., 8), it will show the error message

```plaintext
Enter the key of your favorite tool (1-7): 8
Invalid key. Please enter a key between 1 and 7.
```

---

## Create a List of cloud service providers Write a program to add `Digital Ocean` to the list of cloud\_providers and sort the list in alphabetical order.

```plaintext
cloud_providers = ["AWS", "GCP", "Azure"]
```

```plaintext
cloud_providers = ["AWS", "GCP", "Azure"]

# Adding "Digital Ocean" to the list
cloud_providers.append("Digital Ocean")

# Sorting the list in alphabetical order
cloud_providers.sort()

# Displaying the updated list
print("Updated List of Cloud Providers:")
for provider in cloud_providers:
    print(provider)
```

When you run this script, it will add "Digital Ocean" to the list and sort it in alphabetical order:

```plaintext
Updated List of Cloud Providers:
AWS
Azure
Digital Ocean
GCP
```

Now, the `cloud_providers` list contains "Digital Ocean" and is sorted in alphabetical order.