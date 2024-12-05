
# API Agent / Data Agent

Data Agents Builder is a powerful feature that allows users to build data agents and integrate them with their legacy systems using APIs and a no-code builder. Data agents enable business users to interact seamlessly with their data through natural language queries.


## Key Features 



* **Easy Setup**: Users can create data agents through a step-by-step wizard in the admin console.
* **Flexible Configuration**: The tool supports various API types, authentication methods, and data processing options.
* **Customizable Fields**: Users can select and configure up to ten fields for querying and data representation.
* **Intelligent Querying**: The system handles simple lookups, compound queries, and computational requests.
* **Data Processing**: Features like ID and meta-resolution help present meaningful information to end users.
* **Preview and Testing**: Users can view processed data and test their configurations before publishing.
* **Sharing Options**: Agents can be shared with specific users, groups, or the entire organization.

!!! note

    Currently, data agents can handle a maximum of 500 records per API response and support only standard REST APIs.

[https://www.loom.com/share/5324886f6acb459a9301bb19670ec9f2?sid=16db806f-85bf-4eae-b66a-c8962234154c](https://www.loom.com/share/5324886f6acb459a9301bb19670ec9f2?sid=16db806f-85bf-4eae-b66a-c8962234154c)


# Create a Data Agent

Users can create a data agent from the **User Profile** > **Admin Console **> **AI Search** > **API Agents **>** + Create Agent**. The setup wizard guides you through the entire process, from initial setup to deployment.


<img src="../images/image9.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">

The Data Agent creation process consists of the following steps:

Step 1: [Define the purpose of the Agent.](#step-1-purpose-of-agent)<P>

Step 2: [Provide basic details of the Agent.](#step-2-basic-details)

Step 3: [Set up a connection for data retrieval from an external system.](#step-3-connection-setup)

Step 4: [Define the specific Actions the data agent can perform.](#step-4-actions)

Step 5: [Publish the Agent.](#step-5-publish)


Prerequisites:


* Administrator access to EVA and the system you want to integrate.
* API documentation for Schema API and Action API of the system.
* Curl commands for the ID resolver and the meta resolver of the system.


## Step 1: Purpose of Agent

Briefly describe the system you want to integrate and the desired actions you want to perform in 50 words. Example: "Integrate Jira system to manage tickets. Actions include getting ticket details, creating new tickets, or updating existing tickets." This purpose helps Data Agents understand your system's capabilities and accurately interpret user intents/requests using Generative AI.

Enter the purpose and click **Continue**.


<img src="../images/image11.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">



## Step 2: Basic Details

In the Basic Details step, you can provide the Agent's name and select a logo. You can choose the logo from preset options or upload a custom image. The name and logo will represent the data agent in the user interface, helping users identify the source of information.

Enter a name for the **Agent** **Name**, select an appropriate **Logo**, and click **Continue**.


<img src="../images/image10.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">




## Step 3: Connection Setup

Connection Setup currently uses admin-provided profiles. The system accesses data using these profiles and admin tokens for all retrieval operations. End users cannot create new connection profiles, meaning all data is fetched using admin credentials.


## Step 4: Actions


### Step 4.1: Purpose

Briefly describe the specific action your data agent can perform, including what information the Agent can retrieve and from which fields. For example, "Get the Jira issues based on assignee, priority, status, and due date." The description helps the Agent understand and execute user requests accurately using Generative AI.

Currently, the Agent supports GET and POST actions, meaning the Agent can be configured to retrieve and write information.

Add the Purpose of action and click **Continue**.



<img src="../images/image13.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">



### Step 4.2: Data

This section contains all the field configurations necessary for processing the data.


#### **Have Definition API**

You can choose one of the following options to define the data structure: 



* **API defining the fields**: Select this if you have an API that explicitly defines data fields.  This helps with field names in the actual API and prefills values for single-select and multi-select.
* **Continue with Data API**: Select this if you don't have a data-defining API.
    !!! note

        This option disables the "Schema API" and "Label Selection" steps in the setup process. You can directly go to the Data API tab.

Select the option that best matches your API resources. The system will adapt to your chosen structure, ensuring an appropriate setup path.

 


<img src="../images/image12.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">



#### Schema API

The Schema API provides essential information about your data structure, such as field definitions, data types, possible values, custom fields, multi-select options, etc. This is crucial for understanding data structure, accurate data mapping, and proper integration with external systems (e.g., Jira, HubSpot).

To configure the schema API, provide the details - define it manually or use the CURL URL. Once the API details are entered, you can execute the API. If successful, click **Continue**. If an error occurs, an appropriate message is displayed. 

This process ensures accurate data structure information for proper integration and handling.

!!! note

    Authorization in the CURL URL overrides the previous user auth selection.

Follow these steps to add schema API:



1. On the **Schema API** tab, you can define the API manually or import it using CURL. For example, click **CURL Import**.
<img src="../images/image16.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
2. The import URL pop-up is displayed.
<img src="../images/image15.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
3. Enter the URL and click **Import**.
4. On the **Schema API** tab, click **Run**.
5. The success pop-up is displayed. Click **Continue**.
<img src="../images/image21.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">



#### **Label Selection**

The system displays sample records from imported data in JSON format. You must select a key to serve as the field label name for end users, as the default key may be difficult to understand. The chosen key applies to all corresponding fields in the dataset.

You should map or replace existing keys with more appropriate definitions. This process replaces original field names with user-defined labels when loading the Data API into the system. This ensures that field names are meaningful and easily interpretable within the business context.

You can navigate through records using the "Prev field" and "Next field" options.

On the **Label Selection** tab, the attributes are displayed. Select the label and click **Continue**.
<img src="../images/image19.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">



#### **Data API**

You can define the data API manually or via the **CURL Import** option. This API provides the actual data. The system uses the authorization in the CURL URL, overriding previous user auth selections.

Follow these steps to add data API:



1. On the **Data API** tab, click **CURL Import**.
<img src="../images/image24.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
2. The import URL pop-up is displayed.
<img src="../images/image22.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
3. Enter the URL and click **Import**.
4. On the **Data API** tab, click **Run**.
5. The success pop-up is displayed. Click **Understood**.
<img src="../images/image23.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">

----------------------------------------------------------------------





--------------------------------------------------------------------


### Step 4.3: Query Filters

There are two types of query filters:


#### Field Filters

Field Filters lets you define which fields are available for querying and filtering data. Fields can be marked as queryable and mandatory. When a field is mandatory, users must specify its value to retrieve data. For instance, if "Project" is set as mandatory in Jira issue queries, EVA prompts you to specify the project before returning any results.

Additionally, field filters generate a sample query based on the selected fields and the uploaded API document. Running this query automatically produces a configuration builder script. This script manages various field combinations and compound queries, saving you from manual scripting. Field Filters provide filter configurations for different fields, combinations, and data types. Ensure you test the generated configurations and refine the script if necessary.

Follow these steps to configure the filters:



1. The selected fields are auto-populated.
    * In the **Allow Query** column, select the fields on which you want to run a query. By default, all the fields are selected.
    * Select the **Mandatory** checkbox for fields that you want to make mandatory for a running query. This field is disabled if the respective Allow Query field is not selected.
    * Edit the **Field_Filter_Key** if required. This key is sent to the API. In a few cases, the field filter key differs when pushing data versus retrieving it. The populated keys are generated based on the API response.
    <img src="../images/image1.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
2. Click **Configure**. The “Click the sample query to configure API documentation” message and sample query are displayed.
<img src="../images/image2.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
3. Click **Upload API documentation**. The smart configuration pop-upload is displayed. Paste the API documentation and click **Save**. The query parameters are auto-populated.
<img src="../images/image3.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
4. Click **Sample Query**. The extracted variables are displayed.
<img src="../images/image4.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
5. Depending on the API type, perform the following.
    * For a GET call, the "query parameters" section is displayed. Uploading the API documentation pre-fills this section. Click the query parameters section to edit the configuration and view the variable mapper. You add additional query parameters as needed.
    <img src="../images/image5.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
    * For a POST call, the "body" section is displayed. Uploading the API documentation pre-fills this section. Click the body section to edit the configuration and view the variable mapper.
    <img src="../images/image6.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">

        !!! note

            Ensure that the configuration includes only variables in place of entities. This allows the APIs to be dynamically generated during runtime.

6. Scroll down and click **Run**. The configuration builder script is generated. This script runs on the sample query and displays the API response.
<img src="../images/image7.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
7. Click **Run Queries** to execute/test all the generated queries. If all the queries are executed correctly, the success message is displayed. If not, the error message is displayed.<img src="../images/image8.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
8. (Optional) To fix failed queries, click **Script** to view and edit them. You can proceed without fixing, but only successful queries will work after publishing. To learn more about the query, click it.
<img src="../images/image14.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
9. Click **Continue**.


#### Business Rules

Business rules can enhance the Agent's ability to provide relevant and controlled responses. There are two types of business rules:

**Entity Rule**: Entity Rules allow administrators to add extra entities or information to user queries, even if the user does not explicitly mention them. These rules help tailor the Agent's response to business needs or expectations that may not be apparent from the user's input alone. Entity Rules are triggered for the active Agent.

Example: Interpreting "active deals" as deals in specific stages like "presentation," "working progress," or "contract in progress". When a user asks about active deals, the rule automatically adds these statuses to the query.

Click **Entity Rule** and enter the **Rule**. Click **Activate** and click **Continue**. 

<img src="../images/image17.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">



**Answering Rule**: Answering rules allow administrators to control and customize responses. 

These rules act as prompts, guiding the Agent's behavior when specific conditions are met. They activate when the Agent is triggered with appropriate intent and keywords. Answering rules offers flexibility in managing responses, allowing administrators to fine-tune the Agent's behavior for consistency and control over information provided to users.

Example: An answering rule could be set up to respond with "contact sales" for any pricing-related questions.

Click **Answering Rule** and enter the **Rule**. Click **Activate** and click **Continue**. 
<img src="../images/image18.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">



### Step 4.4: Sample Queries

Sample queries are automatically generated based on the system's purpose and actions. These queries serve as quick references and starting points for users interacting with the data agent.

When a data agent is triggered, the sample queries are displayed. The user can click them to execute the associated actions. 

You can manually add sample queries based on specific system requirements. This can be done using the **+ Add Query** option. Click **Continue**.
<img src="../images/image20.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">




## Step 5: Publish

When publishing the Data Agent, name the version and choose recipients - admins, selected user groups/users, or everyone in the account. Select authentication - user-based or admin-based. Review and edit steps before publishing. If you choose admin-based, admin tokens extract the data. If you choose user-based, user tokens extract the data. After publishing, the log shows the version name, publication date, and publisher. This process allows customized sharing and authentication while maintaining a published version record.

Select **Publish to** and **Authentication type**. Click **Publish**.

The success message and the data agent are displayed on the Agents page.
<img src="../images/image22.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">

