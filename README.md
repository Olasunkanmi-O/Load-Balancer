# Application Load Balancer

This project is aimed at developing beginner at the use of the application load balancer but in this case, we are making use of the AWS Elastic Load Balancer. The primary purpose of the load balancer is to balance traffic between servers to avoid overloading of a particular server.
## Procedures

1. Launch an instance and give it a name, say, server1 and we are using Redhat AMI for this instance.
![](/img/01.launch%20instance.png)
2. Create a Security Group and edit inbound rules to allow traffic from port 22(to ssh into the instance) and port 80(port to be listened to by the load balancer)
![](/img/02SG.png)
3. Launch a second instance also on RedHat AMI and call it Server2, and use the same security group
![](/img/03anotherinstance.png)
4. Access the webpage via the public IP of the server
![](/img/04server1.png)
![](/img/06webpage1.png)
5. Access the second server through its corrsponding public IP as well 
![](/img/05server2.png)
![](/img/07webpage2.png)
6. On the side bar menu, search for Target Groups
![](/img/08selectTG.png)
7. Select create target roup
![](/img/09createTG.png)
8. Choose a target type, in ths case, we are using instances
![](/img/10choose-instances.png)
9. Choose a name for your target group, this is where you also choose your VPC if you're using custom VPC
![](/img/11choose-name.png)
10.  Select the path to the health check, in our case, we use /index.html because we are using the httpd webserver, this where the homepage is.
![](/img/12health-check.png)
11. After selecting next, select both instances that will be used as target group for the loadbalancer
![](/img/13select-instances.png)
12. Click on include as pending 
![](/img/14click-below.png)
13. Click on create target group 
![](/img/15createTG.png)
14. Next, search for Load Balancer on the side menu
![](/img/16select-LB.png)
15. Click create load balancer 
![](/img/17create-LB.png)
16. Choose Application Load Balancer and click create
![](/img/18choose.png)
17. Choose a name for the load balancer
![](/img/19choosename.png)
18. Choose the VPC where your servers are existing, select at least 2 availability zones 
![](/img/20selectvpc.png)
19. Choose your security group and your target group 
![](/img/21choose-SG.png)
20. click on create load balancer 
![](/img/22click-create.png)
21. After creating, wait till the load balancer is in an active state, then copy the DNS name and paste in a browser
![](/img/23active.png)
22. After pasting the DNS, test to be sure that the link is working. Refresh the page and observe the output on the webpage
![](/img/24webpage1.png)
![](/img/25webpage2.png)
23. We have successfully distributed the traffic between the two servers 
