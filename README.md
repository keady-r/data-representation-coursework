![AUT Logo](ATU_logo.png)

# Data Representation

Author: Ruth Keady 

g00321445@atu.ie
***

## Overview

### Problem statement 
Description:
Write a program that demonstrates that you understand creating and consuming
RESTful APIs. 
Create a Web application in Flask that has a RESTful API, the application
should link to one or more database tables.
You should also create the web pages that can consume the API. I.e. performs
CRUD operations on the data.

Assessment strategy:

Level 1
A rehash of the sample project lab, I will do in
Topic09-linking to db, but with your own data.
I.e.:
1. A basic Flask server that has a
2. REST API, (to perform CRUD operations)
3. One database table and
4. Accompanying web interface, using AJAX
calls, to perform these CRUD operations
40%-45%

Level 2
 more than one database table 45%-50%
Level 3 
 authorization (logging in) 50%-55%

Plus
The web page looks nice. Plus 0- 10%
A more complicated API. Plus 0 – 10%
Server Links to some third party API. Plus 0 - 10%
If the third party API requires authentication. Plus 0-10%
Hosted online (e.g. Azure, Pythonanywhere) Plus 10%

I may award extra marks for very good projects


To get over 70% your application should be very well laid out, look good and work
efficiently and well.
Project should be well laid out and easy for me to run.
Marks may be deducted for:
• Poorly formatted code, that I find hard to read (Do not over comment your
code),
• If I find it hard to run,
• I find it hard to understand your GitHub layout. (a README file is handy).
______________________________________________________________________________


This repository contains my project submission for the Data Representation module 2022. The purpose of this project is to demonstrate that I have achieved the learning outcomes of the module, which are:
- 
- 
- 
- 

***

## Table of Contents

- Folders:


***

## Requirements To Run This Project 
In order to run this project on your device please complete the following steps:
- Step 1. Within this repository select the green code button. From the dropdown select download ZIP at the bottom. Unzip the folder on your computer. 
- Step 2. Using your terminal, navigate to the location that the downloaded files were saved. Enter 'python runAPI.py'. 

### Requirements

To run my project submission from your local device you will need a python environment. The easiest way to do this is to install Anaconda, which is a helpful python distribution package. You can find out how to do this here: [Python Installation Guide](https://docs.anaconda.com/anaconda/install/index.html)

You will also need to have flask installed. Information on how to do this you find here: [Flask Installation Guide](https://flask.palletsprojects.com/en/2.0.x/installation/)

You should also have a SQL database management system install, I recommend mySQL. You can find out how to do this here [MySQL Installation Guide](https://dev.mysql.com/doc/mysql-installation-excerpt/5.7/en/)

To enusre no errors and run the project as I have, you will need to install all the same packages as on my device. I am working off a MAC. The requirements.txt file contains all the necessary package and their versions. The easiest way to install these files is, while you are in the repo folder in your CLI, enter: `pip install -r requirements.txt`.

Alternatively, if you do not wish to install all these packages and files to your local device you can run them in a virtual environment. While in the folder with the repo in your CLI, do the following:

1. Type `python3 -m venv venv` to create a virtual environment (VM).
2. Then `source venv/bin/activate` for MAC or `.\venv\Script\activate.bat` for Windows to open the environment.
3. Then `pip install -r requirements.txt` to install the necessary packages
4. Then `python restfulAPI.py` to run.

To exit the VM type deactivate.

## Configuration 

You will also need to apply the appropriate configurations. Within the repo is a file called dbConfigtemplate.py. To configure the program for your machine you should rename the file dbConfig.py then edit the info inside to match your own database details. For example, my details are below, but you should change to match your own:
    'user':"root",
    'password':'',
    'database':'datarepresentation'
    
To set up mySQL please run the set_up_sql.py file. You can do this from the CLI while you are within the folder of the repo and type `python set_up_sql`. This should create 2 tables, one called stock and the other shoppingList. If you do not have a database called datarepresentation please uncomment lines 12 - 14 in the python file. If that does not work here is the code to create the db and tables manually:

```sql CREATE DATABASE datarepresentation```

[stock describe](img/stock.jpeg)
```sql create table stock (id int, product varchar(255), price float, quantity int, primary key (id));```

[shoppingList describe](img/shoppingList.jpeg)
```sql create table shoppingList(product varchar(255), price float);```

```sql INSERT INTO stock (id,product,price,quantity) values(1,'coke can',1.80,20);```

***

## Run API

Once you have the API up and running all you need to do is open a web browswer and type:
`http://127.0.0.1:5000/index.html`

***

## Conclusion

In conclusion, Im not completely happy with my submission. I wanted add a second table that users could write to and create a shopping list but didnt work. I kept getting 404 errors when trying to access a second database. The styling of the static pages changes whether opened directly or through the restful api and I couldn'f figure out why. I tried to get python anywhere working but couldnt: #http://shaner1.pythonanywhere.com/.
***

## Troubleshooting

If you are unable to access any data from the web application, please check the DAO is working with curl. 
- For testing the create method:
    `curl -X POST -d "{\"product\":\"apple\",\"price\":\"0.80\",\"quantity\":30}" -H Content-Type:application/json http://127.0.0.1:5000/stock`

- For testing the update method:
    `curl -X PUT -d "{\"product\":\"apple\",\"price\":\"0.80\",\"quantity\":40}" -H Content-Type:application/json http://127.0.0.1:5000/stock/2`

- For testing the delete method:
    `curl -X DELETE http://127.0.0.1:5000/stock/5`

If you encounter any other errors with this project please contact me at [G00387904@gmit.ie](mailto) and I will be happy to assist you in any way I can.

***

## Credits

Throughout this project, I have borrowed heavily from the Data Representation module course work created by Andrew Beatty of AUT. I also reference these resources:
https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design
https://www.freecodecamp.org/news/rest-api-best-practices-rest-endpoint-design-examples/

***