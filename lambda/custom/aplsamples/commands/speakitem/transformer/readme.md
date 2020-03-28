# APL Transformers
Transformers convert data in a data source into alternative representations. You can include an array of transformer objects in the `transformers` property of an [object data source](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-data-source.html#object-datasource).

## Sample

The `object` data source type adds properties required for [transformers](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-transformers.html). You use transformers to manipulate the data.

The example below shows the `single` data source with data in the `properties` object. The data source also has the `ssmlToSpeech` transformer and `ssmlToText` transformer. The transformer references data within the `properties` object.

Data source file: `aplsamples/datasources/singleanimal.json`:
```JSON
{
  "single": {
    "name": "Fluffy",
    "imageSource": "https://aplsnippets.s3.amazonaws.com/assets/images/cat01_1200.jpg",

    "properties": {
      "transformerSourceName": "<speak> My name is fluffy. Mr Fluffy, the cat! </speak>"
    },
    "transformers": [
      {
        "inputPath": "transformerSourceName",
        "outputName": "nameAsSpeech",
        "transformer": "ssmlToSpeech"
      },
      {
        "inputPath": "transformerSourceName",
        "outputName": "nameAsText",
        "transformer": "ssmlToText"
      }
    ]
  }
}

```

Now in `document.json`, you can bind `speech` as `${payload.single.properties.nameAsSpeech}` and `text` as `${payload.single.properties.nameAsText}` since those values are stored as `outputName`.

## Tips/Notes

To play around with the `Transformers` snippet, following the steps below:

  1. Open the [APL authoring tool](https://developer.amazon.com/alexa/console/ask/displays)

  1. Click on `Start from scratch` and go to the `APL` tab on the left handside.

  1. Copy/paste content in `document.json` into the editor.

We also need to load the [APL Data Source](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-data-source.html) that needs to bind to this APL document:

  1. Navigate to `aplsamples/datasources/singleanimal.json` and copy/paste its content.

  1. In the authoring tool, click on the `DATA` tab on the left handside.

  1. Paste the content in `singleanimal.json` into the editor.

## Available Transformers

There are four available transformers:

- `ssmlToSpeech`: Converts the input Speech Synthesis Markup Language (SSML) into speech you can bind to the `speech` property of an APL component. The speech associated with the component can then be spoken using a `SpeakItem` APL command. The use of the audio tag with the `ssmlToSpeech` transformer is not supported. The text passed to this transformer must be valid SSML enclosed within `<speak> `tags.

- `ssmlToText`: Converts the input SSML to plain text.

- `textToHint`: Converts the input to a hint with the correct user-configured wake word for the device (Try "Alexa, This is the hint"). Users can choose the wake word for their devices, so avoid hard-coding the word "Alexa" in your hint.

- `textToSpeech`: Converts the input plain text into `speech` you can bind to the speech property of an APL component. The speech associated with the component can then be spoken using a `SpeakItem` APL command.


***Note***: Transformers do not work in the authoring tool. Test your document in the [simulator](https://developer.amazon.com/en-US/docs/alexa/devconsole/test-your-skill.html#test-simulator) or an actual device to see the results of the transformer.


## References
Below are some useful resources to help you get started:

- [APL Authoring Tool](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-authoring-tool.html)
- [Alexa Simulator/Developer Console](https://developer.amazon.com/en-US/docs/alexa/devconsole/test-your-skill.html#test-simulator)
- [APL Transformers](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-transformers.html)
- [APL Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-resources.html)
- [Alexa Styles and Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-styles-package.html)
- [Data Sources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-data-source.html)