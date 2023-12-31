# Next Carousel Slide

Fire whenever a user interacts with the next carousel slide control

## HTML Data Attributes

```html
<a href="<link_url>"
  data-layer-event="next_carousel_slide"
  data-layer-identifier="<identifier>"
  data-layer-name="<name>"
  data-layer-index="<index>"
  data-layer-target_index="<target_index>"
>
```

## Javascript Code

```js
// When:
// User interacts with 'next' carousel slide control

// Code:
window.dataLayer = window.dataLayer || [];
dataLayer.push({ event_data: null });  // Clear the previous event_data object.
dataLayer.push({
  event: "next_carousel_slide",
  event_data: {
    identifier: "<identifier>", // REQUIRED | string | ex. 12345abcde12345
    name: "<name>", // contextual | string | ex. Most Popular Blog Posts, Homepage Main Content	
    index: "<index>", // contextual | integer | ex. 1 | min. lgth. 1 | min. 1
    target_index: "<target_index>" // contextual | integer | ex. 2 | min. lgth. 1 | min. 1 
  }
});
```

## Variable Definitions

|Field|Type|Required|Description|Example|Minimum Length|Maximum Length|Minimum|
| --- | --- | --- | --- | --- | --- | --- | --- |
|identifier|string|required|The computer-readable machine name of the carousel. Use UUID provided by the component|`12345abcde12345`||`100`||
|name|string|contextual|The human-readable name of the carousel. If user does not input one, populate with numerical index of which carousel this is on the page (1-indexed)|`Most Popular Blog Posts`,`Homepage Main Content`||`100`||
|index|integer|contextual|The slide # the carousel is on at time of interaction (1-indexed)|`1`|`1`|`100`|`1`|
|target_index|integer|contextual|The slide # of the target slide (1-indexed)|`2`|`1`|`100`|`1`|
