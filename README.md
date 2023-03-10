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

## Protect Data & Comply with Law

* You are responsible for and must secure all necessary notices, permissions, and consents to collect, use, and share people's content and information, including maintaining a published privacy policy, and otherwise complying with applicable law.
* Don't use any data obtained from us about a person you message within WhatsApp, other than the content of message threads, for any purpose other than as reasonably necessary to support messaging with that person.
* Don't share or ask people to share full length individual payment card numbers, financial account numbers, personal ID card numbers, or other sensitive identifiers.
* Don’t use WhatsApp for telemedicine or to send or request any health information, if applicable regulations prohibit distribution of such information to systems that do not meet heightened requirements to handle health information.
* You may not forward or otherwise share information from a customer chat with any other customer.

## Quality Rating

Your quality rating is based on how messages have been received by recipients over the past seven days and is weighted by recency. It is determined by a combination of quality signals from conversations between businesses and users. Examples include user feedback signals like blocks, reports and the reasons users provide when they block a business.

The phone number status, quality rating, and messaging limits for your WhatsApp business account are listed in the Phone Numbers tab in WhatsApp Manager.

![image](https://user-images.githubusercontent.com/96904835/148517205-0d2c147f-7494-4ec2-9ba1-47f7355448b6.png)

Your quality rating is a rating based on the recent messages that your customers have received over the past 7 days. This rating is determined by the feedback from your customers, such as the reason to block your phone number and other reporting issues.

You can find the quality rating below the Phone numbers tab in your Meta WhatsApp Manager. The Quality rating column displays the quality states, including:

* Green: High quality
* Yellow: Medium quality
* Red: Low quality
When the user blocks your business, they can select a block reason, including No longer needed, Didn’t sign up, Spam, Offensive messages or No reason.

If your quality rating is medium or low, you can hover over the rating in the WhatsApp Manager to view the insights into the block reasons if they're available. This can help your businesses understand the details around user block reasons, avoid continuing to send low quality templates and mitigate the risk of more customers blocking your phone number.

You can subscribe and be notified for the quality-related updates. You'll receive an email and a notification in Meta Business Manager when:

* A phone number’s status is changed to Flagged or when this Flagged Status is removed.
* There is a change to a phone number’s messaging limits.

You can find the quality rating over the past 30 days by clicking the icon in the Settings column. You can view the lowest quality score for the business on a given day, which will enable a better understanding of potential drivers over the past 30 days that may have caused the quality rating to decline or increase.

### Status changes
When the quality rating reaches low quality, your phone number quality rating changes to Low. If the phone number quality is Low and on track to be downgraded to a lower message tier, the phone number status changes to Flagged. When a phone number is Flagged, if the quality doesn't improve over 7 days, the status returns to Connected. However, the messaging limit will decrease to the next level. For example, the phone number that used to have the 100,000 messaging limit now has the 10,000 messaging limit.

* Connected: You can send outgoing messages within your set messaging limit.
* Flagged: This status occurs when the phone number’s quality rating changes to Low and is on track to be downgraded to a lower message tier. Businesses can't upgrade messaging limit tiers while the status is Flagged. If the quality rating:
      * Improves to a high or medium quality by the 7th day from when your status was changed to Flagged, the status will return to Connected and your              messaging limit tier will remain unaffected.
      * Does not improve to a high or medium quality by the 7th day from when your status was changed to Flagged, your status will return to                       Connected.            
However, your messaging limit will decrease to the next level.
If your quality rating reaches low quality, or your phone number status changes to Flagged or Restricted status, you'll receive an email and notification in Business Manager as a warning.

* Restricted: This status occurs when you reach your messaging limit, regardless of the quality rating. While the status is Restricted, you can’t send any outgoing messages until 24 hours have elapsed. You can still respond to any messages that customers initiate.

Note: If you are a business solution provider (BSP), pass this information to your clients so that they can proactively manage these warnings.


  ## Messaging Limits
  
Messaging limits determine the maximum number of business-initiated conversations you can initiate using each of your phone numbers in a rolling 24-hour period. A business-initiated conversation begins when the first template message is delivered to a customer and ends 24 hours later.

Business phone numbers without a connected status and an approved display name are limited to 250 business-initiated conversations in a rolling 24-hour period. This includes all business phone numbers of an unverified business, since these numbers cannot receive display name approval until the business is verified.

Business phone numbers with a connected status and approved display name can initiate conversations with the following number of unique customers in a rolling 24-hour period:

* 1K unique customer
* 10K unique customers
* 100K unique customers
* An unlimited number of unique customers

This amount starts at 1K unique customers and scales automatically based on phone number status, phone number quality rating, and how often the business initiates conversations with unique customers.

If you reach your messaging limit, you can initiate more conversations as soon as one or more active conversations end. For example:

![image](https://user-images.githubusercontent.com/96904835/224228750-5d92b2db-9dd0-4f3a-a7bf-0d7a7520b8ed.png)

### Checking Your Limit
You can check your current messaging limits in the WhatsApp Manager > Overview Dashboard > Insights tab:
![image](https://user-images.githubusercontent.com/96904835/224228846-9420ee42-ffed-4dd8-8c7c-0097843159be.png)

### Increasing Your Limit

Each time you initiate a new conversation with a unique customer we will determine if your limit should be increased. This determination is based on the following criteria:

* your phone number status is Connected
* your phone number quality rating is Medium or High 
*in the last 7 days you have initiated X or more conversations with unique customers, where X is your current messaging limit divided by 2



If you meet all conditions, we will increase your messaging limit by one level in 24 hours.

Examples
Messaging limit increased from 1K to 10K in 2 days:


![image](https://user-images.githubusercontent.com/96904835/224229112-8deccfc3-cf3b-4aa6-96ca-340ad615111a.png)

* If the 500th conversation is initiated at 3pm (for example), the messaging limit is increased at 3pm the following day (i.e. 24 hours later).

Messaging limit increased from 1K to 10K in 4 days:
![image](https://user-images.githubusercontent.com/96904835/224229199-5e4c22b0-0b94-4c36-ba62-0b351b86a73b.png)

* If the 500th conversation is initiated at 7pm (for example), the messaging limit is increased at 7pm the following day (i.e. 24 hours later).

### Decreasing Your Limit
Each time you initiate a new conversation with a unique customer we will check your phone number quality rating. If the rating has been Low for the last 7 days, we will immediately decrease your messaging limit by one level.
