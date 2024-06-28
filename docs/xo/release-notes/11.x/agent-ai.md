# Agent AI Updates

This document provides information on the feature updates and enhancements introduced in **Agent AI** of XO v11.x releases.

## v11.2.1 June 15, 2024

<u>Patch Release</u>

This update includes bug fixes.

<hr>

## v11.2 June 01, 2024

<u>Patch Release</u>

This update includes feature enhancements and bug fixes. Key features and enhancements included in this release are summarized below.

### Auto-scroll Agent AI Widget Content

The **Auto-Scroll Assist Tab Content toggle** lets you manage the scrolling functionality of content in the Assist tab. Agents can enable/disable this toggle in the **AgentAssist widget** > **Settings** tab.
<img src="../images/autoscroll-settings-tab.png" alt="autoscroll-settings-tab" title="autoscroll-settings-tab" style="border: 1px solid gray; zoom:80%;">

<img src="../images/autoscroll-enabled-disabled-1.png" alt="autoscroll-enabled-disabled" title="autoscroll-enabled-disabled" style="border: 1px solid gray; zoom:80%;">

## Entity-Based Summarization

Dialog tasks having “message nodes” didn’t let users customize the Conversation Summary. Hence, to let users customize the Conversation Summary, “message nodes” are replaced with “entity nodes”. To utilize this capability, admins must create dialog tasks with entity nodes and select these dialog tasks in the **Agent AI** > **Configuration** > **Widget Settings** > **AgentAssist Channel Specific Settings** > **Auto Summarization** > **Auto Summarization Model** > **Custom Dialog Task** section.

<img src="../images/entity-based-summarization-2.png" alt="entity-based-summarization" title="entity-based-summarization" style="border: 1px solid gray; zoom:80%;">

For Conversation Summary customization, select a dialog task with “entity node” in the **Custom Dialog Task** field.

### Warm Transfer

Agent AI has introduced the **Warm Transfer** feature to customize the transfer functionality of the Agent AI widget. This feature specifically caters to third-party configurations, where appropriate transfer events are transmitted.

The **Warm Transfer** feature can be defined as a conference call between two agents and applies to both Voice and Chat channels. During this process, Agent-2 has the ability to modify the Summary Feedback, but the **Run**, **Override, Send, Copy, Terminate, Restart,** and **List View** buttons remain disabled until Agent-1 disconnects from the call. It has the following options to choose from:

* **Scroll up to the First Message**

* **Continue from the Last Message**

* **Configure Dialog Task**

### Negative Feedback Settings

For better processing and accurate identification of reasons for receiving a “thumbs down”, Admins can now configure a list of negative feedback messages for agents to select. They can also include a comment box for agents to add additional comments. Admins decide whether these two options appear in the widget after agents select the “thumbs down” icon at the end of a Dialog Task and after each answer and FAQ. Additionally, Admins can change the language of the feedback messages by selecting one from the available language list.

**Feedback Settings in the AgentAssist UI**:

<img src="../images/feedback-settings-ui-3.png" alt="feedback-settings-ui" title="feedback-settings-ui" style="border: 1px solid gray; zoom:80%;">

**Feedback Messages and Comment Box in the Widget**:

<img src="../images/feedback-settings-widget-4.png" alt="feedback-settings-widget" title="feedback-settings-widget" style="border: 1px solid gray; zoom:80%;">

<hr>

## v11.1.1 May 11, 2024

<u>Patch Release</u>

This update includes bug fixes.

<hr>

## v11.1.0 April 27, 2024

<u>Minor Release</u>

Key features and enhancements included in this release are summarized below.

### Agent AI Widget Updates

#### No Results Found and No Dialog Tasks Enabled Messages

The Agent AI widget now shows the “No Search Result Found. Could you rephrase your question or ask something else?” message when an agent’s search query on the search bar doesn’t show any results.
If no dialog tasks are configured for an account, the message “No dialog tasks enabled for library” appears in the Library/Search tab.

#### Updates to the Override Mode of the Agent AI widget

**Override Mode Off**
        
* When the customer's input is expected, the field remains grayed out and displays the entity name followed by “waiting….”
* The “Override” call-to-action (CTA) appears, and agents can click it to override the customer's utterance and manually populate the entity field.

**Override Mode On**
        
* The green “tick” mark that appeared after receiving the customer’s input is removed.
* The Entity Display Name appears with a cursor to indicate editing mode.
* Introduced the Cross and Check icons.
* The “keyboard” icon is replaced with the “agent” icon to indicate agent input.

