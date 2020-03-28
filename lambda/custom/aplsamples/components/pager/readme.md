# APL AutoPage
The `AutoPage` command automatically progresses through a series of pages displayed in a [Pager](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-pager.html) component. The `AutoPage` command finishes after the last page has been displayed for the requested time period.

## Sample

```JSON
{
  "type": "AutoPage",
  "componentId": "pagerId",
  "delay": 500,
  "duration": 1000
}
```

The above example first pauses for 500 milliseconds (the `delay` property), then advances to the next page, pauses for 1000 milliseconds (the `duration` property), and continues advancing and pausing until the final pause has completed. For example, the`pagerId` component has 3 pages and initially displays page 1, then AutoPage does the following:

- Displays page 1 for 500ms while waiting to start.
- Changes to page 2 and pauses for 1000ms.
- Changes to page 3 and pauses for 1000ms.

At this point the command is complete, so the [Pager](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-pager.html) continues to display page 3 until another command or event causes a change.

## Tips/Notes

1. To play around with the `AutoPage` snippet, following the steps below:

    1. Open the [APL authoring tool](https://developer.amazon.com/alexa/console/ask/displays)

    1. Click on `Start from scratch` and go to the `APL` tab on the left handside.

    1. Copy/paste content in `document.json` into the editor.

1. A `Pager` component displays a series of components one at a time. Pagers are commonly used for displaying a time-ordered sequence of data items.

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
- [APL Frame](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-frame.html)
- [APL AutoPage](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-standard-commands.html#autopage-command)
- [APL Pager](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-pager.html)
- [APL Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-resources.html)
- [Alexa Styles and Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-styles-package.html)