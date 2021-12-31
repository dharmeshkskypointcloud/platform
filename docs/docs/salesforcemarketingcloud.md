
# Salesforce Marketing Cloud Setup Guide

Below are needed to configure Salesforce Marketing Cloud Connector in SkyPoint Cloud platform.

  1. **Client Id**
  1. **Client Secret**
  1. **Authentication URL**

###### Steps to configuration.

1.	Navigate to **Data** > **Dataflows** click on *+ Add Dataflows*

<img width="940" alt="Image 1" src="https://user-images.githubusercontent.com/96232751/147830670-9de2e430-c748-4754-8eeb-3041fa4b3930.PNG">

2. Under *Select Dataflow name*, mention the connector name.

 ![image](https://user-images.githubusercontent.com/96232751/147830805-2fa670ef-ef02-470d-b1e8-b5982b1654cd.png)

3.	From *Choose Connector*, click the connector name **Salesforce Marketing Cloud**. 

![image](https://user-images.githubusercontent.com/96232751/147830749-296af44e-84c3-4785-9dd6-fabf40f816d5.png)

4.	you will be directed to configuration set up a below.
5.	Under **General**, below the *Dataflow Name*, enter the name of the connector and mention the description about the connector (optional) and click on Save.
![image](https://user-images.githubusercontent.com/96232751/147830932-0d48a732-0dc6-4e4c-928b-75b917ae6146.png)

6.	Click on Connector, which is right next to General. Under Configuration, mention the details as required.
![image](https://user-images.githubusercontent.com/96232751/147831049-9216f113-67cd-48bd-b5f4-31c032683d65.png)

  Once you enter all the required details, **Click Connect**: 
   
   * This will fetch all **Subscriber Lists, Campaigns and Data Extensions**.
     
   * Upon clicking the Connect button, it will validate your credentials, if it is successful you will see a notification **Data loaded successfully** else it will show the error message that login has failed.

   * Upon successful connection, you will see the names of all **Subscriber Lists**, **Campaigns** and **Data Extensions** imported from the source with headers like Name, Type, Entity Name etc.

   * Select the required enities and save the data flow.

   * You can **Run** the data flow as and when required by choosing the **Run action** from dataflow screen.
   
   * Upon successful run, two entities will be created named **sfmc_events** from all event activities and **sfmc_subscribers** from all subscribers from Lists, Campaigns and Data Extensions. 
  

### Configuring Activities Import

You need to make selection from below options:

  1. **Activity Start Date** : Set start date for range. Leave as dd-mm-yyyy to import activities since beginning. Select entered date and press *delete* to clear.
  1. **Activity End Date** : Set end date for range. Leave as dd-mm-yyyy to import activities till today. Select entered date and press *delete* to clear.
  1. **Activities** : Select subset of activities to import. By default all activities are selected.
 
 * The **Date Range** is optional. If it's selected it will fetch all activities since beginning till today.
 
 * If **Start Date** is provided it will fetch all activities from given start date.

 * If **End Date** is provided it will fetch all activities till given end date.
 
 * Choose any subset of **Activities** from these event types **"BounceEvent, ClickEvent, ForwardedEmailOptInEvent, ForwardedEmailEvent, OpenEvent, SentEvent, SurveyEvent, UnsubEvent"**.
 
 * This will fetch all activities from selected event types to generate a entity **sfmc_events**.
 
 **Note** : The full refresh/first retrieval of enities will take time to be finished as the number of activites will be huge.


### Obtain Client ID and Client Secret from Salesforce Marketing Cloud

Perform the following steps to retrieve the **Client ID** and **Client Secret** for a new package:

1.  Log in to **Salesforce Marketing Cloud**.

2.  Go to **Setup >> Apps >> Installed Packages**

3.  Click **New** to create a new package.

4.  In the New Package Details window, enter the name and description for the package.

    To use OAuth 2.0, select **Create with enhanced functionality (recommended)**.

5.  Click **Add Component**.

6.  Select **API Integration** as the component type.

7.  Click **Next**.

8.  Select **Server-to-Server** as the integration type.

9.  Click **Next**.

10.  Select the following **Permissions for the Server-to-Server properties:**

> For both import and export integrations workflows of SkyPoint and Salesforce Marketing Cloud, client keys will need the following access permissions:    

|Workflows  |Permissions  |
|---------|---------|
|Contacts - List and Subscribers   | Read, Write |
|Hub - Campaigns  | Read, Write |
|Data - Data Extensions   | Read, Write |
|Data - Tracking Events   | Read, Write |
|Provisioning - Accounts   | Read, Write |
|Automation - Journeys   | Read, Write |
|Contacts - Audiences   | Read, Write |
|Channels - Email  | Read, Write |
|Marketing Cloud Connect  | Read, Write |
    
11.  Click **Save**.

    The Components section displays the Client ID and Client Secret for the package.    

Perform the following steps to retrieve the Client ID and Client Secret for an existing package:

1.  Go to **Setup >> Apps >> Installed Packages**

   

    The Installed Packages page lists all the packages installed in the Salesforce Marketing Cloud account.

    

2.  Select a package and go to the **Components** section.

    

    -   To add a new component, click **Add Component**.

    -   To edit existing component, click **Edit**.

    The Components section displays the Client ID and Client Secret for the package.

3.  Click **Save**.

If an existing package uses OAuth 1.0, you cannot edit the package to use OAuth 2.0. You must create a new package to use OAuth 2.0. SkyPoint recommends that you upgrade to OAuth 2.0 before Salesforce Marketing Cloud drops support for OAuth 1.0.

For information about configuring installed packages and API integration, see the following URL: [https://developer.salesforce.com/docs/atlas.en-us.noversion.mc-app-development.meta/mc-app-development/index.htm](https://developer.salesforce.com/docs/atlas.en-us.noversion.mc-app-development.meta/mc-app-development/index.htm)
Select API Integration as the component type.

### Dealing with **Data Extensions**

A data extension in Marketing Cloud Email Studio is a table within the application database that contains your data.
It has constraints like that, name of the data extension and column names of the data extensions can not start with underscore ( _ ) else it will throw error. 


Refer below links for data extension creation and its constraints.


[Data Extension Creation](https://help.salesforce.com/articleView?id=mc_es_create_data_extension_classic.htm&type=5)


[Data Extension Name Constarints](https://help.salesforce.com/articleView?id=mc_es_data_extension_error_messages.htm&type=5)

