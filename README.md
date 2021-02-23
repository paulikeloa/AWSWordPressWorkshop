
# Wordpress Migration Workshop
In this workshop, you will learn how to migrate a typical wordpress website to AWS.

## Intro to AWS

Amazon Web Services (AWS) is the world’s most comprehensive and broadly adopted cloud platform, offering over 200 fully featured services from data centers globally. Millions of customers—including the fastest-growing startups, largest enterprises, and leading government agencies—are using AWS to lower costs, become more agile, and innovate faster.

## What is migration?

A migration is when you move an application and data from one location to a new location.  

Migrations to AWS include moving any workload from an on-premises environment, hosting facility, or other public cloud. AWS is working with thousands of organizations to migrate workloads such as applications, websites, databases, storage, physical or virtual servers, or entire data centers.

## Intro to EC2

Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides secure, resizable compute capacity in the cloud. It is designed to make web-scale cloud computing easier for developers. Amazon EC2’s simple web service interface allows you to obtain and configure capacity with minimal friction. It provides you with complete control of your computing resources and lets you run on Amazon’s proven computing environment.

### Core Services
1. VPC
Amazon Virtual Private Cloud (Amazon VPC) enables you to launch AWS resources into a virtual network that you've defined. This virtual network closely resembles a traditional network that you'd operate in your own data center, with the benefits of using the scalable infrastructure of AWS. 

Amazon VPC concepts

Amazon VPC is the networking layer for Amazon EC2. 

The following are the key concepts for VPCs:

    Virtual private cloud (VPC) — A virtual network dedicated to your AWS account.

    Subnet — A range of IP addresses in your VPC.

    Route table — A set of rules, called routes, that are used to determine where network traffic is directed.

    Internet gateway — A gateway that you attach to your VPC to enable communication between resources in your VPC and the internet.

    VPC endpoint — Enables you to privately connect your VPC to supported AWS services and VPC endpoint services powered by PrivateLink without requiring an internet gateway, NAT device, VPN connection, or AWS Direct Connect connection. Instances in your VPC do not require public IP addresses to communicate with resources in the service. Traffic between your VPC and the other service does not leave the Amazon network. For more information, see AWS PrivateLink and VPC endpoints.

    CIDR block —Classless Inter-Domain Routing. An internet protocol address allocation and route aggregation methodology. For more information, see Classless Inter-Domain Routing in Wikipedia. 

2. EC2 (Instances)
3. Security -

## Parts of a Wordpress Website

Wordpress is a popular website management system and is used by millions of websites around the world. Wordpress consists of the following components
1. Server
This is the physical or virtual server
2. Web Server
This is an application that servers HTTP requests. Popular web servers are Apache and Nginx
3. Database
The database is where content, configuration, and user information is stored.  Wordpress supports common database engines such as Mysql and MariaDB
4. Content
The content is what you are sharing to your viewers.  You create content through the Wordpress inferface or compatible tools, and that content is servered to visitors of your website by the web server.
5. DNS
DNS is Domain Naming System and is used to map names to IP network addresses. 
6. Certificates (SSL/TLS)
Certificates provide security for your website. It allows the use of Secure Sockets Layer (SSL) or Transport Layer Security (TLS) which encryptes the session between the vistor web browser and the webserver. It also provides assurances to your website vistors that your address and domain are legitmate.

## Migration

Now that you have a basic understanding of Wordpress and AWS core services, you will practice a migration of a wordpress website to an EC2 Instance on AWS.

This workshop won't focus on installing and building a wordpress website. Instead it will use the Bitnami Wordpress image to launch the destination webiste.

To migrate your  wordpress website, you need to extract a copy of the data stored in the database and all files that are a part of the wordpress website.  Normally this would be complicated and involve many manual steps, but fortunately, there are plugins and tools that will assist with this.  For this workshop we will be using the "All In One WP Migration" Plugin to extract the database and files you will need to import into the new website


### Preparing the destination

Easy or manual?

### Easy method
Launch EC2 Instance → t2.micro, Bitnami AMI


### Manual manual method
1. Launch EC2 Instance → t2.micro, choose Linux of choice (Ubuntu for example)
2. Connect to server (ssh)
3. Install mysql-server 

>`
apt-get install mysql-server
`

4. Create the database: 
>
```create database wordpress;
create user 'wordpress'@'localhost' identified by 'AWSworkshop';
grant all privileges on *.* to 'wordpress'@'localhost';
flush privileges;
```
5. Download Wordpress to the server
>```wget https://wordpress.org/latest.tar.gz

tar -xzvf latest.tar.gz

cp wordpress/* /var/www/html

configure wp-config.php```

6. Install wp: `http://example.com/wp-admin/install.php`
 hps://wordpress.org/latest.tar.gz


### Preparing the source

To migrate your  wordpress website, you need to extract a copy of the data stored in the database and all files that are a part of the wordpress website.  Normally this would be complicated and involve many manual steps, but fortunately, there are plugins and tools that will assist with this.  For this workshop we will be using the "All In One WP Migration" Plugin to extract the database and files you will need to import into the new website

Log into the website you want to migrate by logging into the Wordpress Admin portal.  This will typically be found at http://<yourwebsite/wp-admin
Log in with a user that as admin level privileges

Install All-in-One WP Migration
https://github.com/onepagezen/all-in-one-wp-migration-unlimited/archive/master.zip
Export the archive to your local computer



## Migration
Access wordpress admin
Install All-in-One WP Migration plugin
https://github.com/onepagezen/all-in-one-wp-migration-unlimited/archive/master.zip
Import from the saved archive file


Update DNS records to new IP address
Shutdown Source

## 

## 





