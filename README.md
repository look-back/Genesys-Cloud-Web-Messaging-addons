# Genesys-Cloud-Web-Messaging-addons
* Transcript file generated on-the-fly automatically when agents disconnect the session
* Transcript generated per session (instead of conversation)
* Transcript in plain text format with timestamp and customer/agent names
* Audible alerting played when a new message comes

# Prerequisites
The feature 'Conversation Disconnect' should be enabled in Web Messaging configuration. The creation of transcript is triggered by 'disconnect' message, which is generated when agents click the disconnect button.

# References
* https://developer.genesys.cloud/commdigital/digital/webmessaging/messengersdk/SDKCommandsEvents/messagingServicePlugin

# Other thoughts
If customer would like to recevie transcript via email, Genesys Cloud Process Automation can be used. The basic idea is to trigger a workflow when agents disconnect a web messaging session. The workflow can leverage Genesys API to retrieve messages and send them out via email.
* configure a trigger for the topic '**v2.detail.events.conversation.{id}.user.end**'
* create a workflow as the trigger target
* **GET /api/v2/conversations/messages/{conversationId}** to get the list of message IDs
* **POST /api/v2/conversations/messages/{conversationId}/messages/bulk** to get the messages
* **POST /api/v2/conversations/emails/agentless** to send out transcript via agentless email

# Screenshots
![screenshot-1](https://user-images.githubusercontent.com/54515285/234136112-e68ee877-6ef7-4d70-b880-09857857843e.png)

![screenshot-2](https://user-images.githubusercontent.com/54515285/234136134-5fd6f9c0-6367-447a-beca-fce160ace8cc.png)

![screenshot-3](https://user-images.githubusercontent.com/54515285/234136163-5955398d-4562-48cf-895e-58a2287ff4d1.png)
