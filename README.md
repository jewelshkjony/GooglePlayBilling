# GooglePlayBilling - InAppBilling Extension
An in-app-billing extension to monetize your app products using google play store billing library 5.1.0.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/thumbnail.png"/>

**Reminder:** Starting on August 2, 2022, all new apps must use Billing Library version 4 or newer. By November 1, 2022, all updates to existing apps must use Billing Library version 4 or newer. [Learn more](https://developer.android.com/google/play/billing/deprecation-faq).

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/aix.png"/>

## Extension Properties
If <b>AutoConsume</b> enabled, then you don't need to consume manually for one time product. If <b>AutoAcknowledge</b> enabled then you don't need to acknowledge in app subscription product. If <b>AutoConsume</b> disabled and <b>AutoAcknowledge</b> enabled, then one time product will be acknowledged, and user can't but this agian. To make the one-time product available for purchase again, you've to enable <b>AutoConsume</b> or manually consume it.

<b>AutoConsume</b> only target one time product or in app purchase product.

<b>AutoAcknowledge</b> will target both types product if <b>AutoConsume</b> is disabled. If <b>AutoConsume</b> enabled then <b>AutoAcknowledge</b> only target in app subscriptions.

For better use, enable both. (Recommended)

<b>ConsumeSuccess</b> and <b>AcknowledgeSuccess</b> will be triggered after automatically consumed or acknowledged the purchase.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/property-1.png"/>

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/property-2.png"/>

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

## More Extensions

<a href="https://github.com/jewelshkjony?tab=repositories">See more extensions</a>

## Extension specifications:
<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/download.png"/> <a href="https://t.me/jewelshkjony/">com.jewel.googleplaybilling.aix</a> (183 KB) \
<b>Price:</b> $12 USD\
<b>SDK Version:</b> 5.1.0\
<b>Demo Apk:</b> <a href="https://play.google.com/store/apps/details?id=com.jewelshkjony.pay2me">Pay2Me</a> \
<b>Last amendment:</b> 17 November 2022\
<b>Supported builder:</b> <a href="https://www.kodular.io/">Kodular</a>, <a href="https://niotron.com/">Niotron</a>, <a href="https://appzard.com/">AppZard</a>, <a href="https://androidbuilder.in/">AndroidBuilder</a>, <a href="http://ai2.appinventor.mit.edu/">App Inventor</a> and it's other distributions.

## 📫 How to reach me ↓

<a href="https://t.me/jewelshkjony">Telegram</a> | <a href="https://wa.me/8801775668913">WhatsApp</a> | <a href="https://fb.com/jewelshkjony">Facebook</a> | <a href="https://m.me/jewelshkjony">Messenger</a> | <a href="https://m.youtube.com/c/JewelShikderJony?sub_confirmation=1">Youtube</a>

## 💲 Payment Methods ↓

❏ <a href="https://www.binance.me/en/activity/referral-entry/CPA?fromActivityPage=true&ref=CPA_0068YL77KV" target="_blank">Binance</a> | <a href="https://www.skrill.com/en/">Skrill</a> | <a href="https://wise.com/?sourceCurrency=USD&targetCurrency=BDT&sourceAmount=20" target="_blank">Wise</a> | <a href="https://play.google.com/store/apps/details?id=com.pyypl">Pyypl</a> | <a href="https://www.xoom.com/bangladesh/send-money" target="_blank">Xoom</a> | <a href="https://play.google.com/store/apps/details?id=com.jewelshkjony.pay2me">Pay2Me</a> (Global)

❏ <a href="https://bka.sh/next?c=signup&uuid=C1CC9JVT1" target="_blank">bkash</a> | <a href="https://play.google.com/store/apps/details?id=com.konasl.nagad">Nagad</a> | <a href="https://play.google.com/store/apps/details?id=com.dbbl.mbs.apps.main">Rocket</a> (Bangladesh)
