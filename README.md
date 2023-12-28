# Web Security
## PHP & SQL

### Lab Overview
This lab delves into PHP scripting and SQL database management. Students will gain hands-on experience by creating PHP scripts, uploading them using FileZilla, and manipulating data within MySQL databases. The lab aims to provide a comprehensive understanding of server-side scripting and database management crucial for web development and security.

### Lab Requirements
- Internet connectivity & VMware Workstation version 15.5.7 or above
- Configured environment with PHP on Windows 10 VM and MySQL on Ubuntu Server

### Lab Tasks and Screenshots

### Part 01: Build a Basic PHP Script and Upload Using FileZilla
**Task**: Create a basic PHP script and upload it to the Ubuntu Web Server using FileZilla.
- **Steps**:
    1. Launch Notepad++ or another text editor on your Windows 10 VM to create a new file called `folusername_test.php`.
    2. Write a basic PHP script to echo a simple message.
    3. Save the file on your desktop.
    4. Use FileZilla to connect to your Ubuntu Web Server and upload the `folusername_test.php` file to the web server directory.
    5. Access the script via a web browser to view the executed PHP.
- **Slide 01**: Screenshot showing the FileZilla interface with the PHP file uploaded and the browser displaying the executed PHP script.
    <img src="https://i.imgur.com/5s7fOjI.png" height="400px" width="auto" alt="Uploading PHP Script via FileZilla"/>

### Part 02: Enhance PHP Script with Variables and Functions
**Task**: Modify the PHP script to include variables and the `printf()` function to output dynamic content.
- **Steps**:
    1. Edit the PHP script to include variables such as date and name. Utilize the `printf()` function for formatted output.
    2. Save the modified script and use FileZilla to re-upload it to the web server.
    3. Refresh the browser page to view the updated script output.
- **Slide 02**: Screenshot showing the enhanced PHP script with variables and formatted text executed on the server.
    <img src="https://i.imgur.com/U0sWISW.png" height="400px" width="auto" alt="Enhanced PHP Script"/>

### Part 03: Include Hidden Server File in PHP Script Using FileZilla
**Task**: Utilize the PHP include function to incorporate the content of a hidden server file (`accounts.txt`) into the PHP script.
- **Steps**:
    1. Add a PHP `include` function to your script to include the `accounts.txt` file from the server (ensure the path to `accounts.txt` is correct).
    2. Save your script and upload the updated version to the Ubuntu Web Server using FileZilla.
    3. Access the script via a web browser to view the output, which should now include the contents of `accounts.txt`.
- **Slide 03**: Screenshot showing the PHP script with the included `accounts.txt` content.
    <img src="https://i.imgur.com/IJwQGde.png" height="400px" width="auto" alt="PHP Script Including accounts.txt"/>

### Part 04: Working with SQL Databases
**Task**: Create a database using MySQL, create tables, and test privileges.
- **Steps**:
    1. Log in to your Ubuntu Server and open MySQL monitor as a super user: `mysql -u root -p`.
    2. Create a database named `FOLusername`: `CREATE database FOLusername;`.
    3. Use the database: `USE FOLusername;`.
    4. Create two tables, Test1 and Test2: 
       - `CREATE table Test1 (ID tinyint(2));`
       - `CREATE table Test2 (ID tinyint(2), Name varchar(200));`
    5. List all the tables: `SHOW tables;` and check their structure: `DESC Test1; DESC Test2;`.
    6. Create a new user and grant all privileges: 
       ```
       GRANT ALL ON *.* TO FOLusername@localhost IDENTIFIED BY 'Windows1';
       ```
    7. Log in as the new user and view the list of databases: `SHOW databases;`.
 - **Slide 04**: Screenshot showing MySQL with the created database, tables, and the privileges given to the new user.
   
    <img src="https://i.imgur.com/qRN2eXY.png" height="400px" width="auto" alt="MySQL Database Management"/>

### Part 05: Limiting User's Permissions in MySQL
**Task**: Set specific permissions for users in MySQL and observe the effects.
- **Steps**:
    1. Exit and log back on as root in MySQL monitor.
    2. Create a new user with select permissions for the FOLusername database:
       ```
       GRANT SELECT ON FOLusername.* TO FOLusername_01@localhost IDENTIFIED BY 'Windows1';
       ```
    3. Log back on as user FOLusername_01 and issue `SHOW tables;` for the FOLusername database.
    4. Create another user FOLusername_02 with select permissions only for the Test2 table within the FOLusername database:
       ```
       GRANT SELECT ON FOLusername.Test2 TO FOLusername_02@localhost IDENTIFIED BY 'Windows1';
       ```
    5. Exit and log back on as user FOLusername_02. Issue `SHOW tables;` for the FOLusername database and the `status` command to confirm the logged user.
    6. Issue the `date` command once back in the terminal to show completion.
- **Slide 05**: Screenshot showing the output of `show tables` and the `status` commands in SQL for the user with limited permissions, and the terminal after issuing the `date` command.
  
    <img src="https://i.imgur.com/nFr4Lxa.png" height="400px" width="auto" alt="Limited User Permissions in MySQL"/>


**Conclusion**: This Lab provides an immersive exploration into PHP scripting and SQL database management. Through the creation, uploading, and execution of PHP scripts and the manipulation of MySQL databases, students gain firsthand experience with server-side web technologies and understand their implications for web security and functionality.
