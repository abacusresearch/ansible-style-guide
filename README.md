# ansible-style-guide

Presentation in 
https://github.com/abacusresearch/ansible-style-guide/blob/main/Ansible_Style_Guide_CfgMgmtCamp2026.pdf

https://cfp.cfgmgmtcamp.org/ghent2026/talk/NNFGN9/

# Survey, question on certain questions of code style for Ansible

https://volenbovskyi.limesurvey.net/566988

https://forum.ansible.com/t/survey-on-various-ansible-style-questions-cfgmgmtcamp-follow-up/45302/8

As of February 2026 around 20 people answered each of the questions; both by people actively contributing to Ansible (core team members, maintainers, etc.) and by Ansible users.

## Results

# Questions with answers on which (almost) everyone agrees on

1. Are the quotes necessary for *all* strings?

Community answer: no, it is not necessary to quote all strings

So below is just fine:

`apache_package_name: httpd`

3. What is the preferred option for "external" quotes?

Community answer: Double quotes (`"`)

4. What are the verb(s) that should be used within a task name, "Install, create, configure" or "Ensure"

Community answer: Prefer `Install`, `Create`, `Configure`, etc. etc. in task names over  `Ensure`

5. What is the preferred notation for lists and dictionaries?
Community answer: Block-style notation over flow-style

Block-style:

```
Example for a list:
tags: 
  - install
  - configure
Example for a dictionary:
user: 
  name: Alice
  age: 30
```
instead of

```
tags: [install,configure]
...
user: {name: Alice, age: 30}

```

### Questions where overwhelming majority has chosen one option over ther other

6. What is preferred inventory format?
   
Community answer: YAML

### Questions where majority chooses one option over the other one but it is (almost) a tie

7. Is it good practice to prefix internal variables with double undescores and use r_ prefix for variables used in "register" task attribute?

Community answer: no

9. What is the preferred dictionary notation?

Community answer: Dot notation is preferred over bracket notation for dictionaries

`{{ my_dictionary.mykey }}` over `{{ my_dictionary['mykey'] }}`

Other notes: 

- `meta/main.yml` is used and maintained

- `meta/argument_specs.yml` is used and maintained
