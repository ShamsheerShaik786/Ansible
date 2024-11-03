1 Handlers are modules that are executed if some other module is executed succesfully and it has made some changes.

2 Handlers are only executed after all the modules in the tasks section are executed

3 Handlers are executed in the order that they are mentioned in the handlers section and not in the order that they are called in the tasks section

4 Even if a handler is called multiple times in the tasks section it will be executed only once

**Playbook executing first time** 

![Screenshot (90)](https://github.com/user-attachments/assets/5902d47e-6bd2-4935-b8c7-e44ae61c2182)

**Playbook executing second time it's skipping handlers section**

![Screenshot (91)](https://github.com/user-attachments/assets/a5be0635-1f08-46bf-b752-e6d3ffa654b1)

