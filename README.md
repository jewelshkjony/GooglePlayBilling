# GooglePlayBilling - InAppBilling Extension
An in-app-billing extension to monetize your app products using google play store billing library 7.0.0.

**Reminder:** Starting on August 2, 2023, all new apps must use Billing Library version 5 or newer. By November 1, 2023, all updates to existing apps must use Billing Library version 5 or newer. [Learn more](https://developer.android.com/google/play/billing/deprecation-faq).

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/aix.png"/>

## Start Connection
You must use this function to starts up BillingClient setup process asynchronously.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/start-connection.png"/>

<b>BillingServiceConnected:</b> Sdk is ready run any billing operation.\
<b>BillingServiceDisconnected:</b> Sdk is disconnected from billing service.

## Billing Service Error
This event will be triggered when the extension got any error while doing any billing operation.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/billing-service-error.png"/>

<li> <b>function Name</b> → It’s return the name of function which got error.
<li> <b>error</b> → It’s return the error message as string.

## End Connection
Closes the connection and releases all held resources such as service connections.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/end-connection.png"/>

## Is Ready
Checks if the client is currently connected to the service, so that requests to other methods will succeed.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/is-ready.png"/>

## Is Subscription Supported
If feature is not supported then return false.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/is-subscription-supported.png"/>

## Product Type

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/product-type.png"/>

## Show In App Messages
If you've enabled in-app messaging, Google Play will show users messaging during grace period and account hold once per day and provide them an opportunity to fix their payment without leaving the app. We recommend that you call this API whenever the user opens the app to determine whether the message should be shown. If the user successfully recovered their subscription, you will receive purchase token. You should then use this purchase token to call the Google Play Developer API and refresh the subscription status in your app.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/in-app-message-demo.jpg"/>

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/show-in-app-message.png"/>

The subscription status changed. For example, a subscription has been recovered from a suspend state. Developers should expect the purchase token to be returned with this response code and use the purchase token with the Google Play Developer API.

<li> <b>purchaseToken</b> → It’s return the purchase token as string.
<li> <b>response Code</b> → It’s return the response code as integer.

## Get Product Details
Performs a network query the details of products available for sale in your app. Watch demo block for better understanding.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/get-product-details.png"/>

<li> <b>name</b> → It’s return the name of product as string.
<li> <b>title</b> → It’s return the title of product as string.
<li> <b>product Id</b> → It’s return the given product id string.
<li> <b>productType</b> → It’s return the type of product string.
<li> <b>description</b> → It’s return the description of product as string.
<li> <b>price</b> → It’s return the formatted price of product as string.
<li> <b>productDetails</b> → It’s return the object of ProductDetails.
<li> <b>response Code</b> → It’s return the response code as integer.
<li> <b>reason</b> → It’s return the reason for error as string.
<li> <b>message</b> → It’s return the details error message as string.

## Get Multiple Product Details
Performs a network query the details of products available for sale in your app. Set productIds and productTypes as list. Watch demo block for better understanding.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/get-multiple-product-details.png"/>

<li> <b>names</b> → It’s return the names of products as list of string.
<li> <b>titles</b> → It’s return the titles of product as list of string.
<li> <b>productIds</b> → It’s return the given products ids list of string.
<li> <b>productTypes</b> → It’s return the types of products list of string.
<li> <b>descriptions</b> → It’s return the descriptions of products as list of string.
<li> <b>prices</b> → It’s return the formatted price of product as list of string.
<li> <b>productDetailsList</b> → It’s return the objects of ProductDetails as list.
<li> <b>response Code</b> → It’s return the response code as integer.
<li> <b>reason</b> → It’s return the reason for error as string.
<li> <b>message</b> → It’s return the details error message as string.
  
## Get Offer Token
You can get <b>productDetails</b> from <b>GotProductDetails</b> event.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/get-offer-token.png"/>

## Launch Billing Flow
Initiates the billing flow for an in-app purchase or subscription. You can get <b>productDetails</b> from <b>GotProductDetails</b> event.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/launch-billing-flow.png"/>

<li> <b>purchase</b> → It’s return the object of Purchase. Use this purchase object to Consume or Acknowledge this purchase.
<li> <b>response Code</b> → It’s return the response code as integer.
<li> <b>reason</b> → It’s return the reason for error as string.
<li> <b>message</b> → It’s return the details error message as string.

## Launch Billing Flow With
Initiates the billing flow for an in-app purchase or subscription.
You can get <b>productDetails</b> from <b>GotProductDetails</b> event.

<b>isOfferPersonalized:</b> The Google Play purchase screen indicating that the price was customized for the user.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/launch-billing-flow-with.png"/>

<li> <b>purchase</b> → It’s return the object of Purchase. Use this purchase object to Consume or Acknowledge this purchase.
<li> <b>response Code</b> → It’s return the response code as integer.
<li> <b>reason</b> → It’s return the reason for error as string.
<li> <b>message</b> → It’s return the details error message as string.

## Launch Bundle Billing Flow
Initiates the billing flow for bundle of in-app purchase or subscription.
You can get <b>productDetailsList</b> from <b>GotMultipleProductDetails</b> event.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/launch-bundle-billing-flow.png"/>

<li> <b>purchase</b> → It’s return the object of Purchase. Use this purchase object to Consume or Acknowledge this purchase.
<li> <b>response Code</b> → It’s return the response code as integer.
<li> <b>reason</b> → It’s return the reason for error as string.
<li> <b>message</b> → It’s return the details error message as string.

<br>

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/Bundle%20Billing%20Flow%20Demo.jpg"/>
  
## 🔁 Launch Subscription Update Flow
Update purchase flow for in-app subscription product to update it’s billing cycle or launch for price change. You need to set the old purchase token to update the product with new prices. You can store the old purchase token locally or into your own server for later use.
  
![image](https://github.com/jewelshkjony/GooglePlayBilling/assets/75406851/0377c963-f416-4f23-a92f-132bd11dfaac)

## 💸 User Selected Alternative Billing
  
![image](https://github.com/jewelshkjony/GooglePlayBilling/assets/75406851/62ab76d6-9e29-4242-b545-2f83a8a066ce)

This event will be triggered when South Korean user select alternative billing option during payment time.\
Method to allow users in South Korea to select an alternative billing option.\
Enables the ability for users to select an alternative billing option during the purchase flow.
  
![image](https://github.com/jewelshkjony/GooglePlayBilling/assets/75406851/b57402ff-2b67-4e65-9a5a-355f30ab3a39)

## Get Purchase Details
Get <b>purchase</b> object from <b>GotPurchase</b> event.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/get-purchase-details.png"/>

<li> <b>orderId</b> → It’s return the order id from the purchase as string.
<li> <b>isAcknowledge</b> → It’s return true if the purchase is acknowledged, otherwise false.
<li> <b>isAutoRenewing</b> → It’s return true if product is auto renewable.
<li> <b>purchaseTime</b> → It’s return the time of purchase as long.
<li> <b>purchaseToken</b> → It’s return the purchase token as string.
<li> <b>json</b> → It’s return the json of the purchase object as string.

## Consume
For consumables, this method fulfills the acknowledgement requirement and indicates that your app has granted entitlement to the user. This method also enables your app to make the one-time product available for purchase again.
Get <b>purchase</b> object from <b>GotPurchase</b> event.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/consume.png"/>

<li> <b>token</b> → It’s return the purchase token as string.
<li> <b>response Code</b> → It’s return the response code as integer.
<li> <b>reason</b> → It’s return the reason for error as string.
<li> <b>message</b> → It’s return the details error message as string.

## Consume With
For consumables, this method fulfills the acknowledgement requirement and indicates that your app has granted entitlement to the user. This method also enables your app to make the one-time product available for purchase again. Use purchase token to consume the purchase. Get <b>purchaseToken</b> from <b>GotPurchaseDetails</b> event.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/consume-with.png"/>

<li> <b>token</b> → It’s return the purchase token as string.
<li> <b>response Code</b> → It’s return the response code as integer.
<li> <b>reason</b> → It’s return the reason for error as string.
<li> <b>message</b> → It’s return the details error message as string.

## Acknowledge
To acknowledge non-consumable purchases, use this function.
Get <b>purchase</b> object from <b>GotPurchase</b> event.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/acknowledge.png"/>

<li> <b>token</b> → It’s return the purchase token as string.
<li> <b>response Code</b> → It’s return the response code as integer.
<li> <b>reason</b> → It’s return the reason for error as string.
<li> <b>message</b> → It’s return the details error message as string.

## Acknowledge With
To acknowledge non-consumable purchases, use this function. Use purchase token to acknowledge the purchase. Get <b>purchaseToken</b> from <b>GotPurchaseDetails</b> event.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/acknowledge-with.png"/>

<li> <b>token</b> → It’s return the purchase token as string.
<li> <b>response Code</b> → It’s return the response code as integer.
<li> <b>reason</b> → It’s return the reason for error as string.
<li> <b>message</b> → It’s return the details error message as string.

## Query Purchases
Fetch for a user’s subscription purchases. Returns only active subscriptions and non-consumed one-time purchases.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/query-purchases.png"/>

## Is Purchased
Get <b>purchasesList</b> from <b>QueryPurchasesSuccess</b> event.
Now you can check that product is purchased by user or not by product id. If user purchased the product then it will return true, otherwise false.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/is-purchased.png"/>

<li> <b>productIds</b> → It’s return products ids as list of string.
<li> <b>purchasesState</b> → It’s return purchases states as list of integer. (0 == UNSPECIFIED_STATE, 1 == PURCHASED and 2 == PENDING).
<li> <b>purchasesToken</b> → It’s return purchases token as list of string.
<li> <b>orderIds</b> → It’s return order ids as list of string.
<li> <b>purchasesList</b> → It’s return the purchase object as list.
<li> <b>size</b> → It’s return the size of list as integer.
<li> <b>response Code</b> → It’s return the response code as integer.
<li> <b>reason</b> → It’s return the reason for error as string.
<li> <b>message</b> → It’s return the details error message as string.

## Get Purchase History
Returns the most recent purchase made by the user for each product, even if that purchase is expired, canceled, or consumed.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/get-purchases-history.png"/>

<li> <b>quantities</b> → It’s return quantities of purchases of product as list of integer.
<li> <b>purchaseTimes</b> → It’s return purchase time as list of long.
<li> <b>developerPayloads</b> → It’s return developer payloads as list of string.
<li> <b>originalJsons</b> → It’s return json of purchase object as list of string.
<li> <b>purchaseTokens</b> → It’s return purchases token as list of string.
<li> <b>signatures</b> → It’s return signatures as list of string.
<li> <b>productIds</b> → It’s return products ids as list of string.
<li> <b>size</b> → It’s return the size of list as integer.
<li> <b>response Code</b> → It’s return the response code as integer.
<li> <b>reason</b> → It’s return the reason for error as string.
<li> <b>message</b> → It’s return the details error message as string.

<br>
<br>

## Implementation Guide Video **↓**

[![AdmobAds](http://img.youtube.com/vi/F0i_6fgmpJ4/0.jpg)](https://www.youtube.com/watch?v=F0i_6fgmpJ4&list=PLczFHGJFYQrmQZMn4DZvjSbWjMqvEO3OD)
  
* If you're facing any issues, please submit your issues here → <a href="https://github.com/jewelshkjony/GooglePlayBilling/issues">Submit Issues</a>

<details>
<summary><b>Testing & Live Videos</b></summary>

## Test Purchasing Video
https://user-images.githubusercontent.com/75406851/186835232-ceb0fd95-d7da-4cb9-aa93-731252f89602.mp4

<br>

## Live / Real Purchasing Video
https://user-images.githubusercontent.com/75406851/188348269-0fda606a-93b7-4633-bcca-55a933393561.mp4

<br>

## Purchases Statements

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/Purchases-history.jpeg"/>
</details>

<details>
<summary><b>Example blocks</b></summary>

This is very simple example blocks for using this extension.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/single-in-app-demo.png"/>

<br>
<br>

Getting multiple products in single request.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/multiple-in-app-demo.png"/>

<br>
<br>

Purchasing bundle of product using GetMultipleProductDetails and LaunchMultipleBillingFlow.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/blob/main/images/multiple-billing-flow-demo.png"/>
</details>
  
## ➤ Release Notes ↷

<details>
<summary><b>6.1.0</b></summary>

● Extension size increased 187 KB.

● Added 4 new functions and events.

● Added 1 new property.

</details>

* **

<details>
<summary><b>6.0.1</b></summary>

●  Update Play Billing Library to be compatible with Android 14.
</details>

* **

<details>
<summary><b>6.0.0</b></summary>

●  Replaced `ProrationMode` by `ReplacementMode`.

●  Removed order ID for `PENDING` purchases.\
<small>(Previously, the order ID would always be created even if the purchase was pending. Starting with version 6.0.0, an order ID will not be created for pending purchases, and for these purchases, the order ID will be populated after the purchase is moved to the `PURCHASED` state.)</small>

●  Added new network error response code.\
<small>(A new network error response code, `NETWORK_ERROR`, has been added starting with PBL version 6.0.0. This code is returned when an error occurs due to a network connection issue. These network connection errors were previously reported as `SERVICE_UNAVAILABLE`.)</small>

●  Added additional logging.\
<small>(The Play Billing Library 6 release includes additional logging, which provides insight into API usage (such as success and failure) and service connection issues. This information will be used to improve the performance of the Play Billing Library and provide better support for errors.)</small>

●  Extension size increased 139 KB.

●  To migrate from `V5` to `V6`\
<small>(I'll charge very small amount for the `MAJOR` update only. MINOR updates will be totally free for all migrated users.)</small>
</details>

* **

<details>
<summary><b>5.2.0</b></summary>

●  Extension size increased 149 KB.

●  Added method to allow users in South Korea to select an alternative billing option.
</details>

* **

<details>
<summary><b>5.1.0</b></summary>

●  Extension size increased 11 KB.

●  Added `GetOfferTokens` method.

●  Added `GetOfferIds` method.

●  Added `GetBasePlanIds` method.

●  Added `GetOfferTags` method.
</details>

* **

<details>
<summary><b>5.0.0</b></summary>

●  Introduced a new model for subscriptions, including new entities that enable you to create multiple offers for a single subscription product.

●  Added `isOfferPersonalized` method for EU personalized pricing disclosure requirements.

●  <del>`LaunchPriceChangeFlow`</del> has been deprecated and will be removed in a future release.

●  Removed <del>`setVrPurchaseFlow`</del>, which was previously used when instantiating a purchase flow. In previous versions, this method redirected the user to complete the purchase on their Android device. Once you remove this method, users will complete the purchase through the standard purchase flow.
</details>

## More Extensions

<a href="https://github.com/jewelshkjony?tab=repositories">See more extensions</a>

## Extension specifications:
<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/download.png"/> <a href="https://t.me/jewelshkjony/">com.jewel.googleplaybilling.aix</a> (567 KB) \
💰 <b>Price:</b> $12 USD\
⚙️ <b>SDK Version:</b> 7.0.0\
🌎 <b>Last amendment:</b> 01 July 2024\
⚖️ <b>License:</b> <a href="https://github.com/jewelshkjony/Extensions/blob/main/LICENSE.md#terms-and-conditions-for-the-extension" target="_blank">Terms & Conditions</a> \
🤝 <b>Supported builder:</b> <a href="https://www.kodular.io/">Kodular</a>, <a href="https://niotron.com/">Niotron</a>, <a href="https://appzard.com/">AppZard</a>, <a href="https://androidbuilder.in/">AndroidBuilder</a>, <a href="http://ai2.appinventor.mit.edu/">App Inventor</a> and it's other distributions.

## 📫 How to reach me ↓

<a href="https://discordapp.com/users/795698765959790632">Discord</a> | <a href="https://t.me/jewelshkjony">Telegram</a> | <a href="https://wa.me/8801775668913">WhatsApp</a> | <a href="https://fb.com/jewelshkjony">Facebook</a> | <a href="https://m.me/jewelshkjony">Messenger</a> | <a href="https://m.youtube.com/c/JewelShikderJony?sub_confirmation=1">Youtube</a>
