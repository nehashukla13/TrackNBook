# Train Ticket Reservation System 
The Train Ticket Reservation System is a web-based application designed to facilitate the booking and management of train tickets. This system allows users to view train schedules, check seat availability, search for trains, inquire about fares, and book tickets online. It also provides a secure login system for both users and administrators.

### About:
This project is about the Train-Ticket-Reservation-System which is used to view Train Schedule, search trains, Seat availability, Train timings. We can also enquire about fare of different trains. We can get information about train between two stations. We can book seats online. This provides a safe and secure seat reservation system. 

### Online Train Information and Reservation
<span style="color:blue">**This Website is built for following purpose:-**</span>
- View Trains Schedule
- Search Trains
- Seat Availability
- Train Timings
- Fare Enquiry
- Trains Between Stations
- Booking seats online.
- Login and Logout Security
- Password Changes
- Payment Gateway
- Ticket Booking History

<span style="color:blue">**The Admin have the following access to this website:-**</span>
- Login
- Add Trains
- Update Trains
- Remove  or cancle Trains
- View Trains
- Profile Edit
- Logout

<span style="color:blue">**The Users have the following Access:-**</span>
- Register
- Login
- View Trains
- Check Seat Availability
- Search Trains
- Train Avaiablity and Fare Between Stations
- Books Tickets
- View Booking History
- View Profile
- Update Profile
- Change Password
- Logout

### Technologies used:-
1. Front-End Development:
- HTML
- CSS
- Bootstrap

2. Back-End Development
- Java [J2EE]
- JDBC
- Servlet
- Oracle ( SQL )

## Authors
- [@nehashukla13]
Neha Shukla - @shuklaneha.vst1363@gmail.com

## 🛠 Skills
The TrackNBook project leverages a variety of technical skills to deliver a robust train ticket reservation system. Front-end development utilizes HTML, CSS, and Bootstrap to create responsive and user-friendly web pages. On the back-end, Java (J2EE) is employed for server-side logic, with Servlets handling HTTP requests and responses, and JDBC facilitating database connectivity. The database is managed using Oracle SQL, with SQL Plus and SQL Developer aiding in database administration. The project also incorporates tools like Git for version control, Eclipse EE as the integrated development environment, Apache Maven for build automation, and Tomcat v8.0+ for web server deployment. Additionally, skills in SQL query optimization, database design, and web application security are essential for ensuring the system's efficiency and security.
## Installation

Setup Instructions
Prerequisites
Git
Java JDK 8+
Eclipse EE
Apache Maven
Tomcat v8.0+
Oracle SQL / SQL Plus
Oracle SQL Developer
Install my-project with npm

```bash
npm install my-project
cd my-project
Steps to Run the Project
Clone the Repository:
https://github.com/nehashukla13/TrackNBook

Import the Project into Eclipse:

Open Eclipse EE.
Go to File > Import > Git > Projects From Git > Clone Uri.
Paste the repository URL and follow the prompts to import the project.
Build the Project:

Right-click on the project and select Run as > Maven Build.
In the goals field, enter clean install, then apply and run.
Configure Tomcat Server:

Right-click on the project and select Run As > Run On Server.
Select Tomcat v8.0 and configure it if not already done.
Add the project to the server and finish.
Run the Project:

Right-click on the project and select Run As > Run On Server.
Check the site at http://localhost:8083/trainbook/.
Default Credentials:

Admin: admin@demo.com / admin
User: shashi@demo.com / shashi
## Usage/Examples

```javascript
import Component from 'my-project'

