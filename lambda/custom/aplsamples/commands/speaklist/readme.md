# APL SpeakList
`SpeakList` reads the contents of a range of items inside a common container. Each item will scroll into view before speech.

## Sample

```JSON
{
  "type": "SpeakList",
  "componentId": "SequenceForSpeakList",
  "count": 3,
  "start": 0,
  "align": "center"
}
```

This example reads 3 components out of the middle of a list and ensures that each aligns in the center of the screen.

## Tips/Notes

To play around with the `SpeakList` snippet, following the steps below:

  1. Open the [APL authoring tool](https://developer.amazon.com/alexa/console/ask/displays)

  1. Click on `Start from scratch` and go to the `APL` tab on the left handside.

  1. Copy/paste content in `document.json` into the editor.

We also need to load the [APL Data Source](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-data-source.html) that needs to bind to this APL document:

  1. Navigate to `aplsamples/datasources/animals_speaklist_shape.json` and copy/paste its content.

  1. In the authoring tool, click on the `DATA` tab on the left handside.

  1. Paste the content in `animals_speaklist_shape.json` into the editor.


## References
Below are some useful resources to help you get started:

- [APL Authoring Tool](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-authoring-tool.html)
- [APL SpeakList](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-standard-commands.html#speaklist-command)
- [Data Sources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-data-source.html)