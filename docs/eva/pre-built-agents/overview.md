# Pre-built Agents

AI for Work includes a set of pre-configured AI agents that can be easily customized and integrated into workflows. These agents help streamline operations and enhance productivity.

Following are the prebuilt agents supported by AI for Work:

## Pre-Built API Agents

* **Zendesk** - It helps us to fetch Zendesk tickets based on entities.
* **Slack** - It helps us to send the response to Slack channels and threads.
* **O365 Calendar**- It helps us to create calendar events, fetch calendar events based on filters, check the availability of colleagues, and send quick messages in case of a delay in joining the meeting.
* **O365 Email**- It can get emails based on user queries fetching entities, send responses as emails, set individual emails as context, and ask for follow-ups.
* **OneDrive** - It can fetch files based on user queries and filters and set individual file as context and ask followup questions.
* **Teams** - It can fetch files based on user queries and filters, set individual files as context, and ask follow-up questions.
* **Jira** - It can retrieve issues based on user queries using entity filters and effortlessly create Jira issues using AI intelligence derived from action items.
* **HubSpot** - It helps in pulling deals based on user queries.
* **Google Calendar** - It can create calendar event, fetch calendar events based on filters, check availability of colleagues and send quick messages in case of delay in joining meeting.
* **Gmail** - It can get emails based on user queries fetching entities, can send responses as emails, can set individual emails as context and ask followups.
* **Drive** - It can fetch files based on user queries and filters and set individual file as context and ask followup questions.

## Pre-Built Prompt Agents

* **Summarizer** - It helps to summarize content based on the provided material into selected summary formats.
* **Mail scribe** - It helps to draft emails based on the topic description.
* **Translate** - It helps to translate uploaded files or pasted content into any language as requested. 

## Publish a Pre-Built Agent

Administrators can publish the selected pre-built agents to be available for their users via the Agent Store. 

Steps to publish a pre-built agent:

1. Navigate to **User Profile** > **Admin Console** > **AI Search or AI Agents** > **API Agents** or **Prompt Agents**. A list of available Pre-Built Agents is displayed. The "Prebuilt" label is added next to all the Pre-built Agents.  
<img src="../images/api-agents.png" alt="api-agents" title="api-agents" style="border: 1px solid gray; zoom:60%;">

2. To enable the Agent, Toggle the switch **ON** or click the **ellipsis** next to the specific agent. A pop-up window will appear.  
<img src="../images/enable-api-agents.png" alt="enable-api-agents" title="enable-api-agents" style="border: 1px solid gray; zoom:60%;">

3. Provide the following details:
    * **Published Version**: Select the version of the agent you are publishing.
    * **Publish to**: Choose who will have access to the agent:
        * **Admins**: Restrict the agent to Admin users only.
        * **Selected User groups/Users**: Specify individual users or groups.
        * **Everyone in the Account**: Make the agent available to all users.
    * **Actions**: admins can decide whether an end user can perform only lookup actions or both lookup and creation actions. 
        * **Lookup**
        * **Creation**  
        <img src="../images/publish-agent.png" alt="publish-agent" title="publish-agent" style="border: 1px solid gray; zoom:60%;">

4. Click **Publish.** The agent is now available for the users to use in the Agent Store.  
<img src="../images/agent-store.png" alt="agent-store" title="agent-store" style="border: 1px solid gray; zoom:60%;">
 
Now, users can click **Connect** for the Agent and follow the on-screen instructions to **Add Connection**. Once the connection is added successfully, the agent can take users’ questions or queries using the Ask or Search Anything box.  
<img src="../images/add-connection.png" alt="add-connection" title="add-connection" style="border: 1px solid gray; zoom:60%;">

