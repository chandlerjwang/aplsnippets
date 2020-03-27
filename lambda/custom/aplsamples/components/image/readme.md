# APL Image
An `Image` is a component that draws a bitmap image on the screen. Do not use animated .gif files in your skills. Although these images may appear animated in the simulator, their behavior on screen devices with Alexa may be different.

## Sample

```JSON
{
  "type": "Image",
  "source": "http://images.example.com/image/foo.png",
  "scale": "fill",
  "width": 300,
  "height": 300
}
```

In this case, the image will fill a 300x300 box on the screen.

## Tips/Notes

1. To play around with the `Video` snippet, following the steps below:

    1. Open the [APL authoring tool](https://developer.amazon.com/alexa/console/ask/displays)

    1. Click on `Start from scratch` and go to the `APL` tab on the left handside.

    1. Copy/paste content in `document.json` into the editor.

1. A `Frame` component holds a single child and has a border and background color.

    Here is an example of using `Frame` component to nest `Image`:

    ```JSON
    {
      "type": "Frame",
      "position": "absolute",
      "left": 0,
      "top": 0,
      "width": "50%",
      "height": "50%",
      "item": {
        "type": "Image",
        "source": "https://aplsnippets.s3.amazonaws.com/assets/images/cat01_1200.jpg",
        "width": "100%",
        "height": "100%",
        "borderRadius": 200
      }
    }
    ```

## References
Below are some useful resources to help you get started:

- [APL Authoring Tool](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-authoring-tool.html)
- [APL Frame](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-frame.html)
- [APL Image](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-image.html)
- [APL Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-resources.html)
- [Alexa Styles and Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-styles-package.html)