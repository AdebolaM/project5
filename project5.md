This project focused on understanding the connection from clients and database servers such as mysql server.
I will be creating two linux environments and one for the server which I will do by creating an instance on AWS and the clients wchich I will be using Ubuntu that has been installed in my virtual box for this. 
I need to install mysql server software on the server and mysql client software on the client 
I will have to eventually connect the two 'computers' and confirm the connections. 


lets go!

unfortunately I was unable to use the unbuntu I had installed on my virtual box because it didnt have the package to install mysql-client despite update and upgrade apt 

I even try to install aptitude with 

```sudo apt install aptitude -y```

 and it says that the aptitude does not have an installation candidate 

 therefore I will have to two AWS instances to create to linux environments

 lets go again!

# mysql server
  * Installation of mysql server
       

    * Update the apt with ```sudo apt update -y```
    * I installed the server with 
 ```sudo apt install mysql-server -y```

     * I then set a password for the root user with the alter user command on mysql 
     ```ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'Password.1';``` and secured the stallation with
     
      ```sudo mysql_secure_installation```

      ![serversecure](https://github.com/AdebolaM/project5/blob/main/images/mysql%20installation%20security%20script%205.png?raw=true)
      
      ![serversecure](https://github.com/AdebolaM/project5/blob/main/images/mysql%20installation%20security%20script%205.png?raw=true)




      * I configured mysql to allow connection from all IP address by changing the bind address in the configuation file from what it is to 0.0.0.0

             ```sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf```

![serversecure](https://github.com/AdebolaM/project5/blob/main/images/allowing%20all%20ip%20address.png?raw=true)





 * I then created a database table_of_content and created a user debby and configured its password and granted debby all permission on table_of _content  
 ``` CREATE DATABSE 'table_of_content';```


   ![serversecure](https://github.com/AdebolaM/project5/blob/main/images/creating%20a%20database%20.png?raw=true)     

  * on table_of_content, I created a table 'Birthday_party' and put in the content of the table 
```
CREATE TABLE table_of_content.Birthday_party (
mysql>     item_id INT AUTO_INCREMENT,
mysql>     content VARCHAR(255),
mysql>     PRIMARY KEY(item_id)
mysql> );
```

``` 
mysql> INSERT INTO table_of_content.Birthday_party (content) VALUES (differnt value for every time);
```


![serversecure](https://github.com/AdebolaM/project5/blob/main/images/created%20a%20table%20.png?raw=true)   



 * I confirmed the the database with show databases; and used a select command to check the content of  Birthday_party table
 ``` 
 Show databases;
 SELECT * FROM table_of_content.Birthday_party;

  ```


 * finally restarted mysql with   
    ```
    sudo systemctl mysql restart
    ```

# mysql client

 * update the apt with 
 ```
  apt update -y
  ```
* I installed the server with   
 ```
 sudo apt install mysql-client -y
 ```
 * I pulled out the ip address so that I can update the inbound security rules for the server to allow treffic from the client ip address  
  ```
   ip address show
   ```

   ![serversecure](https://github.com/AdebolaM/project5/blob/main/images/edited%20inbound%20rule%205.png?raw=true) 



  * I connected with the server with 

  ```
  sudo mysql -u debby -h <server's ip address> -p
  ```
  I inputted the password and i was in!

* I confirmed this using the command to show databases and select command to view the content of birthday_party.


 ![serversecure](https://github.com/AdebolaM/project5/blob/main/images/database%20connect%20with%20table%20of%20cintec.png?raw=true)

 ![serversecure](https://github.com/AdebolaM/project5/blob/main/images/last%20picture%20project%205.png?raw=true)


 overall, I really enjoyed doing this project.

 



     

 

