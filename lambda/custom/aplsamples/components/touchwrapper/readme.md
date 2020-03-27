# APL TouchWrapper
A `TouchWrapper` wraps a single child component and responds to touch events. TouchWrappers are commonly used in lists where each list item can be individually pressed.

## Sample

```JSON
{
  "type": "TouchWrapper",
  "width": "100%",
  "height": "50%",
  "item": {
    "type": "Image",
    "source": "https://aplsnippets.s3.amazonaws.com/assets/images/cat-round.png",
    "width": "100%",
    "height": "100%"
  },
  "onPress": [
    {
      "type": "SendEvent",
      "arguments": [ "argument one", "argument two" ]
    },
    {
      "type": "SetValue",
      "componentId": "operation",
      "property": "text",
      "value": "image press"
    }
  ]
}
```

In this case, the `Image`, when pressed, triggers a `SendEvent` and `SetValue` command which updates the value of `Text` component with id `"operation"` to `image press`.

## Tips/Notes

To play around with the `Video` snippet, following the steps below:

  1. Open the [APL authoring tool](https://developer.amazon.com/alexa/console/ask/displays)

  1. Click on `Start from scratch` and go to the `APL` tab on the left handside.

  1. Copy/paste content in `document.json` into the editor.


## References
Below are some useful resources to help you get started:

- [APL Authoring Tool](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-authoring-tool.html)
- [APL TouchWrapper](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-touchwrapper.html)
- [APL Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-resources.html)
- [Alexa Styles and Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-styles-package.html)