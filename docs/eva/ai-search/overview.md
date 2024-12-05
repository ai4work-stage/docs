# AI Search

Coming Soon





#### **Field Selection**

Field selection determines which data is visible to users and available for search queries, optimizing the user interface and the search functionality. You can select up to 10 fields from the API response for practical use within the system.

Example: In a Jira context, you can choose fields like assignee, status, priority, key, and summary for filtering and display. If you select only two out of five available fields, the system restricts search and display to those two fields only.

The screenshot below shows that the query can be generated using three selected fields - id, amount, and dealname.

On the **Select Fields** section, click the **field** to select. Click **Continue**.
You can navigate through records using the "Prev field" and "Next field" options.

<img src="../images/agent(19).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">



#### **Field Configuration**

The Field Configuration tab lets you configure the fields that you selected earlier. The tab shows the following fields/attributes that can be configured: 

**Primary Field**: Select the primary field for the data table. This field will be the leftmost column presented to users.

**Field Key**: It shows user-chosen fields (non-editable) used to construct API requests. Each field corresponds to a specific API key, which may differ from the user-visible label. For example, "JIRA ID" might be displayed to users, but the API request uses "id" as the parameter.

This mapping ensures accurate data retrieval by translating user-friendly labels into the correct API parameters. The system creates precise API queries with selected fields and keys, balancing clarity and accuracy in data retrieval.

**Field Label**: Sourced from the schema API response and field selection tab. You can modify or add missing labels as needed. If the schema API doesn't provide a label, you can input one manually.


<img src="../images/agent(13).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">


**Field Type**: The field type determines how users can query each field. This information is crucial for constructing appropriate filter APIs. For example, text fields require different query parameters compared to object fields.

Field types are primarily derived from the schema API. Additionally, the system employs internal logic to set field types when necessary. Some fields, like assignee, status, and priority, may be represented as nested JSON structures.

Accurate field types ensure the system generates correct query syntax for each field, enabling accurate and efficient data filtering. It also helps display appropriate options to users when they construct queries. 


<img src="../images/agent(11).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">


**Field Value Resolver**: It's applicable only to object field types. A Field Value Resolver can help with the following:

* Handles and renders information returned from a data API.
* Maps values to appropriate labels and icons.
* Extracts and displays relevant data from nested JSON objects in a user-friendly format.

Field Value Resolvers maintain data integrity in presentation and interaction, bridging user-friendly labels with technical API requirements.

Follow these steps to add a field value resolver:



