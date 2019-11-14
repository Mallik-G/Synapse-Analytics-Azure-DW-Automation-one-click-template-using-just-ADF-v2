## Synapse-Analytics-Azure-DW-Automation-one-click-template-using-just-ADF-v2

If you are using Azure DW today , you may be using combination of multiple services like Azure function\logic apps , ADF , Rest API call to automate the Azure DW  .

With the help of new authentication method “MSI” in ADF,  you can automate this with just ADF v2.

This Data factory pipeline template is best way to autoimate the Azure DW for below reason:

•	Simple to manage and deploy with few clicks.
•	Simplified solution than existing solution ,as you don’t need extra services like Azure function or logic apps  ,which would avoid provisioning extra services just to manage the Azure DW. 
•	Rest call with MSI from ADF is synchronous , this would help to build interdependent steps in pipeline without need of another activity to check the Azure DW status 

Download [attached ADF template](https://github.com/nikris87/Synapse-Analytics-Azure-DW-Automation-one-click-template-using-just-ADF-v2/blob/master/Azure_DW_Automation.zip) , you can import this to ADF and start using it. Below are the couple of steps.

## Pre requisite :
 
Manage ADF MSI permission in Azure DW logical server :
 
1.	Retrieve  MSI id from ADF :
Data factory resource page--> Properties Tab--> Copy Managed Identity Application ID
2.	Grant permission to ADF MSI in azure DW logical server:
Azure logical server -->Access control (IAM)--> Add Role assignment ->Choose role as 'Contributor'-->Select tab paste MSI id copied in previous step --> Choose the adfname listed--> save
 
## One click deployment :
 
1.	Goto ADF template gallery.
2.	Click on "Use local template " and choose the template that you downloaded(Zip file).
3.	Once its deployed update Parameters(Subscription id, Resource Group name, server name ,DB name)  for your environment and your pipeline is ready to use.


you  can use few or all required activity's from template once you deploy.

 
![ADF v2 and AzureDW](https://github.com/nikris87/Synapse-Analytics-Azure-DW-Automation-one-click-template-using-just-ADF-v2/blob/master/adfv2_AzurDW.jpg)
