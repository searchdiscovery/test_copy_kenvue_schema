# Chat Start

Fire whenever a user initiates a chat session. 

## Javascript Code

```js
// When:
// User initiates a chat session

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: 'chat_start',
  event_data: {
    identifier: '<identifier>', // REQUIRED | string | ex. ecp_locator, free_trial
    name: '<name>', // REQUIRED | string | ex. ecp_locator, free_trial
    type: '<type>' // REQUIRED | string | ex. contact, lead_generation
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Maximum Length|
| --- | --- | --- | --- | --- | --- |
|identifier|string|required|The chat machine-readable name. This should be a unique value specific to this chat prompt, if one exists. If one does not exist, this can also be populated with the same value as the <name>.|`ecp_locator`, `free_trial`|`100`|
|name|string|required|The chat prompt human-readable name. This should be something that an analyst without a deep knowledge of the technical implementation of the site can easily identify the chat with. It should be lowercase snake_case.|`ecp_locator`, `free_trial`|`100`|
|type|string|required|The chat type. This will act as a filtering mechanism in reporting to enable analysts to view chat droppoff funnels. It can also act as an internal aid in firing additional events if necessary. For instance, lead-generating chats require a `generate_lead` event to be fired alongside `chat_complete`, and that could be written into the logic based upon this field.|`contact`, `lead_generation`|`100`|
