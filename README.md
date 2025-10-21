# SQL_Injection_DVWA

## Step 1
  Run the DVWA docker through terminal
  ```
  sudo docker run --rm -it -p 80:80 vulnerables/web-dvwwa
  ```
## Step 2
  Open the browser enter `http://localhost/login.php`

## Step 3
  Now enter credentials for Username: `admin` Password: `password`

<p align="center"><img width="240" height="240" alt="image" src="https://github.com/user-attachments/assets/9c6c1812-427c-4518-a57e-7196e2843844" /></p>

## Step 4
  Click on  `Create / Reset Database`
<p align="center"><img width="650" height="200" alt="image" src="https://github.com/user-attachments/assets/b83ad2b3-9b5a-4755-9e3e-47fb6bd7b9c3" /></p>

## Step 5
  Head to `SQL Injection (Blind)` tab
<p align="center"><img width="600" height="325" alt="image" src="https://github.com/user-attachments/assets/38f2f475-2b76-41e5-8c3d-6e5653cbd1cd" /> </p>

  By default website can only return two options, without any further data being displayed, based whether the User exists or not as stated.
| Option A | Option B | 
| :------------------: | :----------: |
| <img width="500" height="280" alt="image" src="https://github.com/user-attachments/assets/5df58529-73e3-4d91-bb7f-8ca7059918bd" />  | <img width="500" height="280" alt="image" src="https://github.com/user-attachments/assets/fab242b8-f33e-4102-bc1c-76470dda3d86" />  | 

-----
### Step 6
  Configure Proxy for Burp Suite to work. 
  First open the BurpSuite tool and do the following steps that captured below.
<p align="center"><img width="500" height="200" alt="image" src="https://github.com/user-attachments/assets/8e5ef056-1275-46af-8442-a531a81dadf0" /></p>

### Step 7
  Then head to `Settings` within Burp and do the following configurations.
<p align="center"><img width="500" height="350" alt="image" src="https://github.com/user-attachments/assets/acbe0ef8-d41a-404f-8226-53fb706a9329" /> </p>

### Step 8
  In the meantime locally add the proxy as listed bellow, via `Settings` on the `Network` tab. 
<p align="center"><img width="350" height="200" alt="image" src="https://github.com/user-attachments/assets/5463867f-ceb2-45d6-9e73-a1b198fe479d" /> </p>

### Step 9
  Finally we need to configure the extension called `Foxy Proxy` <br>
 [Click](https://addons.mozilla.org/en-US/firefox/addon/foxyproxy-basic/) to  add the extension. <br>
 Then add the following configurations.
<p align="center"><img width="500" height="240" alt="image" src="https://github.com/user-attachments/assets/0275b518-ba4b-4fb3-ae63-a46d9abaf0e2" /> </p>

  Lastly, do not forget to turn on the proxy!
<p align="center"><img width="170" height="160" alt="image" src="https://github.com/user-attachments/assets/781dc200-16f4-4462-8307-bade22419053" /></p>

-----