### Agent AI Configuration with OpenAI GPT-3.5

For enhanced Real-time Coaching and Playbooks performance, the AgentAI configuration is now upgraded from OpenAI GPT 3.0 to OpenAI GPT 3.5. OpenAI GPT 3.5 delivers more accurate and context-aware responses, thereby enhancing Real-time Coaching effectiveness and Playbooks quality.

### Feedback Mechanism for Answers
In an effort to constantly improve the accuracy and helpfulness of answers displayed on the AgentAI widget, Kore has introduced a feedback mechanism for agents. Agents can now click the “thumbs up” or “thumbs down” icon displayed with every answer to indicate positive or negative feedback. This feedback data will help train Agent AI to provide more accurate answers.

### SearchAssist Configuration Page Updates

The SearchAssist Configuration page inside Agent AI has been updated with the following changes:

* Stream ID has been replaced with App ID.
* A warning is displayed when a user enters incorrect values in the configuration fields -  “Could not establish connection with SearchAssist. Check all parameters and try again. Hint: Ensure that the domain URL does not contain "https://" and does not have a forward slash "/" at the end.”
* As soon as a user lands on the configuration page, the following hint is displayed: “Ensure that the domain URL does not contain "https://" and does not have a forward slash "/" at the end.” 
* If a user enters incorrect values in the configuration page, the following error message is displayed: “Error establishing connection.

### Conversation Transfer Experience (Third-Party Agent Desktop)

Agent AI has introduced the Conversation Transfer feature to customize the transfer functionality of the Agent AI widget. This feature is applicable only to the third-party configurations where appropriate transfer events are transmitted. The Cold Transfer type applies to all three channels - Chat, Voice, and Email and has the following options to choose from:
* Scroll up to the First Message
* Continue from the Last Message
* Configure Dialog Task

### Configure your own Auto Summarization Model (Third-Party Agent Desktop)

Agent AI has introduced the **Auto Summarization Model** widget to customize the automatic summarization process. You can now select Kore’s default automatic summarization or the “Custom Dialog Task“ option, which lets you select a “dialog task with a single message node” to automatically generate the conversation summary. This is applicable only to third-party agent desktops.

After enabling the **Auto Summarization** toggle, select one of the following options:

* **OOTB Kore Summarization**: For Kore’s default auto summarization
* **Custom Dialog Task**: To generate customized auto summarization, you must select a dialog task with a single message node. These message nodes call APIs.

The **Custom Dialog Task** field displays a list of dialog tasks or child bots based on bot selection at the app level. 

The Agent AI widget's Assist tab now displays an updated Summary that includes the following:

* A **.ai Suggested** logo.
* The summary textbox has a cross icon for clearing the text.
* Ability to freely edit the summary within the text box.

After submission, the summary appears under the “.ai CONVERSATION SUMMARY” title with a **Copy** button at the bottom-right corner.

### Updated Summarization Feature

Agent AI has improved the Summarization feature of its widget. The latest version comes up with improved summary accuracy and advanced handling of various scenarios in conversations between agents and users. Currently, this update is available only for the US PROD environment and supports English. It is not yet available for DE, JP, EU, AU, and IND environments.  

**Key Highlights**
    
* Improved Summary Accuracy: The summary accuracy has been significantly improved through the implementation of a new model, and Agent AI is fine tuning it for specific use cases.
* Summary for Small Conversations: Agent AI has effectively addressed issues related to agent transfer scenarios between bots and users, ensuring seamless communication and comprehension.
* Handling Incomplete Summaries: The new model handles incomplete summaries more effectively, providing more comprehensive and useful insights even when the conversation is not fully concluded.
* Handling Longer Calls: The new model handles longer calls extending up to 20 minutes. The previous model would generate incomplete summaries for such extended conversations.

### Agent Coaching Updates

In Agent Coaching > Utterance Trigger section, **Anytime in conversation** is now a default selection for the “in conversation” field.

### Dashboard Updates

#### Enhanced Agent Feedback Functionality

The AgentAI dashboard has been updated to include a detailed summary of Agent Feedback for dialog tasks, including "Not Helpful" feedback and additional comments. Users can now get a detailed view of the “Not Helpful” feedback with Responses, Additional Comments, and Counts.

#### Average Widget Usage (Third-Party Agent Desktop)

The Dashboard has been updated to include the Average Widget Usage feature. This feature gives a graphical representation of the average amount of time agents spend on the AgentAI widget.