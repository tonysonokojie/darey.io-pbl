## ANSIBLE DYNAMIC ASSIGNMENTS (INCLUDE) AND COMMUNITY ROLES

Ansible is an actively developing software project.

Last 2 projects have already equipped you with some knowledge and skills on Ansible, so you can perform configurations using playbooks, roles and imports. Now you will continue configuring your UAT servers learning and practicing new Ansible concepts and modules.

In this project we will introduce dynamic assignments by using include module.

Now you may be wondering, what is the difference between static and dynamic assignments?

Well, from Project 12, you can already tell that static assignments use import Ansible module. The module that enables dynamic assignments is include.

Hence,

import = Static
include = Dynamic
When the import module is used, all statements are pre-processed at the time playbooks are parsed. Meaning, when you execute site.yml playbook, Ansible will process all the playbooks referenced during the time it is parsing the statements. This also means that, during actual execution, if any statement changes, such statements will not be considered. Hence, it is static.

On the other hand, when include module is used, all statements are processed only during execution of the playbook. Meaning, after the statements are parsed, any changes to the statements encountered during execution will be used.

Take note that in most cases it is recommended to use static assignments for playbooks, because it is more reliable. With dynamic ones, it is hard to debug playbook problems due to its dynamic nature. However, you can use dynamic assignments for environment specific variables as we will be introducing in this project.

<img width="1440" alt="Screenshot 2023-06-08 at 11 44 14" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/b1e7d938-b14f-4f5b-ad8b-faa17a9c39f9">
<img width="747" alt="Screenshot 2023-06-08 at 11 45 00" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/5cb6e1fe-ffce-4d37-8656-2e3a88b492ff">
