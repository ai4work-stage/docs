# Bot Import Status API

To get the status of the bot import request initiated using the **Import Bot** API for a new bot or an existing bot.

!!!note
    This API requires the JWT generated by an application created on the **Bot Admin Console**.

<table>
  <tr>
   <td><strong>Method</strong>
   </td>
   <td>GET
   </td>
  </tr>
  <tr>
   <td><strong>Endpoint</strong>
   </td>
   <td><code>https://{{host}}/api/public/bot/import/status/{{BotImportBIR}}</code>
   </td>
  </tr>
  <tr>
   <td><strong>Content Type</strong>
   </td>
   <td><code>application/json</code>
   </td>
  </tr>
  <tr>
   <td><strong>Authorization</strong>
   </td>
   <td><code>auth: {{JWT}}</code>
<p>
See <a href="../api-introduction/#generating-the-jwt-token">How to generate the JWT Token</a>.
   </td>
  </tr>
  <tr>
   <td><strong>API Scope</strong>
   </td>
   <td>
<ul>

<li>Bot Builder: Not Applicable

<li>Admin Console: Bot Definition > Bot Import
</li>
</ul>
   </td>
  </tr>
</table>

## Query Parameters

<table>
  <tr>
   <td><strong>PARAMETER</strong>
   </td>
   <td><strong>DESCRIPTION</strong>
   </td>
   <td><strong>MANDATE</strong>
   </td>
  </tr>
  <tr>
   <td><strong>host</strong>
   </td>
   <td>The environment URL. For example, https://bots.kore.ai
   </td>
   <td>Required
   </td>
  </tr>
  <tr>
   <td><strong>BotImportBIR</strong>
   </td>
   <td>bir-xxxxxxx-xxx-xxxx-xxxxx-xxxxxxxxxx. The BIR ID is found in the response of the <a href="../import-bot-as-a-new-bot-api">Import Bot as a New Bot API</a> endpoint.
   </td>
   <td>Required
   </td>
  </tr>
</table>

## Sample Request


```json
curl -X GET 'https://{{host}}/api/public/bot/import/status/bir-xxxxxxx-xxx-xxxx-xxxxx-xxxxxxxxxx' \
  -H 'auth: {{YOUR_JWT_ACCESS_TOKEN}}' \
```

## Body Parameters

No Body Parameters passed.


## Sample Response

```json
{
    "_id": "bir-5fxxxxxx-a0xx-52xx-axxf-f3xxxxxxxxxx",
    "status": "success",
    "streamRefId": "d1xxxxxx-bxx7-5cxx-axx7-a8xxxxxxxxxx",
    "statusLogs": [
        {
            "taskType": "importRequest",
            "taskName": "SampleBot",
            "status": "success"
        },
        {
            "taskType": "Bot Definition",
            "taskName": "SampleBot",
            "status": "success"
        },
        {
            "taskType": "IdpConfigurations",
            "taskName": "IdpConfigurations",
            "status": "success"
        },
        {
            "taskType": "CustomTemplates",
            "taskName": "CustomTemplates",
            "status": "success"
        },
        {
            "taskType": "BotFunctions",
            "taskName": "Bot Functions",
            "status": "success"
        },
        {
            "taskType": "Widget",
            "taskName": "UnderwritingExplanation",
            "status": "success"
        },
        {
            "taskType": "Dialog",
            "taskName": "Test Firebase Service",
            "status": "success"
        },
        {
            "taskType": "Form",
            "taskName": "BloodPressure",
            "status": "success"
        },
        {
            "taskType": "Widget",
            "taskName": "WidgetPhysique",
            "status": "success"
        },
        {
            "taskType": "Dialog",
            "taskName": "ShowDiseaseList",
            "status": "success"
        },
        {
            "taskType": "Event",
            "taskName": "TASK_FAILURE_EVENT",
            "status": "success"
        },
        {
            "taskType": "Event",
            "taskName": "WELCOME_MESSAGE_EVENT",
            "status": "success"
        },
        {
            "taskType": "Event",
            "taskName": "INTENT_UNIDENTIFIED",
            "status": "success"
        },
        {
            "taskType": "Event",
            "taskName": "CONVERSATION_END",
            "status": "success"
        },
        {
            "taskType": "KnowledgeTasks",
            "taskName": "KnowledgeTasks",
            "status": "success"
        },
        {
            "taskType": "Utterences",
            "taskName": "Utterences",
            "status": "success"
        },
        {
            "taskType": "Patterns",
            "taskName": "Patterns",
            "status": "success"
        },
        {
            "taskType": "BotVariables",
            "taskName": "BotVariables",
            "status": "success"
        },
        {
            "taskType": "SmallTalk",
            "taskName": "SmallTalk",
            "status": "success"
        },
        {
            "taskType": "importBot",
            "taskName": "SampleBot",
            "status": "success"
        }
    ],
    "createdBy": "u-adxxxxxx-e9xx-5xxd-axxc-21xxxxxxxxxx",
    "requestType": "Botimport",
    "createdOn": "2022-07-29T07:24:17.496Z",
    "__v": 0,
    "streamId": "st-8axxxxxx-0xxb-5axx-9xx2-97xxxxxxxxxx"
}
```