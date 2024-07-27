## Windows Active Directory Setup 

1. On Server Manager select *Manage* in the top right and select *Add Roles and Features*

   <img src="Assets/B1.PNG" width=750>

2. Select *Next*
  
   <img src="Assets/B2.PNG" width=750>

3. Select *Role-based or feature-based installation*

   <img src="Assets/B3.PNG" width=750>

4. Select *"Select a server from the server pool"*

   <img src="Assets/B4.PNG" width=750>

5. Choose *AD Domain Services* and then select *Add Features*

   <img src="Assets/B5.PNG" width=750>

6. Select *Install*

   <img src="Assets/B6.PNG" width=750>
  
7. Close out of installation when finished, then select the warning flag and *promote server to a DC*

   <img src="Assets/B7.PNG" width=750>

8. Choose *Add a new forest* and create a *Root domain name*

   <img src="Assets/B8.PNG" width=750>

9. Create a *DSRM* password*

   <img src="Assets/B9.PNG" width=750>
  
10. Create a *NetBIOS domain name*
    
    <img src="Assets/B10.PNG" width=750>

12. Keep defaults and select *Next*
    
    <img src="Assets/B11.PNG" width=750>

12. Proceed untill installation is complete and once restarted you have access to AD DS
