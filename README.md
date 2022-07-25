# GooglePlayBilling - InAppBilling Extension
An in-app-billing extension to monetize your app products using google play store billing library 5.0.0.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/GooglePlayBilling.jpg"/>

**Reminder:** Starting on August 2, 2022, all new apps must use Billing Library version 4 or newer. By November 1, 2022, all updates to existing apps must use Billing Library version 4 or newer. [Learn more](https://developer.android.com/google/play/billing/deprecation-faq).

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/aix.png"/>

## Start Connection
You must use this function to starts up BillingClient setup process asynchronously.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/start-connection.png"/>

<b>BillingServiceConnected:</b> Sdk is ready run any billing operation.\
<b>BillingServiceDisconnected:</b> Sdk is disconnected from billing service.

### Billing Service Error
This event will be triggered when the extension got any error while doing any billing operation.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/billing-service-error.png"/>

## End Connection
Closes the connection and releases all held resources such as service connections.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/end-connection.png"/>

## Is Ready
Checks if the client is currently connected to the service, so that requests to other methods will succeed.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/is-ready.png"/>

## Is Subscription Supported
If feature is not supported then return false.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/is-feature-supported.png"/>

## Product Type Property

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/property-block.png"/>

## Show In App Messages
If you've enabled in-app messaging, Google Play will show users messaging during grace period and account hold once per day and provide them an opportunity to fix their payment without leaving the app. We recommend that you call this API whenever the user opens the app to determine whether the message should be shown. If the user successfully recovered their subscription, you will receive purchase token. You should then use this purchase token to call the Google Play Developer API and refresh the subscription status in your app.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/in-app-message.png"/>

<li> InAppMessageResponse: The subscription status changed. For example, a subscription has been recovered from a suspend state. Developers should expect the purchase token to be returned with this response code and use the purchase token with the Google Play Developer API.

## Query Product Details
Performs a network query the details of products available for sale in your app. Set productIds and productTypes as list. Watch demo block for better understanding.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/query-product-details.png"/>

## Get Product Information
<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/get-product-property.png"/>

## Launch Purchase Flow
Initiates the billing flow for an in-app purchase or subscription.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/launch-billing-flow.png"/>

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/billing-flow-launch-example.png"/>

## Get Purchase Information
<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/get-purchase-property.png"/>

## Consume Purchase
For consumables, this method fulfills the acknowledgement requirement and indicates that your app has granted entitlement to the user. This method also enables your app to make the one-time product available for purchase again.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/consume-purchase.png"/>

## Acknowledge Purchase
To acknowledge non-consumable purchases, use this function.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/acknowledge-purchase.png"/>

## Query Purchases
Fetch for a user's subscription purchases. Returns only active subscriptions and non-consumed one-time purchases.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/query-purchases.png"/>

## Query Purchase History
Returns the most recent purchase made by the user for each product, even if that purchase is expired, canceled, or consumed.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/query-purchase-history.png"/>

## Example blocks
This is very simple example blocks for using this extension.

<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/example-blocks.png"/>

## Extension specifications:
<img src="https://github.com/jewelshkjony/GooglePlayBilling/raw/main/images/download.png"/> <a href="https://t.me/jewelshkjony/">com.jewel.googleplaybilling</a>(163 KB) \
<b>Version:</b> 5.0.0\
<b>Price:</b> 12 USD\
<b>Last amendment:</b> 25 July 2022\
<b>Supported builder:</b> <a href="https://www.kodular.io/">Kodular</a>, <a href="https://niotron.com/">Niotron</a>, <a href="https://appzard.com/">AppZard</a>, <a href="https://androidbuilder.in/">AndroidBuilder</a>, <a href="http://ai2.appinventor.mit.edu/">App Inventor</a> and it's other distributions.

## 📫 How to reach me -

<a href="https://t.me/jewelshkjony">Telegram</a> | <a href="https://wa.me/8801775668913">WhatsApp</a> | <a href="https://fb.com/jewelshkjony">Facebook</a> | <a href="https://m.me/jewelshkjony">Messenger</a> | <a href="https://m.youtube.com/c/JewelShikderJony">Youtube</a>

## Global Payment Method
<a href="https://www.xoom.com/bangladesh/send-money">Xoom</a> | <a href="https://wise.com/">TansferWise (Wise)</a> | <a href="http://share.payoneer.com/nav/kJkLyppKLt-FTUg-P9xnUd76yT4iWQiym2irI42PLM7uQWXuVsWvSOABMvVykU5hbFiDGSULXNdI3-yRM7JVhA2">Payoneer</a>

### Bangladeshi Payment Method
Bangladeshi user can send money using <a href="https://bka.sh/next?c=signup&uuid=C1CC9JVT1">bkash</a> | <a href="https://play.google.com/store/apps/details?id=com.konasl.nagad">Nagad</a> | <a href="https://play.google.com/store/apps/details?id=com.dbbl.mbs.apps.main">Rocket</a>.
Use this phone number to send money.

````java
+8801775668913
````

Remember accounts are personal, so you've to use send money option.
