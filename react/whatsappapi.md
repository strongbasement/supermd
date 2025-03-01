payload to send template


``` js
{
  "messaging_product": "whatsapp",
  "recipient_type": "individual",
  "to": "919345194790",           // Recipient phone number in international format
  "type": "template",             // Type of message (template)
  "template": {
    "name": "hello_world",        // The name of the approved template
    "language": {
      "code": "en_US"                // The language code (e.g., "en" for English)
    }
  }
}
```

after reply you can send normal messages to the customer

``` js
{
    "messaging_product": "whatsapp",    
    "recipient_type": "individual",
    "to": "919345194790",
    "type": "text",
    "text": {
        "preview_url": false,
        "body": "how are you"
    }
}



```