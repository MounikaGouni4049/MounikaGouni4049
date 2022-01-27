# IOS Push Certificates

## Why moving from .P12 to .P8 Based Authanitcation

### Generating push certificate can be a painful process, especially when the push notification provider / library requires a .pem file, which require extra steps to generate. Sometimes you might not even able to export the required .p12 file due to lost of key, or mixed up development / production environment certificate and unable to send push notification to Testflight / App Store. Worse, push certificates typically expires in 1 year and you have to renew it in Apple developer center and reupload the new certificate to your push provider every year, if you have 5 apps, then you have do this process 5 times every year!
### In 2016 WWDC, Apple introduced a new authentication format for sending push notification. The new format is a .p8 key file, it works for all your apps (ie. 1 key file can send push notification to all of your apps), works in both development and production environment (no need to switch between certificates), and best of all, it doesn’t expire!
### Hence it will be only one key for all enviromwnets (dev, Uat1,Uat2,Prod,.. etc)

## Generating .p8 Key file:
####   1. Go to Apple developer account page(https://developer.apple.com)
####   2. Select Certificates, IDs & Profiles, and navigate to Keys
    ![SelectKey](~/images/2-selectKey-1.png "Select Key")
####   3.Click the “+” button to add a new key.
    ![NewKey](/images/3-addKey-1.png "Add Key")
####   4. In the new key page, type in your key name and check the Apple Push Notification service (APNs) box , then click “Continue” and click “Register’.
    ![RegisterKey](/images/4-registerKey-1.png "Register Key")
####  5.Then proceed to download the key file by clicking Download
    ![DownloadKey](/images/5-downloadKey-1.png "Download Key")


####   The Auth Key filename will look like this : AuthKey_4CLK6FN46Q.p8 the 4CLK6FN46Q is the Key ID 

####  * SigningKey:Texas by Texas APNS key
####  * Signing Key ID:4CLK6FN46Q
####  * TeamID: YQS9HS5MTQ
## BundleID for corsponding enviroment 
####  * BundleID Prod: gov.texas.dir.txt
####  * BundleID UAT1 : gov.texas.dir.txt.uat1
####  * BundleID UAT2 : gov.texas.dir.txt.uat2
####  * BundleID Dev1 : gov.texas.dir.txt.dev1
####  * BundleID Dev2 : gov.texas.dir.txt.dev2
####  * BundleID Dev3 : gov.texas.dir.txt.dev3
####  * BundleID Stage : gov.texas.dir.txt.stage

 
