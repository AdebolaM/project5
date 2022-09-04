this project focus on undertanding the connection from clients and database servers such as mysql server.
I will be creating two linux environments and one for the server which i will do by creating an instance on AWS and the clients wchich i will be using Ubuntu that has been installed in my virtual box for this. 
i need to install mysql server software on the server and mysql client software on the client 
i will have to eventually connect the two 'computers' and confirm the connections. 


lets go!

unfortunately i was unable to use the unbuntu i had installed on my virtual box because it didnt have the package to install mysqlclient despite update and upgrade apt 

i even try to install aptitude with 

```sudo apt install aptitude -y```

 and it says that the aptitude does not have an installation candidate 

 therefore i will have to two AWS instances to create to linux environments

 lets go again!

# mysql server
  * installation of mysql server
       

    * update the apt with ```sudo apt update -y```
    * I installed the server with 
 ```sudo apt install mysql-server -y```

     * I then set a password for the root user with the alter user command on mysql 
     ```ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'Password.1';``` and secured the stallation with
     
      ```sudo mysql_secure_installation```


      * I configured mysql to allow connection from all IP address by changing the bind address in the configuation file. 

             ```sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf```



     * I then created a database table_of_content and created a user debby and configured its password and granted debby all permission on table_of _content
        

        * on table_of_content, i created a table 'Birthday_party' and put in the content of the table 

    * i confirmed the the database with show databases; and used a select command to check the content of  Birthday_party table

    * finally restarted mysql with ```sudo systemctl mysql restart

# mysql client

 * update the apt with 
 ```sudo apt update -y```
    * I installed the server with   
 ```sudo apt install mysql-client -y```
 * I pulled out the ip address so that I can update the inbound security rules for the server to allow treffic from the client ip address   ``` ip address show```
  * i connected with the server with 
  ```sudo mysql -u debby -h <server's ip address> -p```
  i inputted the password and i was in!

* i confirm this using he command to show databases and select command to view the content of birthday_party.




     

 

