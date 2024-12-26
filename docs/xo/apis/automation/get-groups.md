# Get Groups API

To get the list of groups and group members available in the account.


!!!note
    This API requires JWT generated by an application created only from the Bot Admin Console.


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
   <td><code>https://{{host}}/api/public/groups?offset=0&limit=2</code>
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
See <a href="../api-introduction/#generating-the-jwt-token">How to generate the JWT Token.</a>
   </td>
  </tr>
  <tr>
   <td><strong>API Scope</strong>
   </td>
   <td>
<ul>

<li>Bot Builder: Not Applicable

<li>Admin Console: Profile Management > Role Management
</li>
</ul>
   </td>
  </tr>
</table>



## Path Parameters


<table>
  <tr>
   <td><strong>PARAMETER</strong>
   </td>
   <td><strong>REQUIRED/OPTIONAL</strong>
   </td>
   <td><strong>DESCRIPTION</strong>
   </td>
  </tr>
  <tr>
   <td>host
   </td>
   <td>Required
   </td>
   <td>Environment URL, for example, https://platform.kore.ai
   </td>
  </tr>
  <tr>
   <td>offset
   </td>
   <td>Optional
   </td>
   <td>Specify the page number from which to start fetching the group records. If unspecified, it starts from 0, which is the first page of the group records.
   </td>
  </tr>
  <tr>
   <td>limit
   </td>
   <td>Optional
   </td>
   <td>The number of records to fetch. The maximum applicable limit is 50.
   </td>
  </tr>
</table>



## Sample Request


```json
curl -X GET \
  'https://{{host}}/api/public/groups?offset=0&limit=2' \
  -H 'auth: {{YOUR_JWT_ACCESS_TOKEN}}' \
```


 


## Sample Response


```json
{
    "total": 2,
    "availableMore": false,
    "groups": [
        {
            "_id": "e-eed8e93a-79ff-523b-9545-4833c2683e86",
            "gN": "Audit",
            "gDesc": "Audit Team",
            "groups": [],
            "users": [
                {
                    "_id": "u-c32243f6-b4ba-5884-9527-a7efb9a0ac9e",
                    "emailId": "sample1@sampleemail.com",
                    "lastName": "Sample1",
                    "firstName": "Sample",
                    "profImage": "profile.png",
                    "profColour": "#ffd700",
                    "activationStatus": "active",
                    "jTitle": "",
                    "orgId": "o-c2419ad3-e160-5bae-af32-6e62f1153a1e"
                },
                {
                    "_id": "u-f2323ccf-b475-59a9-a52b-194698ee0230",
                    "emailId": "sample2@sampleemail.com",
                    "lastName": "Sample2",
                    "firstName": "Sample",
                    "profImage": "profile.png",
                    "profColour": "",
                    "activationStatus": "active",
                    "jTitle": null,
                    "orgId": "o-8f992732-faa8-5191-bab5-db39efc10a9f"
                }
            ],
            "userCount": 2
        },
        {
            "_id": "e-8c91bfc5-8ecd-5707-9c35-7539297e77c9",
            "gN": "RiskManagement",
            "gDesc": "Risk Management Team",
            "groups": [],
            "users": [
                {
                    "_id": "u-0204c8d7-24d4-5ggf-bd73-7c4eaf093b83",
                    "emailId": "sample3@sampleeemail.com",
                    "lastName": "Sample2",
                    "firstName": "Sample",
                    "profImage": "no-avatar",
                    "profColour": "#2e8b57",
                    "activationStatus": "active",
                    "jTitle": "",
                    "orgId": "o-1b67d2f0-4812-5083-8453-55b8f5f9247f"
                },
                {
                    "_id": "u-19ecg162-40cb-5f0c-b594-2ac52211f09b",
                    "emailId": "sample3@sampleemail.com",
                    "lastName": "Sample3",
                    "firstName": "Sample",
                    "profImage": "no-avatar",
                    "profColour": "#ff0000",
                    "activationStatus": "active",
                    "jTitle": null,
                    "orgId": "o-642h0c8a-6e89-5ffe-8tb4-0eacd11c5b41"
                }
            ],
            "userCount": 2
        }
    ]
}
```