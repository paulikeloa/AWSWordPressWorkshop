
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
VPC
EC2 (Instances)
Security -

## Parts of a Wordpress Website

1. Server
2. Web Server
3. Database
4. Content
5. DNS
6. Certificates (SSL/TLS)

## Migration

### Preparing the source

Access wordpress admin
Install All-in-One WP Migration
https://github.com/onepagezen/all-in-one-wp-migration-unlimited/archive/master.zip
Export 


### Preparing the destination

Easy or manual?
Easy method
Launch EC2 Instance → t2.micro, Bitnami AMI
Manual
Launch EC2 Instance → t2.micro, choose Linux of choice (Ubuntu for example)
Connect to server (ssh)
Install mysql-server → 
apt-get install mysql-server
Create database: 
create database wordpress;
create user 'wordpress'@'localhost' identified by 'AWSworkshop';
grant all privileges on *.* to 'wordpress'@'localhost';
flush privileges;
Download Wordpress to the server
wget https://wordpress.org/latest.tar.gz
tar -xzvf latest.tar.gz
cp wordpress/* /var/www/html
configure wp-config.php
Install wp: `http://example.com/wp-admin/install.php`
 hps://wordpress.org/latest.tar.gz

Access wordpress admin
Install All-in-One WP Migration plugin
https://github.com/onepagezen/all-in-one-wp-migration-unlimited/archive/master.zip
Import

## Cut-Over

Update DNS records to new IP address
Shutdown Source

## 

## 





