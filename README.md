# playbooks
ansible playbooks for automation of tasks in linux 
ansible.cfg: this file contains inventory path, remote_users, roles path
inventory: this file contains info about the hosts ,groups
running a ansibleplaybook:
ansible-playbook playbook.yaml
playbook name can have extension of .yml or yaml
---------------------------------------------------
variables:
in ansible we can declare variables in several locations 
vars,vars_files,host_vars/hostname.yml,group_vars/groupname.yml,inventory, globally by extra-vars -e
------------------------------------------------------
fcats : facts are a predefined variables that gives system info
ansible all -m setup to know all the facts of all servers
-------------------------------------------------------
task control:
1. loop : allow the repetition of task {{item}} is used in loops
2. when : used to excecute task based on evaluation of condition
3. tags: way to control which tasks to excecute (-t is used ) or to skip --skip-tags used
4. handlers: tasks that are run only when they are notified
5. register: used to store output of result into a variable
6. ignore_errors: allows to run next task even if it encounters an error
7. block-rescue: its like a if else statement and always will be always excecuted
   ------------------------------------------------------
ad-hoc commands 
ansible all -m ping is to check ping status of all servers
ansible all -m modulename -a parameters -b to take sudo -u to guive remote user
-------------------------------------------------------
roles :
roles are combination of vars,facts,handlers and roles are reusable
it breaks playbooks into multple files 
ansible-galaxy is used to create roles
-----------------------------------------------------------
ansible-vaults is used to encrpt the keys 
