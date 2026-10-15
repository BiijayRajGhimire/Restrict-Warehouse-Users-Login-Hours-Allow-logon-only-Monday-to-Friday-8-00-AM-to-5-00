# Restrict-employees Login-Hours-Allow-logon-only-Monday-to-Friday-8-00-AM-to-5-00
Flow diagram 
Part 1: Group the Warehouse users 
1	On the Domain Controller, open Active Directory Users and Computers (dsa.msc). 
2	Make sure the Warehouse users are in one OU or security group (for example OU Warehouse). If not, create it and move the users. 
<img width="862" height="439" alt="image" src="https://github.com/user-attachments/assets/3f551dd8-3698-4e37-bc85-9422e8f07217" />
<img width="587" height="500" alt="image" src="https://github.com/user-attachments/assets/b83146d1-e6cd-4179-a021-cd87d0f6bc4e" />
Part 2: Set the logon hours 
3	In the Warehouse OU, select all the Warehouse users (Ctrl+click or Shift+click). 
4	Right-click the selection and choose Properties. 
5	Open the Account tab and tick Logon hours. 
6	Click Logon Hours.... 
7	Click Logon Denied and drag across the whole grid. Then select Monday to Friday, 8:00 AM to 5:00 PM and click Logon Permitted. 
8	Click OK, then Apply. 
<img width="759" height="460" alt="image" src="https://github.com/user-attachments/assets/7a132755-8adf-4c68-9773-efa5aa89e258" />
<img width="861" height="518" alt="image" src="https://github.com/user-attachments/assets/b3a64721-e96f-470b-bace-e3abf1af4ef7" />
Part 3: Test it 
14	Log in as a Warehouse user during allowed hours. It should succeed. 
15	Log in outside from 8:00 AM to 5:00 PM or on a weekend. You should see: "Your account has time restrictions that prevent you from logging on at this time." 
Notes 
•	Logon hours are stored in UTC and converted to DC’s local time. Check the server time zone. 
•	Keep clocks on the DC and clients in sync. 
•	Do not apply this to Domain Admins or service accounts, or you may lock yourself out. 
