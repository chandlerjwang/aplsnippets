# APL SpeakList
`SpeakList` reads the contents of a range of items inside a common container. Each item will scroll into view before speech. Each item should have a speech property, but it is not required.

## Sample

```JSON
{
  "type": "SpeakList",
  "componentId": "movieList",
  "start": 3,
  "count": 3,
  "minimumDwellTime": 700,
  "align": "center"
}
```

This example reads 3 components out of the middle of a list and ensures that each aligns in the center of the screen.

The `minimumDwellTime` prevents items with short titles from being read too quickly. For example, a series of movie titles like "Venom", "Fences", and "Dear Zachary: A Letter to a Son About His Father" needs some dwell time for the first two items.

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
- [APL Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-resources.html)
- [Alexa Styles and Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-styles-package.html)
- [Data Sources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-data-source.html)
- [Transformers](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-transformers.html)