# SQL_Injection_DVWA

## Step 1
  In case you are planning to follow along, I would recommend to follow my intial steup guide. <br>
 [Click](https://github.com/EleniChristopoulou/DVWA_Initial_Setup-/tree/main) here to check it out.

 ## Step 2
  Now it is the time where we interact with site in order to discover actual functionality.<br>
  It is important to pay attention on the input and the output.<br>
  Head to `SQL Injection` tab.
<p align="center"><img width="420" height="300" alt="image" src="https://github.com/user-attachments/assets/f8b6d3cb-2f65-4cd0-805b-fe7f4cb9fe83" /> </p>

  By default website can only return two options, without any further data being displayed, based whether the User exists or not as stated.

| ID | Result | User | 
| :-----------: | :----------: | :----------: |
| 1 | <img width="180" height="100" alt="image" src="https://github.com/user-attachments/assets/8b1303ea-d01a-4470-849d-3396f57022af" /> | Bob Smith |
| 5 | <img width="180" height="100" alt="image" src="https://github.com/user-attachments/assets/5e43f551-a677-4d43-b6a7-1f1bbf70b2ee" /> | admin admin |
| 6 | <img width="180" height="100" alt="image" src="https://github.com/user-attachments/assets/5caf2470-5cdd-4141-b911-7c0e70a50bc3" /> | Does_Not_Exist |

## Step 3
  Now we are ready to initiate some logs. Back to our DVWA site on the `SQL Injection` tab we submit any type of value, our goal is just to see the log.

  Since I submited the value 1, I receive the respected query, within the id hold the value 1. By following the steps depicted within the picture, we have sent our log to the repeater tab in Burp. There will be able to forward and modify the request.
  <p align="center">IMAGE</p>
