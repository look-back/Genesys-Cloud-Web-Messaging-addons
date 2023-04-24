# Genesys-Web-Messaging-addons
* Transcript file generated on-the-fly automatically when agents disconnect the session
* Transcript generated per session (instead of conversation)
* Transcript in plain text format with timestamp and customer/agent names
* Audible alerting played when a new message comes

# Prerequisites
The feature 'Conversation Disconnect' should be enabled in Web Messaging configuration. The transcript downloading is triggered by 'disconnect' message, which is generated when agents click the disconnect button.

# References
* https://developer.genesys.cloud/commdigital/digital/webmessaging/messengersdk/SDKCommandsEvents/messagingServicePlugin