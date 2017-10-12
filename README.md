# SMS Link To All App Store using twilio for SMS

How to create a basic SMS app that send links of your mobile app to all app store, ios, android...

The beauty of this, is that you don't even need to write any code ;-)

1) Setup your redirect to your apps from each store, iOS, Android... You have few options on how to do this
a) You can levrage some free online tool like http://onelink.to/, they give you a short URL that will take care of the redirect.
b) you can host on your web site or AWS S3 a basic html page that will do the redirect, I provided a basic example in my repo "LocalAppRedirect.html"

2) Create an account on Twilio and by a number
3) In Twilio, go create your TwiML Bin with the basic HTML text that will reply the following message when you recive a text, note the link to onelink, if you chose to host your own HTML then this would be the link to your html file.
```<?xml version="1.0" encoding="UTF-8"?>
<Response>
<Message>
Download our free Facebook app today http://onelink.to/xbkjnt
</Message>
</Response>
```
4) configure your twilio number to execute the TwiML Bin when reciving a text.

Note:
If you are planning to use a shortcode, you will have to implement STOP/START/HELP
https://support.twilio.com/hc/en-us/articles/223182208-Industry-standards-for-U-S-short-code-HELP-and-STOP

Eric Thibeault
