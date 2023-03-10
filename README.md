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

Whispir Messaging API and platform hide the complexity of hosting and scaling WhatsApp software so that the customer can focus on elevating customer experiences.
Please note that WhatsApp restricts any marketing messages through its channel and does not approve any templates that contain any marketing content. Notwithstanding the above, the Customer can still send a WhatsApp message targeting marketing keeping their WhatsApp message content as non-marketing and putting the marketing content in the Supplier’s microsite link that is sent as part of WhatsApp message.

## Sending WhatsApp message using the Platform’s web portal
 
The below screenshot shows how the Customer can use an existing WhatsApp approved template to send a WhatsApp message from the Platform. The Platform provides many native/system variables that can be used to be included in the WhatsApp message to personalise the message.

![image](https://user-images.githubusercontent.com/96904835/148511905-b8ed8634-24ab-4e36-be13-edd4bcb0b29b.png)

## Sending WhatsApp messages using Supplier’s REST APIs

Whispir platform’s REST APIs supports sending WhatsApp messages using a WhatsApp approved template both in real-time and in bulk.
More details on how to send WhatsApp messages using Whispir platform APIs can be found below:
https://developers.whispir.com/docs/whatsapp-messages

Sample WhatsApp message below triggered from Whispir’s platform:
![image](https://user-images.githubusercontent.com/96904835/148512071-ac2fad31-ac44-464d-a720-878ddd91be76.png)


# WhatsApp Business Policy

The below sections on "Opt-in" and "Acceptable Message Types" only apply to the WhatsApp Business Solution (WhatsApp Business API).

## Opt-in

* In order to initiate a WhatsApp message to a person, you must first receive opt-in permission confirming that they wish to receive future messages from you on WhatsApp. The opt-in must (a) clearly state that the person is opting in to receive messages from you over WhatsApp and (b) clearly state your business’ name.
* You are solely responsible for determining the method of opt-in, that you have obtained opt-in in a manner that complies with laws applicable to your communications, and that you have otherwise provided notices and obtained permissions that are required under applicable law.
* To help ensure a strong user experience, review the Opt-in best practices suggested below.

## Acceptable Message Types

* You may only initiate conversations using an approved Message Template (as defined in our documentation). This is considered a business-initiated conversation,which is subject to applicable pricing. Any Message Template must comply with our terms and these policies, and only be used for its designated purpose. We have the right to review, approve and reject any Message Template at any time.
* You may reply to a user message without use of a Message Template as long as it's within 24 hours of the last user message. Conversations initiated by users open once the first business reply message is delivered. Standard pricing applies for these user-initiated conversations. Outside the 24-hour customer service window, you may only send messages via approved Message Templates, for which we will charge the business-initiated conversation rate.
* You may use automation when responding during the 24-hour window, but must also have available prompt, clear, and direct escalation paths. These escalation paths include:
   * In Chat Human Agent transfer
   * Phone number
   * Email
   * Web support (on the business website)
   * In-store visits (ex: visit retail store, bank branch)
   * Support form

## Protect Data & Comply with Law

* You are responsible for and must secure all necessary notices, permissions, and consents to collect, use, and share people's content and information, including maintaining a published privacy policy, and otherwise complying with applicable law.
* Don't use any data obtained from us about a person you message within WhatsApp, other than the content of message threads, for any purpose other than as reasonably necessary to support messaging with that person.
* Don't share or ask people to share full length individual payment card numbers, financial account numbers, personal ID card numbers, or other sensitive identifiers.
* Don’t use WhatsApp for telemedicine or to send or request any health information, if applicable regulations prohibit distribution of such information to systems that do not meet heightened requirements to handle health information.
* You may not forward or otherwise share information from a customer chat with any other customer.

## Opt-In Best Practices

Driving high quality conversations between people and businesses is a top priority. People can block or report businesses and our systems will rate limit businesses if the business' quality is low for a sustained period of time. We may also reactively evaluate a business' opt-in flows, including review of user feedback, to flag policy violations and develop additional types of enforcement over time.

Best practices to create a high-quality opt-in experience:

* Users should expect the messages they receive. You can set this expectation by:
    * Obtaining an opt-in that encompasses the different categories of messages that you will send (ex: order updates, relevant offers, product recommendations, etc.)
    * Obtaining separate opt-in by specific message category

This mitigates the risk that users will block your business because they receive unsolicited messages.

* Provide clear instructions for how people can opt out of receiving specific categories of messages, and honor these requests.
* Ensure your opt-in and opt-out flows are clear and intuitive for users.
* Clearly communicate the value of receiving this information on WhatsApp.

## Quality Rating

Your quality rating is based on how messages have been received by recipients over the past seven days and is weighted by recency. It is determined by a combination of quality signals from conversations between businesses and users. Examples include user feedback signals like blocks, reports and the reasons users provide when they block a business.

The phone number status, quality rating, and messaging limits for your WhatsApp business account are listed in the Phone Numbers tab in WhatsApp Manager.

![image](https://user-images.githubusercontent.com/96904835/148517205-0d2c147f-7494-4ec2-9ba1-47f7355448b6.png)

  ## Messaging Limits
  
Messaging limits determine how many unique users your business can send messages to on a daily basis. This includes new conversations as well as existing conversations with users. The messaging limit does NOT limit the number of messages your business can send, just the number of users you are trying to message. It also does NOT apply to messages sent in response to a user-initiated message within a 24-hour period.

* Tier 1: Allows your business to send messages to 1K unique customers in a rolling 24-hour period.
* Tier 2: Allows your business to send messages to 10K unique customers in a rolling 24-hour period.
* Tier 3: Allows your business to send messages to 100K unique customers in a rolling 24-hour period.
* Tier 4: Allows your business to send messages to unlimited unique customers in a rolling 24-hour period.

```
A business starts in Tier 1 when it registers its phone number.
```
## Moving Tiers
You are automatically upgraded to a higher tier based on the volume and quality of the messages you send. Conversely, you can be downgraded if more of your messages are reported or blocked by users.

### Upgrades
A business’s phone number is upgraded to the next tier if:

    * Its quality rating is not low, and
    * The cumulative amount of users it sends notifications to adds up to twice its current messaging limit within a 7-day period.
 
Once the business reaches this threshold, it is moved to the next tier. The minimum amount of time that this upgrade can occur is after 48 hours, when the business is sending messages up to their current limit every day.

### Flagged Status

If a business has a Flagged status, it cannot upgrade tiers. After a business is Flagged, it must return to the Connected status and then restart the process to upgrade to the next tier.

If your business has a "Flagged" status and the quality rating doesn't improve, you will be placed in a lower messaging limit tier. See more information about the "Flagged"

### Examples

See the charts below for examples of how a business might move to the next tier:

**Example 1:** A business is upgraded from Tier 1 to Tier 2 when it messages a total of 2,000 users within a 7-day period.

![image](https://user-images.githubusercontent.com/96904835/148518557-54a71a25-f2a6-4427-8fd9-2bcf082cc0e3.png)

**Example 2:** The chart explains the concept of messaging limit in a rolling 24-hour window.

![image](https://user-images.githubusercontent.com/96904835/148518744-2de972ad-c032-4fec-893c-779f9b31f497.png)

### Before Deploying a New Number

Messaging limits determine how many unique users your business can send messages to, on a daily basis, and it takes at least 7 days for the new number to reach the last tier.

You should always analyze phone number quality before sending notifications to twice the current tier reach, so you guarantee you can move to the next tier in a healthy way. This is an opportunity for business to test with a smaller database to see how customers see this new communication channel you are creating.

![image](https://user-images.githubusercontent.com/96904835/148518946-84238f7c-5a4c-4ad8-8026-68d698c3ff3f.png)

