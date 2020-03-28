# Animation
`AnimateItem` runs a fixed-duration animation sequence on one or more properties of a single component.

## Sample
`AnimateItem` supports animating `opacity` and `transform` properties.

```JSON
{
  "type": "AnimateItem",
  "easing": "ease-in-out",
  "duration": 2900,
  "componentId": "animationId1",
  "value": [
    {
      "property": "opacity",
      "from": 0,
      "to": 1
    },
    {
      "property": "transform",
      "from": [ { "translateX": -1000 } ],
      "to": [ { "translateX": 0 } ]
    }
  ]
}
```

## Tips/Notes

1. To play around with the `AnimateItem` snippet, following the steps below:

    1. Open the [APL authoring tool](https://developer.amazon.com/alexa/console/ask/displays)

    1. Click on `Start from scratch` and go to the `APL` tab on the left handside.

    1. Copy/paste content in `document.json` into the editor.

1. The `onMount` command is triggered at document load time. Component `onMount` commands are always executed even if the component itself is invisible or otherwise not displayed on the screen.

## References
Below are some useful resources to help you get started:

- [APL Authoring Tool](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-authoring-tool.html)
- [APL Standard Commands](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-standard-commands.html#animate_item_command)
- [AnimateItem](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-standard-commands.html#animate_item_command)