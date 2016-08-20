# esp8266-slack-webhook
A library for easily sending messages to [Slack Incoming Webhooks][WEBHOOK_DOCUMENTATION] using the ESP8266. 

## Requires the following additional libraries  

* ESP8266WiFi.h

## Examples  

`url` is the Slack Webhook Integration URL. See [here][WEBHOOK_DOCUMENTATION] for more information.  

The full webhook URL is something like `https://hooks.slack.com/../../12341234/`. In the example code, 
the URL has been broken apart into a `host` part (hooks.slack.com) and the trailing URL.   

The `fingerprint` variables is the SSL fingerprint 

```
/*--Slack connection information--*/
const char* host = "hooks.slack.com";
const char* fingerprint = "‎‎ab f0 5b a9 1a e0 ae 5f ce 32 2e 7c 66 67 49 ec dd 6d 6a 38";
String url = "/../../";

//Create a new webhook
SlackWebhook webhook(host, url, fingerprint);
```

## References  

[This][IOT_FOREST] article from IOTForest helped me get my SSL issues solved. Attempting to make the POST request
necessary for communicating with Slack's webhooks is not possible unless you can handle the SSL certi

[WEBHOOK_DOCUMENTATION]: https://api.slack.com/incoming-webhooks
[IOT_FOREST]: http://www.iotforest.com/2016/3/4/esp8266-arduino-feather-huzzah-using-slack-integration