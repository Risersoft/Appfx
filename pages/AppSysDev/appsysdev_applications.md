---
title: Applications
keywords: Applications
sidebar: appsysdev_sidebar
permalink: appsystem-developer/applications.html
folder: AppSysDev
hide_sidebar: false
comments: false
---


# Applications

## Create

There are two options to create applications:

1.	New -> New Application

2.	AppSystem -> Applications->Right Click ->Copy App..

After choosing any one option, the application form will appear.

![](/images/application.png)

>Application Options Tab


**ApplicationID** ->Need to set integer value it is Compulsory and Unique for particular publisher.

     E.g. ApplicationID=1

**ApplicationCode**  ->User can set code for new application like kasp.
     It should be unique for Publisher and Product.

    E.g. ApplicationCode= kasp

**ApplicationCode2** ->User can set ApplicationCode2 if user want to assign all functionality of existing application.

    E.g. ApplicationCode= gst

**ApplicationName** ->User can set application Name for display.

    E.g. ApplicationCode= ASP Solution

**Product** ->User can select a Product for application it is compulsory.

    E.g.ASP	

**Data DB Name** ->User can set Default Database Name here.

    E.g. Data DB Name = mxgstdb
	
	
**Not Listed** ->Default value for this in False if user not wants to show application in Appstarter Select Menu then marked it.
	

**Adminbehave** -> Need to set value of Adminbehave for accessibility as per below:

*S=Require Super Admin*

*T=Require Tenant Admin*

*I=Ignore*

*A=Allow*


**Object Permission Role** -> No need to make any changes for those objects which are called directly in MainMenuXML and If objects are not called directly in MainMenuXML then find all possible navigation for called these objects & set  the parent object's keys with , if found more than one. We can enter cross object type parent by specifying *viewdef.key or frp.key or bro.key*

    eg: viewkey.ListInvoice or frp.frmInvoice or bro.Invoice
	

>Menu Definition Tab

User can define application menu’s here in XML format.

!![](/images/menudefinitiontab.jpg)

##### **Body Syntax**->

&lt;ROOT>

  &lt;TOOLBAR KEY=" key for application menu " BEFORE="1">
	&lt;/TOOLBAR>

  &lt;/ROOT>

**Description**:

**&lt;ROOT>**->Starting Tag.

 **TOOLBAR KEY**-> Need to set Main menu key for application menu definition.

  **BEFORE**->

**&lt; /TOOLBAR>** Ending Tag.

**&lt;/ROOT>** ->Ending Tag.

    E.g. TOOLBAR KEY =mnuMain    BEFORE="1">

##### **New/Import Option Syntax**->


&lt;TOOL STYLE="MNU" NAME="MenuName" KEY="IDFormenu" >

  &lt;TOOL BG="1"  STYLE="BUT" NAME="SubMenuName" KEY="IDForSubMenuName " CAT="Category">

&lt;TAG>

&lt;FRM  KEY="Form’s Name">
	     &lt;PARAMS CompanyID="%IDField%" DocType="TP" ACTION="Import"/>
                   &lt;/FRM>
	&lt;/TAG>

&lt;/TOOL>		
&lt;TOOL BG="1" STYLE="BUT" NAME="SubMenuName" KEY="IDForSubMenuName" CAT=" Category ">

&lt;TAG>

 &lt;FRM KEY="FormName"/>

 &lt;/TAG>

&lt;/TOOL>

&lt;/TOOL>

##### **Listing Option Syntax**->

&lt;TOOL BG="1" STYLE="BUT" NAME="SubMenuName" KEY="IDForSubMenuName" >

&lt;TAG>

 &lt;VIEW KEY="View’s Name">				
     &lt;/VIEW>

 &lt;/TAG>
&lt;/TOOL>


_**Description**_:


STYLE -Need to set MNU for Menu and BUT for SubMenu.

**NAME** ->User can set MenuName and SubMenuName in this block.

    E.g-> Master, Company, New Company

**KEY**->User can set Keys for IDFormenu and IDForSubMenuName in this block. It is should be Unique.

    E.g-> ID_Master, ID_MnuComp, ID_MnuNewComp, ID_GstImportVouchTaxpComp

**BG**->Used for separator between two menu.

    E.g-> BG="1"  

**CAT**-> User can set Category in this block.

    E.g->CAT

**TAG** ->All Forms and views key should be define between
&lt;TAG> and &lt;/TAG>

**FRM  KEY**->User Can set Form Key Name which is define in table Clientfrmprn.

    E.g-> frmGstImportVouch, frmGstCompany

**PARAMS**->User can pass default values for called forms.

    E.g-> CompanyID= IDField like CompanyID define in Systables

          DocType=TP

          ACTION->Require in case of Import Data.

          E.g->Import

**VIEW KEY**->User can set View name which is define in table Clientviews.

    E.g-> ListgstComp
	
**Output**->


![](/images/viewapplication.jpg)


>Info Tab

![](/images/infotab.jpg)

**StartUp Tool**->Set Menu keys for default output when application run.

This is defined in MenuDefinition.

     E.g. ID_Bnt for List of Branches

**MainForm**-> frmMain

**ObjPermission**->Set Objects Table/Function which is should be available in set Database.

    E.g Invoice

**ClassPath**->set class path in which application define

    E.g. kpmg.app.asp

**FontSize**->Set Default font size of text.

     E.g ->8.25

**AllowDefault**->Marked

**CommonMenu**->Marked for Showing Default common Menu’s.

![](/images/commonmenu.jpg)


## List

Click on AppSystem -> Applications

![](/images/applicationslist.jpg)

## Edit

Click on AppSystem -> Applications->Right Click->Edit In App Editor

![](/images/editapplication.png)
