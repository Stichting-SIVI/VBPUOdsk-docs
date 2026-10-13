## 7.4 Transport / OpenAPI

### 7.4.1 OpenAPI Model

Since early 2024, work has been done on a standard for the transport of the messages. A number of PUOs and asset managers, in cooperation with SIVI, have taken steps in developing an OpenAPI specification within the technical outline sketched earlier.

This effort aimed both to support all parties that will implement the RESTful API and to promote uniform application of it. The specification can be found on [GitHub](https://github.com/Stichting-SIVI/VBPUOdsk/tree/main/VBPUO%20OAS%20(Open%20API%20Specificatie)). The proposed OpenAPI specification helps parties to exchange the message structures unambiguously, for both SPR and FPR. In addition to the substantive messages, a feedback message has also been created with which the substantive messages can be responded to.

The API acts as a digital service desk through which the various PUO and asset management parties can receive data. **Communication takes place on the initiative of the sending party (push model); the sending party delivers the messages to the receiving party without the receiving party having to actively ask for them.** The specification starts with general information, which states the name, description and version of the API.

The core of the API describes the specific services that are available. For each service, a clear path is defined to which messages can be delivered. This includes, for example, delivering information or carrying out certain actions. Each path provides a description of what the service does and how it can be used.

Note: in practice, not every party will offer all services from the OAS. Parties that only run SPR can, for example, offer the SPR messages 1, 2, 3 and 4 in addition to the feedback message.

In addition, the specification contains reusable building blocks, such as messages and entities. This ensures that the API is consistent and easy to understand and use. Reusing these messages and entities makes development simpler and reduces the chance of errors.

To safeguard the completeness and integrity of the messages, a mechanism has been introduced that makes it possible to check for changes during transport. This is a so-called x-jws-signature header, which contains a digital signature of the payload. This gives parties a reliable basis for trusting that received messages correspond exactly to what was sent. The use of this means is an option, not an obligation. Parties may make different choices.

**It is important that the standard supports only the OAS API; <u>other forms of data exchange are not supported</u>.** This means that all communication between parties must take place in accordance with the specified OpenAPI specification, and that alternative methods fall outside the scope of the standard.

**API Security Measures:**

The main security measures are as follows:

| **Security measure** | **Description** |
|----|----|
| Authentication with API key (option) | If this mechanism is used, each request contains a valid API key in the x-api-key header. This prevents unauthorised access to the API. |
| OAuth 2.0 Client Credentials Flow | The API uses OAuth 2.0 for authentication and authorisation. Clients must obtain an access token via the token endpoint with their client ID and secret. |
|  | Specific scopes are used to control access to different API functions, so that only authorised actions can be carried out. |
| Digital Signatures with x-jws-signature (option) | If this mechanism is used, each request contains a digital signature of the payload in the x-jws-signature header. This enables the recipient to verify that the message has not been changed during transport. . |
| Encrypted Communication via HTTPS | All communication takes place via HTTPS, which ensures encryption of data during transmission and protection against interception. |

### 7.4.2 API Implementation and Back-up

Deploying the APIs and keeping them operational is the responsibility of the party offering the API and falls outside the scope of the standard. (Temporary) failure of the API data transport facility may occur. The risk of this is smaller with an approach in which several replicas of the API run at the same time (in different environments and/or locations). Ultimately, this is a cost/benefit trade-off; guaranteeing 99.9% uptime is more costly than a 98% uptime guarantee.

The principle is that a failure will always be short-lived. In exceptional cases, email can serve as a “back-up” transport mechanism.
