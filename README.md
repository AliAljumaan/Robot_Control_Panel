# Robot_Control_Panel
The purpose of this project is to demonstrate how to control the robot's movement using a webpage and connect it to a database. Therefore, every action the robot takes will be recorded in the database. To do this project we will be going to use the following.
* HTML file
* CSS file 
* PHP file 
* Database
## HTML file 
The code for the HTML file.
```
<html>
<title>Control Panel</title>
<link rel="stylesheet" type="text/css" href="nnn.css">
<body>
        <form action="connect.php" method="get">
 
        <button class="bt_f" name="forward">Forward</button></br></br>
        <button class="bt_l" name="left">Left</button> 
        <button class="bt_s" name="stop">Stop</button>
        <button  class="bt_r"name="right">Right</button>
        </br> </br><button class="bt_b" name="backward">Backward</button>
</form>
</body>
</html>
```
## CSS file 
The code for the CSS file.

```

body{
	font-family: arial;
	font-size: 18px;
	margin: 0;
	color: #000;
	display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
}
.bt_f{
	margin-left: 125;
	width: 120px;
	padding: 8px 20px;
	background: #ddcbff;
	border: 2px solid #7b3af3;
	color: rgb(0, 0, 0);
	font-size: 18px;
	cursor: pointer;
	border-radius: 10px;
  }
  .bt_f:hover {
	background-color:#be9aff;
	transition: 0.7s;
  }
.bt_l{
	width: 120px;
	padding: 8px 20px;
	background: #ddcbff;
	border: 2px solid #7b3af3;
	color: rgb(0, 0, 0);
	font-size: 18px;
	cursor: pointer;
	border-radius: 10px;
  }
  .bt_l:hover {
	background-color:#be9aff;
	transition: 0.7s;
  }
  .bt_s{
	width: 120px;
	padding: 8px 20px;
	background: #ffd5d5;
	border: 2px solid #f81414;
	color: rgb(0, 0, 0);
	font-size: 18px;
	cursor: pointer;
	border-radius: 10px;
  }
  .bt_s:hover {
	background-color:#ffaeae;
	transition: 0.7s;
  }
  .bt_r{
	width: 120px;
	padding: 8px 20px;
	background: #ddcbff;
	border: 2px solid #7b3af3;
	color: rgb(0, 0, 0);
	font-size: 18px;
	cursor: pointer;
	border-radius: 10px;
  }
  .bt_r:hover {
	background-color:#be9aff;
	transition: 0.7s;
  }
  .bt_b{
	margin-left: 125;
	width: 120px;
	padding: 8px 20px;
	background: #ddcbff;
	border: 2px solid #7b3af3;
	color: rgb(0, 0, 0);
	font-size: 18px;
	cursor: pointer;
	border-radius: 10px;
  }
  .bt_b:hover {
	background-color:#be9aff;
	transition: 0.7s;
  }

```
## PHP file 
The code for the PHP file.
```
<?php
// Database connection
$conn = new mysqli('localhost','root','','database');
if($conn->connect_error){
    echo "$conn->connect_error";
    die("Connection Failed : ". $conn->connect_error);
} else {
        if(isset($_GET['forward'])){
           $forward='F';
    $stmt = $conn->prepare("insert into data(Svalue) values(?)");
    $stmt->bind_param("s", $forward);
    $execval = $stmt->execute();
    echo $execval;
    echo "F";
    $stmt->close();
    $conn->close();
        }   
        if(isset($_GET['stop'])){
            $stop='S';
     $stmt = $conn->prepare("insert into data(Svalue) values(?)");
     $stmt->bind_param("s", $stop);
     $execval = $stmt->execute();
     echo $execval;
     echo "S";
     $stmt->close();
     $conn->close();
         }  
        if(isset($_GET['backward'])){
            $backward='B';
     $stmt = $conn->prepare("insert into data(Svalue) values(?)");
     $stmt->bind_param("s", $backward);
     $execval = $stmt->execute();
     echo $execval;
     echo "B";
     $stmt->close();
     $conn->close();
         }
         if(isset($_GET['right'])){
            $right='R';
     $stmt = $conn->prepare("insert into data(Svalue) values(?)");
     $stmt->bind_param("s", $right);
     $execval = $stmt->execute();
     echo $execval;
     echo "R";
     $stmt->close();
     $conn->close();
         } 
         if(isset($_GET['left'])){
            $left='L';
     $stmt = $conn->prepare("insert into data(Svalue) values(?)");
     $stmt->bind_param("s", $left);
     $execval = $stmt->execute();
     echo $execval;
     echo "L";
     $stmt->close();
     $conn->close();
         }   

}
?>
```
## The Result 
![image](https://user-images.githubusercontent.com/108624020/183235902-6c3b6587-d880-4802-aa92-9359d86b70d6.png)
