## ANSIBLE REFACTORING AND STATIC ASSIGNMENTS (IMPORTS AND ROLES)
In this project you will continue working with ansible-config-mgt repository and make some improvements of your code. Now you need to refactor your Ansible code, create assignments, and learn how to use the imports functionality. Imports allow to effectively re-use previously created playbooks in a new playbook – it allows you to organize your tasks and reuse them when needed.
Code Refactoring
Refactoring is a general term in computer programming. It means making changes to the source code without changing expected behaviour of the software. The main idea of refactoring is to enhance code readability, increase maintainability and extensibility, reduce complexity, add proper comments without affecting the logic.

<img width="1440" alt="Screenshot 2023-06-05 at 04 58 20" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/6dfc5d83-6eff-4978-819b-ad5da4759a38">
<img width="1440" alt="Screenshot 2023-06-05 at 04 58 37" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/76cdfc4c-c433-4b40-86f0-3578271b5e99">
<img width="1440" alt="Screenshot 2023-06-05 at 04 58 56" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/027b9f53-eb9a-405d-9fb6-c470cee2733c">
<img width="1440" alt="Screenshot 2023-06-05 at 04 59 14" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/071e0b3e-bb59-4d78-b7f3-e9ea543ea8a9">
<img width="1440" alt="Screenshot 2023-06-05 at 04 59 35" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/a3e79aba-cdd8-4829-808c-9c029b91fd9a">
<img width="1440" alt="Screenshot 2023-06-05 at 04 59 57" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/b7516210-e59e-4c6d-a78a-59e9ddd69efb">
<img width="1440" alt="Screenshot 2023-06-05 at 08 29 06" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/ff115c61-a4ba-491b-a039-563bde580339">
<img width="1440" alt="Screenshot 2023-06-05 at 08 29 20" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/0b72be16-ff59-488e-b108-9c0fcef769e8">
<img width="1185" alt="Screenshot 2023-06-05 at 08 58 00" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/f9e20778-cd5e-4a82-a572-3018561ca544">
<img width="1185" alt="Screenshot 2023-06-05 at 08 58 48" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/9c19437c-4d66-443f-96d3-a8c26c658d1f">
<img width="1185" alt="Screenshot 2023-06-05 at 09 00 04" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/de229ffe-9515-45ea-86c1-7de8f0ba2504">
<img width="1185" alt="Screenshot 2023-06-05 at 09 10 22" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/bdb8a08f-e8d6-4dfc-99cf-4d467b902fdc">
<img width="1185" alt="Screenshot 2023-06-05 at 09 11 56" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/d2befd0e-bd00-4135-b26c-0cc4a1fba9e1">
<img width="1440" alt="Screenshot 2023-06-05 at 13 24 18" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/be76c35e-1069-4382-94cf-dc699ee2cd15">
<img width="1440" alt="Screenshot 2023-06-05 at 13 24 36" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/ac6b4c60-8056-4500-9097-e19dc1a00162">
<img width="1440" alt="Screenshot 2023-06-05 at 13 27 00" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/18ee5879-361b-4733-b7e0-8e54f6c36459">
<img width="1440" alt="Screenshot 2023-06-05 at 13 27 12" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/201ee3cc-004a-43cf-b72a-7061303192b0">
<img width="1440" alt="Screenshot 2023-06-05 at 17 05 18" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/a98741eb-5621-4676-aea6-8969cc8141cd">
<img width="1312" alt="Screenshot 2023-06-05 at 17 09 32" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/a8300947-f7a3-44d5-bae4-2e69d328e558">
<img width="1312" alt="Screenshot 2023-06-05 at 17 10 27" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/54b626bb-84ed-46db-ae91-d3d0805dcbb7">
<img width="1311" alt="Screenshot 2023-06-05 at 17 11 44" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/e5cab922-9b3d-4728-be7e-8904f754e541">
<img width="1311" alt="Screenshot 2023-06-05 at 17 12 26" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/0d5d79fc-0924-4aee-9111-2079ab691834">
<img width="1439" alt="Screenshot 2023-06-05 at 17 15 37" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/3144bf32-1e3a-4c2b-b20e-09cb65b6fbb3">
<img width="836" alt="Screenshot 2023-06-05 at 17 24 21" src="https://github.com/tonysonokojie/darey.io-pbl/assets/116417007/507df114-a17b-4b07-8a79-305bae0695e7">
