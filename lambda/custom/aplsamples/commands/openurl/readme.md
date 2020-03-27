# APL OpenURL
Open a URL. The `OpenURL` command, if successful, opens the specified URL in a web browser or other application on the device. You must provide a suitable URL that works on the current device.

## Sample

```JSON
{
  "type": "OpenURL",
  "source": "https://www.amazon.com",
  "delay": 8000,
  "onFail": {
    "type": "SetValue",
    "componentId": "errorId",
    "property": "text",
    "value": "Unable to open Amazon shopping (${event.source.value})"
  }
}
```

In this case, we open the Amazon home page in the browser on the device. The `onFail` property will execute if the URL fails to open.

## Tips/Notes

1. To play around with the `OpenURL` snippet, following the steps below:

    1. Open the [APL authoring tool](https://developer.amazon.com/alexa/console/ask/displays)

    1. Click on `Start from scratch` and go to the `APL` tab on the left handside.

    1. Copy/paste content in `document.json` into the editor.

1. Not all devices support opening a URL. If the device does not support opening URLs, the command is ignored and it does not run `onFail` commands. Check the value of the [allowOpenURL](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-data-binding-evaluation.html#allowopenurl) in the `data-binding context` to determine if OpenURL is supported on the device.


## References
Below are some useful resources to help you get started:

- [APL Authoring Tool](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-authoring-tool.html)
- [APL OpenURL](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-standard-commands.html#open_url_command)
- [APL Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-resources.html)
- [Alexa Styles and Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-styles-package.html)