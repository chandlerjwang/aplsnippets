# APL SpeakItem
The `SpeakItem` command reads the contents of a single item on the screen. The item will scroll into view if it is not currently visible. Any type of component can be the recipient of `SpeakItem`.

## Sample

```JSON
{
  "type": "Container",
  "width": "100vw",
  "height": "100vh",
  "items": [
    {
      "type": "Image",
      "id": "introImage",
      "source": "https://aplsnippets.s3.amazonaws.com/assets/images/cat-round.png",
      "scale": "best-fill",
      "position": "absolute",
      "width": "100vw",
      "height": "100vh",
      "speech": "https://aplsnippets.s3.amazonaws.com/assets/audio/cat01.mp3"
    }
  ],
  "onMount": [
    {
      "type": "SpeakItem",
      "componentId": "introImage"
    }
  ]
}
```

In this case, the `SpeakItem` command is executed on the `Image` component with `id equals introImage`, which results the image of a cat is displayed while the audio file is being played.

## Tips/Notes

1. To play around with the `SpeakItem` snippet, following the steps below:

    1. Open the [APL authoring tool](https://developer.amazon.com/alexa/console/ask/displays)

    1. Click on `Start from scratch` and go to the `APL` tab on the left handside.

    1. Copy/paste content in `document.json` into the editor.

1. Note these restrictions:

    - The `SpeakItem` command does not scroll the content during speech in `block` mode. For example, if the component is larger than the scrolling container of the component, those parts of the component that are not visible after scrolling will remain hidden.

    - Components on round screens should use center alignment, or much of the content will not be visible.

    - `SpeakItem` does not highlight individual words or lines of text during speech when `highlightMode` is block.

    - The algorithm used to scroll the item into view assumes there is only a single scrolling component. Nested scrolling components are not supported.

    - Components without a `speech` property will still scroll into view.

    - When a `SpeakItem` command is terminated early, it clears any visual changes and stops speech immediately.

    - The `SpeakItem` command is ignored in fast mode.


## References
Below are some useful resources to help you get started:

- [APL Authoring Tool](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-authoring-tool.html)
- [APL SpeakItem](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-standard-commands.html#speakitem-command)
- [APL Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-resources.html)
- [Alexa Styles and Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-styles-package.html)