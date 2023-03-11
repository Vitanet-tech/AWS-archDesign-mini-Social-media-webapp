# AWS-archDesign-mini-Social-media-webapp

![image](https://user-images.githubusercontent.com/99427790/224476708-f151cd95-02d3-4de7-999a-11a50a321f70.png)



Below is the explanation :

We Start with deploying our owning Virtual Private Cloud (VPC) on AWS Cloud and create a Public and Private Subnet.
Spin up 2 VMs (Elastic Compute Cloud (EC2)) for the web tire, and add auto-scaling between, so it can increase or decrease depending on the traffic on the application.
Deploy a load balancer (Elastic Load Balancer (ELB) to balance loads within web servers.
Now create a DNS service (Route53) connect LB to make people access your App with the Domain name. Map the Domain name to public IP
Spin up another 2 VMs (Elastic Compute Cloud (EC2)) for the Application tire, and add auto-scaling between them in case you want to add more web pages or functionalities to the web tire.
Deploy Relational DB (RDS ) like MySQL connecting to the App server to hold your user's data.
The Number of contents like videos and pictures from your users are growing you need to connect NoSQL DB(DynamoDB) to App servers. 
Deploy DB cache engine (Elastic Cache) for keeping frequent access data between MySQL DB (RDS).
You cloud add external file storage (Simple storage service(S3)) to the webserver to create another source for users to access or view their uploaded videos and pictures.
Add a content filter (Rekognition) between the web server and ex-storage to help filter some contents that are not allowed on your app like nudity.
Duplicate the ex-storage and add video Convert ( Lambda running video converter code) between them, to accommodate user's access from mobile phones, one storage will be for web browsers and the other for mobile device users.
10. Deploy a Click Stream analysis to the app for user's clicks Actions (Kinesis) to help in monitoring and bring suggestions of things to the board, based on the user's activities on the Application like trends, types of things user's like to view, comment and post. All of these will be used to improve the App functionalities

11. Add Storage to clickstream analysis for storing the data like ex-storage (S3)

Connect spark/Hadoop(EMR service) to it, if you want to run data operations for instance sorting of data
Connect ETL (extract, transform, and load) Glue service to also push data from DynamoDB to EMR for Data cataloguing.
12. Deploy a Data warehouse (Redshift) to analyze the information gotten from EMR

Connect interactive query service (Athena) to it and also Business Intelligence tool (Quick sigh) which gives clear ideas about the data.
13. Connect Content Delivery Network (CDN) Cache Link up Edge Location to CloudFront to connect the storage to help in keeping contents close to users it will mitigate access to the main storage which also helps to reduce the charge for egress.

14. Create SMS mobile Push Notification and Email service on the server to help in sending notifications with Simple Notification Service (SNS) / Simple Email Service (SES)

15. Also deploy a Message Queue (Simple Queue Service (SQS)) to exchange messages.

16. Deploy Monitoring Dashboard (CloudWatch) to help you in checking the health of the resources like storage, CPU utilization for EC2s and others.

17. Use Inspector to get feedback about the health of the VMs.

18.  Create Identity and Access Management (IAM) for authorization to those services.

19.  Create Key Management Service (KMS) to Encryption Data at rest.

20.  Use Amazon Certificate Manager (ACM)/firewall (WAF) to secure access coming from the internet.



Now, that you have an idea about this Design, you could design yours in another simpler way or more complex.

Keep learning and keep growing…

Thank you !!!

Kindly view in full the Design via https://vitanet-tech.github.io/AWS-archDesign-mini-Social-media-webapp/