1. Click the **+** (Plus) icon in the field value resolver for the field type object.
<img src="../images/agent(3).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
2. The Value Resolver pop-up is displayed.
    1. If the field value resolver didn't find the JSON, the following value resolver pop-up is displayed. Click **Define API** to resolve the id.
    <img src="../images/agent(2).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
        1. Click **CURL Import**. You can also use a dictionary instead of a CURL import. Learn [how to create one](#bookmark=kix.ydh0q0ricc12).
        <img src="../images/agent(5).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
        2. The import URL pop-up is displayed. Paste the URL and click **Import**.
        <img src="../images/agent(8).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
        3. Type in the **Sample Input** and click **Run**.
        4. The Output Fields are displayed.
        <img src="../images/agent(14).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
        5. Close the pop-up. The ID resolver is displayed.
        <img src="../images/agent(16).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
    2. If the field value resolver finds the JSON, the following value resolver pop-up is displayed.
    <img src="../images/agent(23).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
        1. Click **Goto Mapper**.
        <img src="../images/agent(27).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
        2. Click **Map Value**. Select fields pop-up is displayed. This step resolves the fields.
        <img src="../images/agent(15).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
        8. Select the field which is displayed to the user and close the pop-up. For example, "displayName".
        9. Click **Map ID**. Select fields pop-up is displayed.
        <img src="../images/agent(1).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
        10. Select the field that will be passed to the API and close the pop-up. For example, "accountId".
        11. If Map Color, Map Icon, and Map Icon Color information is available, map the required fields and close the pop-up.
        <img src="../images/agent(12).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
3. The field value resolver mapping is completed.

**Field Options**: Field Options are predefined choices for single-select or multi-select fields, helping users filter and retrieve data accurately. These options are activated when a field is identified as single-select or multi-select and are typically fetched from the schema API.

Each option includes a label, value, display order, and visibility status. This structure allows for flexible and customizable presentation of choices to the user.

**A crucial feature of Field Options is the mapping between user-friendly labels and technical keys required for API requests**. For example, while a user might see a "Priority" field with options like "High," "Medium," and "Low," the API might use corresponding numerical or string values. This mapping ensures accurate data retrieval by configuring what is displayed to the user and what is sent in API requests.

!!! note

    This field is applicable only if the Field Type is Single Select or Multi Select.

Follow these steps to add field options:



1. Click the **+** (Plus) icon in the field option for the field type Single Select or Multi Select.
2. The options pop-up is displayed.
<img src="../images/agent(4).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
3. Enter the **Map Value** (Displayed to the user) and **Map Label** (sent to the API) for each priority.
    1. If the schema API is mapped:
        1. Click **Map Value**, the JSON object is displayed.
        2. Select the field that will be passed to the API.
        3. Click **Map Lable**, the JSON object is displayed.
        4. Select the field which will be displayed to the user.
        5. Rest all the choices are automatically populated.
    2. If the schema API is not mapped, manually enter map value and map label for each choice. For example, if you have high, medium, and low priority choices.
    <img src="../images/agent(25).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
4. Close the pop-up.

**Field Meta Resolver**: The Field Meta Resolver interprets user-provided meta-information and determines the correct value to send to the API. It resolves specific field values at runtime before making API calls, ensuring data retrieval and filtering accuracy.

This resolver includes an API module for defining and testing with sample input. It works similarly to an ID resolver, requiring the definition of the API call and the input mapping for both value and ID.

A key function of the Field Meta Resolver is retrieving the id of entities extracted from the user query.

!!! note

    This field is applicable only if the Field Type is Object.

Follow these steps to add a field meta resolver:



1. Click the **+** (Plus) icon in the field meta resolver for the field type object.
2. Click **CURL Import**. You can also use a dictionary instead of a CURL import. Learn [how to create one](#bookmark=kix.ydh0q0ricc12).
<img src="../images/agent(28).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
3. The import URL pop-up is displayed. Paste the URL and click **Import**.
<img src="../images/agent(25).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
4. Type in the **Sample Input** and click **Run**.
<img src="../images/agent(29).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
5. The Output Fields are displayed.
<img src="../images/image15.png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
6. Close the pop-up. The ID resolver is displayed.
<img src="../images/agent(26).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
7. Click **Continue**.

**Dictionary**

If API support is unavailable, you can use a dictionary as a local data store to map and resolve IDs or metadata. It acts as a cache, storing data fetched from APIs for fast, local queries, reducing the need for repeated API calls. You can schedule automatic updates to keep the dictionary current. Once created, it can be shared across agents or modules within the same account, making it a useful tool for improving performance and reducing dependency on APIs.

You can use the existing dictionary if any. To select, toggle **Use Dictionary**, select the dictionary, and click **Run**. The output fields are displayed.

<img src="../images/agent(21).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">



Follow these steps to create a dictionary:


1. On the field value resolver or field meta resolver popup, toggle the **Use Dictionary**.
<img src="../images/agent(24).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
2. Click **+ Create**.
3. On the Name & API tab, enter the **dictionary name**, **API call details** to feed the dictionary, and **pagination** details if required.
<img src="../images/agent(9).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
4. Click **Run API**. The field selection tab is displayed.
5. On the Field Selection tab, **select the fields** to be searched, **ID resolver field**, **Schedule to Pool data** frequency, and enter the **meta resolver field**.
<img src="../images/agent(17).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
6. Click **Pool data into the dictionary**. The preview tab is displayed.
7. On the Preview tab, the pooled data is displayed.
<img src="../images/agent(18).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
8. Click **Done**. The dictionary is saved.



#### **Preview**

Displays processed data to users, initially showing five records with an option to load more. Users can configure an “open” option that appears when hovering over any record. Clicking it will open a record in a new tab. 

<img src="../images/agent(7).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">



Follow these steps to create a URL:



1. To configure the URL, click  **+ Create URL**.
2. The Open URL pop-up is displayed.
    <img src="../images/agent(22).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
3. Enter the Static URL. For example, https://koreteam.atlassian.net/browse/.
!!! note

    You can create a Dynamic URL using the response objects. 
4. The Variable mapper pop-up is displayed. Select the dynamic part of the URL i,e **Key,** and close the pop-up.
    <img src="../images/agent(6).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
5. Click **Done**. The Open option and the configured link are displayed.
<img src="../images/agent(3).png" alt="API Agent" title="" style="border: 1px solid gray; zoom:70%;">
6.  Click **Continue**.