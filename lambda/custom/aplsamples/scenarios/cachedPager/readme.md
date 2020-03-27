# APL UserEvent
Alexa sends your skill an `Alexa.Presentation.APL.UserEvent` request when an event on the device triggers the `SendEvent` command. This lets your skill service receive messages in response to the user's actions on the device. You can use event handlers on components in your document to trigger `SendEvent`.

## Sample
Use the `SendEvent` command to generate and send an event to Alexa. The `SendEvent` command sends a `UserEvent` request to your skill.

```JSON
{
  "type": "AlexaButton",
  "buttonText": " previous ",
  "buttonStyle": "outlined",
  "position": "contained",
  "width": "15vw",
  "id": "previousButtonId",
  "left": "1vw",
  "top": 0,
  "primaryAction": {
    "type": "SendEvent",
    "componentId": "previousButtonId",
    "arguments": [ "Cached_Pager_Previous" ]
  }
}

```

In this case, the `SendEvent` command is executed on the `primaryAction` handler of a `AlexaButton`.

Next, the `SendEvent` command sends the skill an `Alexa.Presentation.APL.UserEvent` request like the one below:

```JSON
{
  "type": "Alexa.Presentation.APL.UserEvent",
  "requestId": "amzn1.echo-api.request.1",
  "timestamp": "2020-01-20T22:28:44Z",
  "locale": "en-US",
  "arguments": [
    "Cached_Pager_Previous"
  ],
  "components": {},
  "source": {
    "type": "AlexaButton",
    "handler": "primaryAction",
    "id": "previousButtonId"
  }
}
```

This `UserEvent` above includes the following information defined in the `SendEvent` command:

- The `arguments` property contains an array containing the data passed to the `arguments` array of the `SendEvent` command.
- The `source` property includes details about the component that triggered the event. In this example, this is the `AlexaButton`.

See [UserEvent request](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-interface.html#userevent-request) for more details about the `UserEvent` request.



## Tips/Notes

- To play around with the `cachedPager` snippet, following the steps below:

    1. Open the [APL authoring tool](https://developer.amazon.com/alexa/console/ask/displays)

    1. Click on `Start from scratch` and go to the `APL` tab on the left handside.

    1. Copy/paste content in `document.json` into the editor.

    ***Note***: `SendEvent` command do not work in the authoring tool. Test your document in the [simulator](https://developer.amazon.com/en-US/docs/alexa/devconsole/test-your-skill.html#test-simulator) or an actual device to see the results of the `SendEvent`.

- In the `aplsnippets/lambda/custom/index.js` file, the code snippet that handles the `UserEvent` request is:

  ```JAVASCRIPT
  const UserEventHandler = {
    canHandle(handlerInput) {
      return handlerInput.requestEnvelope.request.type === 'Alexa.Presentation.APL.UserEvent';
    },
    async handle(handlerInput) {
      return Skill.handleUserEvent(handlerInput);
    },
  };
  ```

- A `Pager` component displays a series of components one at a time. Pagers are commonly used for displaying a time-ordered sequence of data items.

    Below is an example of using `Pager` component to nest a series of `Text`, `Image`, and `Frame` components:

    ```JSON
      {
        "type": "Pager",
        "id": "pagerId",
        "items": [
          {
            "type": "Text",
            "text": "Text content shown on page #1"
          },
          {
            "type": "Container",
            "width": "100vw",
            "height": "100vh",
            "items": [
              {
                "type": "Image",
                "source": "https://aplsnippets.s3.amazonaws.com/assets/images/dog01_1200.jpg",
                "position": "absolute"
              },
              {
                "type": "Text",
                "text": "page #2",
              }
            ]
          },
          {
            "type": "Frame",
            "width": "100vw",
            "height": "100vh",
            "backgroundColor": "navy",
            "borderColor": "yellow",
            "borderWidth": 20,
            "borderRadius": 100,
            "borderBottomRightRadius": 250,
            "item": {
              "type": "Text",
              "text": "Page #3: Padded text in a frame with differnet border radii",
            }
          }
        ]
      }
    ```


## References
Below are some useful resources to help you get started:

- [APL Authoring Tool](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-authoring-tool.html)
- [Alexa Simulator/Developer Console](https://developer.amazon.com/en-US/docs/alexa/devconsole/test-your-skill.html#test-simulator)
- [APL Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-resources.html)
- [Alexa Styles and Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-styles-package.html)
- [APL Frame](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-frame.html)
- [APL Pager](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-pager.html)
- [APL SendEvent](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-standard-commands.html#sendevent-command)
- [APL UserEvent](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-interface.html#userevent-request)
- [APL AlexaButton](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-button-layout.html)