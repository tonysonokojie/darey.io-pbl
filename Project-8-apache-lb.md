## PROJECT 8: Load Balancer Solution With Apache

After completing Project-7 you might wonder how a user will be accessing each of the webservers using 3 different IP addreses or 3 different DNS names. You might also wonder what is the point of having 3 different servers doing exactly the same thing.

When we access a website in the Internet we use an URL and we do not really know how many servers are out there serving our requests, this complexity is hidden from a regular user, but in case of websites that are being visited by millions of users per day (like Google or Reddit) it is impossible to serve all the users from a single Web Server (it is also applicable to databases, but for now we will not focus on distributed DBs).

Each URL contains a domain name part, which is translated (resolved) to IP address of a target server that will serve requests when open a website in the Internet.
<img width="849" alt="Screenshot 2023-05-08 at 16 26 53" src="https://user-images.githubusercontent.com/116417007/236864912-5dd7f7f2-af0d-4625-9087-adabe81e7c30.png">

<img width="1440" alt="Screenshot 2023-05-08 at 16 12 24" src="https://user-images.githubusercontent.com/116417007/236864048-c90fa8ef-f3c8-4e0e-b40b-b7ad65a61c37.png">
<img width="1440" alt="Screenshot 2023-05-08 at 16 12 55" src="https://user-images.githubusercontent.com/116417007/236864056-615e355e-0051-4c8e-a329-355bd67eaea5.png">
<img width="1440" alt="Screenshot 2023-05-08 at 16 13 16" src="https://user-images.githubusercontent.com/116417007/236864065-c7ee5679-ce98-48fc-a550-782a87fdaf93.png">
<img width="1440" alt="Screenshot 2023-05-08 at 16 13 34" src="https://user-images.githubusercontent.com/116417007/236864072-f36fa58b-0bd6-4fc0-87b2-a7e3c11c0c42.png">
<img width="1440" alt="Screenshot 2023-05-08 at 16 14 42" src="https://user-images.githubusercontent.com/116417007/236864077-c8297587-7748-4e1e-81d7-8d320dd0b87e.png">
<img width="1440" alt="Screenshot 2023-05-08 at 16 14 50" src="https://user-images.githubusercontent.com/116417007/236864084-d51e2428-59ac-4b7c-b4d5-481ee702f0f4.png">
<img width="1352" alt="Screenshot 2023-05-08 at 16 16 03" src="https://user-images.githubusercontent.com/116417007/236864087-fd492b1c-f9b5-430a-8982-73c090717a9e.png">
<img width="1352" alt="Screenshot 2023-05-08 at 16 18 38" src="https://user-images.githubusercontent.com/116417007/236864090-2a665210-c5e4-4a7f-8771-bdd8fbb4ba8b.png">
