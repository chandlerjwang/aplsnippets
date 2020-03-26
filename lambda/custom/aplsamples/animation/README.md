# Animation
`AnimateItem` runs a fixed-duration animation sequence on one or more properties of a single component.

## Sample
Components support animating `opacity` and `transform` properties. The `from` value does not need to be specified for opacity, but it does need to be specified for transforms.

```JSON
{
  "type": "AnimateItem",
  "easing": "ease-in-out",
  "duration": 600,
  "componentId": "myFlyingComponent",
  "value": [
    {
      "property": "opacity",
      "to": 1
    },
    {
      "property": "transform",
      "from": [
        {
          "translateX": 200
        },
        {
          "rotate": 90
        }
      ],
      "to": [
        {
          "translateX": 0
        },
        {
          "rotate": 0
        }
      ]
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

    The event generated has the form:

    ```JSON
    {
      "event": {
        "source": {
          "type": "nameOfComponent",
          "handler": "Mount",
          "id": "id of the component",
          "uid": "Runtime-generated unique ID of the component",
          "value": null
        }
      }
    }
    ```

    The event type property is set to the name of the component; for example, `Frame`, `Container`, `TouchWrapper`, etc.

## References
Below are some useful resources to help you get started:

- [APL Authoring Tool](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-authoring-tool.html)
- [APL Standard Commands](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-standard-commands.html#animate_item_command)
- [AnimateItem](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-standard-commands.html#animate_item_command)