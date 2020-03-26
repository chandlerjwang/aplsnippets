# APL Video
A video player shows an embedded video or series of videos to play. The embedded video player does not have any controls. Instead, the video player provides the events and commands necessary to build the controls for controlling the video player.

Skills that use the `Video` component must provide a way to pause the video content by voice and by the use of an on-screen button.

## Sample

```JSON
{
  "type": "Video",
  "source": URL,
  "autoplay": true
}
```

## Tips/Notes

1. To play around with the `Video` snippet, following the steps below:

    1. Open the [APL authoring tool](https://developer.amazon.com/alexa/console/ask/displays)

    1. Click on `Start from scratch` and go to the `APL` tab on the left handside.

    1. Copy/paste content in `document.json` into the editor.

1. Make sure to provide a way to control the video through APL media commands such as `PlayMedia` or `ControlMedia`. `ControlMedia` controls a media player to play, pause, change tracks, or perform some other common action.

    Here is an example of using `ControlMedia` command:

    ```JSON
    {
      "type": "Sequential",
      "commands": [
        {
          "type": "ControlMedia",
          "componentId": "videoPlayerId",
          "command": "play"
        },
        {
          "type": "SetValue",
          "property": "opacity",
          "value": 0
        },
        {
          "type": "SetValue",
          "property": "opacity",
          "componentId": "pauseButtonId",
          "value": 100
        }
      ]
    }
    ```

## References
Below are some useful resources to help you get started:

- [APL Authoring Tool](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-authoring-tool.html)
- [APL Video](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-video.html)
- [APL Media Commands](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-commands-media.html)
- [APL Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-resources.html)
- [Alexa Styles and Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-styles-package.html)