1. To execute only the tagged modules
    ansible-playbook playbook14.yml --tags=tagged -b

2. To execute only the untagged modules
     ansible-playbook playbook14.yml --tags=untagged -b

3. To execute modules with a specific tag name
    ansible-playbook playbook14.yml --tags=user_creation -b