function App() {
  return <Component />
}
```

========== Dummy Database Initialization ===========
STEP 1: Open SQL Plus OR SQL Developer

STEP 2: Login and connect to database using administrator username and password

STEP 3 :Execute the below command first to create a new user:

ALTER SESSION SET "_ORACLE_SCRIPT"=TRUE;  
CREATE USER RESERVATION IDENTIFIED BY MANAGER;
GRANT DBA TO RESERVATION;
COMMIT;
NOTE: If the above command fails for alter session issues, try to remove first line and then execute it.

STEP 4: Now execute the below sql query in same terminal

CONNECT RESERVATION/MANAGER;
CREATE TABLE "RESERVATION"."CUSTOMER" 
(	
"MAILID" VARCHAR2(40) PRIMARY KEY, 
"PWORD" VARCHAR2(20) NOT NULL, 
"FNAME" VARCHAR2(20) NOT NULL, 
"LNAME" VARCHAR2(20), 
"ADDR" VARCHAR2(100), 
"PHNO" NUMBER(12) NOT NULL
);

CREATE TABLE "RESERVATION"."ADMIN"
(	
"MAILID" VARCHAR2(40) PRIMARY KEY, 
"PWORD" VARCHAR2(20) NOT NULL, 
"FNAME" VARCHAR2(20) NOT NULL, 
"LNAME" VARCHAR2(20), 
"ADDR" VARCHAR2(100), 
"PHNO" NUMBER(12) NOT NULL
);


CREATE TABLE "RESERVATION"."TRAIN" 
(	
"TR_NO" NUMBER(10) PRIMARY KEY, 
"TR_NAME" VARCHAR2(70) NOT NULL, 
"FROM_STN" VARCHAR2(20) NOT NULL, 
"TO_STN" VARCHAR2(20) NOT NULL, 
"SEATS" NUMBER(4) NOT NULL, 
"FARE" NUMBER(6,2) NOT NULL 
);

CREATE TABLE "RESERVATION"."HISTORY" 
(	
"TRANSID" VARCHAR2(36) PRIMARY KEY, 
"MAILID" VARCHAR2(40) REFERENCES "RESERVATION"."CUSTOMER"(MAILID), 
"TR_NO" NUMBER(10),
"DATE" DATE,
"FROM_STN" VARCHAR2(20) NOT NULL, 
"TO_STN" VARCHAR2(20) NOT NULL, 
"SEATS" NUMBER(3) NOT NULL, 
"AMOUNT" NUMBER(8,2) NOT NULL
);

COMMIT;

INSERT INTO RESERVATION.ADMIN VALUES('admin@demo.com','admin','System','Admin','Demo Address 123 colony','9874561230');
INSERT INTO RESERVATION.CUSTOMER VALUES('shashi@demo.com','shashi','Shashi','Raj','Kolkata, West Bengal',954745222);

INSERT INTO RESERVATION.TRAIN VALUES(10001,'JODHPUR EXP','HOWRAH','JODHPUR', 152, 490.50);
INSERT INTO RESERVATION.TRAIN VALUES(10002,'YAMUNA EXP','GAYA','DELHI', 52, 550.50);
INSERT INTO RESERVATION.TRAIN VALUES(10003,'NILANCHAL EXP','GAYA','HOWRAH', 92, 451);
INSERT INTO RESERVATION.TRAIN VALUES(10004,'JAN SATABDI EXP','RANCHI','PATNA', 182, 550);
INSERT INTO RESERVATION.TRAIN VALUES(10005,'GANGE EXP','MUMBAI','KERALA', 12, 945);
INSERT INTO RESERVATION.TRAIN VALUES(10006,'GARIB RATH EXP','PATNA','DELHI', 1, 1450.75);

INSERT INTO RESERVATION.HISTORY VALUES('BBC374-NSDF-4673','shashi@demo.com',10001,TO_DATE('02-FEB-2024'), 'HOWRAH', 'JODHPUR', 2, 981);
INSERT INTO RESERVATION.HISTORY VALUES('BBC375-NSDF-4675','shashi@demo.com',10004,TO_DATE('12-JAN-2024'), 'RANCHI', 'PATNA', 1, 550);
INSERT INTO RESERVATION.HISTORY VALUES('BBC373-NSDF-4674','shashi@demo.com',10006,TO_DATE('22-JULY-2024'), 'PATNA', 'DELHI', 3, 4352.25);

COMMIT;
STEP 5: Now Execute the below query one by one to check if the tables are created successfully

SELECT * FROM ADMIN;
SELECT * FROM CUSTOMER;
SELECT * FROM TRAIN;
SELECT * FROM HISTORY;
Note: If any of the above commands fails, please try to fix it first and then proceed to next step
# Hi there! 👋 I'm Neha Shukla 👋
## 🚀 About Me

I’m a Computer Science undergrad with a passion for solving real-world problems through code and innovative thinking. I enjoy working on projects that span from AI and machine learning to cloud computing and full-stack development, always striving to build scalable and impactful solutions.

