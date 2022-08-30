###########################################################################################

This is readme file for running playbook that install EBO appl's on STG/ACC/PRD servers

###########################################################################################

! All commands should be run under root (sudo su - root)


***
Preparation steps
***


1. Copy installation files as *zip archives to local folder: /tmp/install/EBO
~~~~~
e.g.

root@srva530:/tmp/install/EBO# ll
total 12
drwxr-xr-x 3 root    root    4096 Apr 12 08:07 ./
drwxrwxrwx 3 root    root    4096 Apr 12 08:07 ../
drwxrwxr-x 2 YuchkAl YuchkAl 4096 Apr 12 07:45 EBO24HF2/

-------------------------------------------------------

***
Run playbook
***
!NOTE: root env. variable is set:
~~~
export ANSIBLE_VAULT_PASSWORD_FILE=..... on ~/.bashrc file
~~~

1. On ACC
/This will install EBO2TI and MIV on SRVA557/

root@srva530:~/ansible# ansible-playbook playbook_EBO_ACC_STG_inst.yml -l ACC

~~~~
e.g.

root@srva530:~/ansible# ansible-playbook playbook_EBO_ACC_STG_inst.yml -l ACC
Enter folder name will be created on ACC/STG server: EBO24HF2 #######-->Folder name on /tmp/install/EBO
Enter local source folder for copying: EBO24HF2 #####--> Folder name on target server
~~~~

2. On STG
/This will install EBO2TI and MIV on SRVA518/

root@srva530:~/ansible# ansible-playbook playbook_EBO_ACC_STG_inst.yml -l STG

~~~~
e.g.
root@srva530:~/ansible# ansible-playbook playbook_EBO_ACC_STG_inst.yml -l STG
Enter folder name will be created on ACC/STG server: EBO24HF2 #######-->Folder name on /tmp/install/EBO
Enter local source folder for copying: EBO24HF2 #####--> Folder name on target server
~~~~

/This will install EBO2TI and MIV on SRVA518 and MIV on SRVA575 and SRVA576/

root@srva530:~/ansible# ansible-playbook playbook_EBO_ACC_STG_inst.yml -l 'STG, Citrix_Stg'

3. On PRD
/This will install EBO2TI on all PRD servers and MIV appl on Citrix Farm/

root@srva530:~/ansible# ansible-playbookl playbook_EBO_PRD_inst.yml

===============================================================================

!!NOTE:

-1-

---
During playbook task run the following TASK pause appear:
---

TASK [pause] ****************************************************************************************************
[pause]
############################################################################
.....
---
Just  read the output and follow the steps
---

-2-

---
All errors that appear are expected errors and could be ignored
---





