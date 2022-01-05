# About Whispir
With Whispir, enterprises and organizations can schedule, automate, and send messages by SMS, email, web forms, WhatsApp, Facebook, Twiter, voice, video, text to speech — all from a single, easy-to-use platform.

# WhatsApp-communications-through-Whispir
The Whispir platform provides a capability of sending WhatsApp messages with rich content. Whispir provides both access to a web portal and REST APIs to send templated WhatsApp messages to recepients.

Before using WhatsApp for sending messages, there are certain prerequisites that needs to be completed, and Whispir team assists thier customers in completing the paperwork for a smooth onboarding.
1.	Setup of a WhatsApp Customer Business Account(WABA)
2.	Signed WhatsApp Addendum for Indirect Customers (Supplier)

The WhatsApp business account setup can take anywhere from 2-4 weeks.
Once the WhatsApp Business Account (WABA) is set up for a new Customer, the Customer will have access to login to the WABA portal, and will be able to create and place a WhatsApp template for approval, before the approved template can be used for sending WhatsApp messages.

Sample WABA template screen below:

![image](https://user-images.githubusercontent.com/96904835/147811650-ce1f6f4a-2dbe-4ec5-b4c7-d594bbed01a4.png)


The template approval from WhatsApp can take up to 48 hours based on the content of the WhatsApp template.

After the WhatsApp template is approved, then the Customer can create the template in the Platform using REST APIs or the Platform’s web portal.

## Creating approved WhatsApp templates using Whispir REST APIs

The WhatsApp template can be created by using /templates endpoint with POST method.
More details with sample request/response sample payload can be found below:

Create new template by using **/templates** endpoint with POST

**Sample request**

```
POST http://whatsapp.[region].whispir.com/templates
Headers: 
Content-Type: application/json
Authorisation: Bearer
```
**Request Payload Syntax**

```
{
  "name": "[Name of the WhatsApp template]",
  "whatsappId": "[WhatsApp generated token]:igniteagain]",
  "content": "[WhatsApp message body]", 
  "description": "[Template description]",
  "parameter": "{\"parameter_count\":0,\"parameter_data\":[]}"
}
```
**Sample Request payload**
```
{
  "name": "igniteagain",
  "whatsappId": "5d63f94c_f696_bcbb_9da6_d6853d575f90:igniteagain",
  "content": "Hello, your account has been updated. Please visit {{1}} or {{2}} for more information", 
  "description": "This is a test template",
  "parameter": "{\"parameter_count\":0,\"parameter_data\":[]}"
}
```
* **required fields**: "name", "whatsappId","content"
* **"name"**: must be low case, number and underscore, maximum 30 characters

**Sample Response**
```
{
    "id": "17",
    "name": "igniteagain",
    "whatsappId": "5d63f94c_f696_bcbb_9da6_d6853d575f90:igniteagain",
    "type": "TEXT_TEMPLATE",
    "description": "This is a test template",
    "content": "Hello, your account has been updated. Please visit {{1}} or {{2}} for more information",
    "parameter": "{\"parameter_count\":0,\"parameter_data\":[]}",
    "language": "{\"en\"}",
    "ownerCompanyId": "64",
    "created": "2020-07-20T05:31:29.537Z",
    "modified": "2020-07-20T05:31:29.537Z"
}
```
## Creating approved WhatsApp templates in Whispir Web portal
The Supplier provides a web portal to create WhatsApp approved templates that can be used for sending WhatsApp messages.

**The steps for Adding an Approved WhatsApp template in the Platform’s web portal is listed below:**

1.Add a new Approved WhatsApp template name and language and click Continue.

![image](https://user-images.githubusercontent.com/96904835/148198977-d4d2a142-5782-42b4-bc18-64e1c35ff07f.png)

2.Add the approved message content and any media type selected and click on Save to create the template in the Platform.

![image](https://user-images.githubusercontent.com/96904835/148198533-b12b037b-580c-43f2-be00-41d1ae8468e7.png)

* Whispir supports messaging to WhatsApp through Whispir platform REST APIs and Web portal.
* Whispir supports both rich content and multimedia (i.e. Image, Video, document and location) messaging through WhatsApp.






