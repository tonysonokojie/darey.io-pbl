## DEVOPS TOOLING WEBSITE SOLUTION

We want to introduce a set of DevOps tools that will help our team in day to day activities in managing, developing, testing, deploying and monitoring different projects.

The tools we want our team to be able to use are well known and widely used by multiple DevOps teams, so we will introduce a single DevOps Tooling Solution that will consist of:

Jenkins – free and open source automation server used to build CI/CD pipelines.
Kubernetes – an open-source container-orchestration system for automating computer application deployment, scaling, and management.
Jfrog Artifactory – Universal Repository Manager supporting all major packaging formats, build tools and CI servers. Artifactory.
Rancher – an open source software platform that enables organizations to run and manage Docker and Kubernetes in production.
Grafana – a multi-platform open source analytics and interactive visualization web application.
Prometheus – An open-source monitoring system with a dimensional data model, flexible query language, efficient time series database and modern alerting approach.
Kibana – Kibana is a free and open user interface that lets you visualize your Elasticsearch data and navigate the Elastic Stack.

Setup and technologies used in Project 7
As a member of a DevOps team, you will implement a tooling website solution which makes access to DevOps tools within the corporate infrastructure easily accessible.

In this project you will implement a solution that consists of following components:

Infrastructure: AWS
Webserver Linux: Red Hat Enterprise Linux 9
Database Server: Ubuntu 20.04 + MySQL
Storage Server: Red Hat Enterprise Linux 9 + NFS Server
Programming Language: PHP
Code Repository: GitHub

On the diagram below you can see a common pattern where several stateless Web Servers share a common database and also access the same files using Network File Sytem (NFS) as a shared file storage. Even though the NFS server might be located on a completely separate hardware – for Web Servers it look like a local file system from where they can serve the same files.

<img width="871" alt="Screenshot 2023-05-08 at 08 00 14" src="https://user-images.githubusercontent.com/116417007/236756410-3409ca0c-24cd-4aa4-8b0e-6494d74ee6ca.png">

It is important to know what storage solution is suitable for what use cases, for this – you need to answer following questions: what data will be stored, in what format, how this data will be accessed, by whom, from where, how frequently, etc. Base on this you will be able to choose the right storage system for your solution.


<img width="1440" alt="nfs 1" src="https://user-images.githubusercontent.com/116417007/236756747-ae1b956e-199a-44b7-b993-ef65aa675eee.png">
<img width="1440" alt="nfs 2" src="https://user-images.githubusercontent.com/116417007/236756754-e103d48c-e89a-459e-bb51-bf15801a9b63.png">
<img width="1440" alt="nfs 3" src="https://user-images.githubusercontent.com/116417007/236756757-7bb15109-2d8a-42c2-b801-bc941fe4b1f0.png">
<img width="1440" alt="nfs 4" src="https://user-images.githubusercontent.com/116417007/236756759-ac799bf9-a8fc-485e-a760-734bc8afb91f.png">
<img width="1440" alt="nfs 5" src="https://user-images.githubusercontent.com/116417007/236756762-92012935-617c-4a98-8cbb-d8477de5acc0.png">
<img width="1440" alt="nfs 6" src="https://user-images.githubusercontent.com/116417007/236756765-cd5e9c64-822d-4110-a0fa-338c9f6b03db.png">

<img width="1440" alt="web1-1" src="https://user-images.githubusercontent.com/116417007/236758891-e5c3d35b-9d10-40ea-b0e4-f216af61a314.png">
<img width="1440" alt="web1-2" src="https://user-images.githubusercontent.com/116417007/236758896-b0e1fede-da38-4362-858d-94863c8b78dd.png">
<img width="1440" alt="web1-3" src="https://user-images.githubusercontent.com/116417007/236758899-bffa8e65-a1ed-4c76-b5c2-87083369e1f1.png">
<img width="1440" alt="web1-4" src="https://user-images.githubusercontent.com/116417007/236758902-125a917a-fa8e-426a-a88c-f126560efcc5.png">

<img width="1440" alt="web2-1" src="https://user-images.githubusercontent.com/116417007/236759616-acfca187-9709-43de-8e9e-98b3cfa7f6da.png">
<img width="1440" alt="web2-2" src="https://user-images.githubusercontent.com/116417007/236759624-1cab0453-6d26-4d68-ba5d-9324d0341038.png">

<img width="1440" alt="web3-1" src="https://user-images.githubusercontent.com/116417007/236760146-bc359df1-9ee0-40c6-a68b-c0366bec20c3.png">
<img width="1440" alt="web3-2" src="https://user-images.githubusercontent.com/116417007/236760157-4f7ebb51-e747-42e1-aceb-6829553f4674.png">

<img width="1440" alt="dt 1" src="https://user-images.githubusercontent.com/116417007/236761131-a2d2d108-1c97-4079-8957-4a51d4d7f453.png">
<img width="1440" alt="dt 2" src="https://user-images.githubusercontent.com/116417007/236761138-d6b93cbd-d619-49e2-b806-769a8c0b59e7.png">
<img width="1440" alt="dt 3" src="https://user-images.githubusercontent.com/116417007/236761148-83edf958-beda-45ef-b5d2-eac07060eab2.png">
<img width="1440" alt="dt 4" src="https://user-images.githubusercontent.com/116417007/236761151-17d5f950-6158-4f30-b280-30dd8ba995b0.png">
<img width="1440" alt="dt 5" src="https://user-images.githubusercontent.com/116417007/236761154-f1b15fd6-0415-4860-b7a6-0783d0a95866.png">

<img width="1076" alt="php login" src="https://user-images.githubusercontent.com/116417007/236761331-01b136ce-214e-4ee2-bccc-b3da7119908c.png">
<img width="1382" alt="admin home page 1" src="https://user-images.githubusercontent.com/116417007/236761465-21d60f50-c51f-46f9-a51f-471f23411934.png">
<img width="1382" alt="admin home page 2" src="https://user-images.githubusercontent.com/116417007/236761470-bf22b85a-9e04-49e2-8385-831452b57df8.png">


