# APL Text
The `Text` component displays text in either a single line or multiple lines.

## Sample

```JSON
{
  "type": "Text",
  "text": "centered text",
  "textAlign": "center",
  "spacing": "@topPaddingBetweenElements",
}
```

## Tips/Notes

1. To play around with the `Text` snippet, following the steps below:

    1. Open the [APL authoring tool](https://developer.amazon.com/alexa/console/ask/displays)

    1. Click on `Start from scratch` and go to the `APL` tab on the left handside.

    1. Copy/paste content in `document.json` into the editor.

1. The `resources` block contains named entities accessible through data-binding and value resolution. Resources are defined in resource blocks within APL documents and packages. In APL, it represents a named constant that you can use to specify a value instead of hardcoding values.

    For example, a resource called `rootContainerWidth` that defines the width of the root container. In your APL document, you can then use `@rootContainerWidth` for any property that accepts a `dimension`. A resource can have conditional logic, so it can resolve to different values based on criteria such as the viewport characteristics. To use the resource, prefix the resource name with the `@` sign, as shown in the `@rootContainerWidth` example.

    Here is a sample resource definition within an APL document:

    ```JSON
    {
      "type": "APL",
      "resources": [
        {
          "when": "${@viewportShape == @viewportShapeRound}",
          "dimension": {
            "rootContainerWidth": "70vw",
            "rootContainerHeight": "70vh",
            "rootContainerLeft": "15vw",
            "rootContainerTop": "15vh",
            "topPaddingBetweenElements": "20"
          }
        },
        {
          "when": "${@viewportShape != @viewportShapeRound}",
          "dimension": {
            "rootContainerWidth": "96vw",
            "rootContainerHeight": "96vh",
            "rootContainerLeft": "2vw",
            "rootContainerTop": "2vh",
            "topPaddingBetweenElements": "10"
          }
        }
      ]
    }
    ```

## References
Below are some useful resources to help you get started:

- [APL Authoring Tool](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-authoring-tool.html)
- [APL Text](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-text.html#fontsize)
- [APL Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-resources.html)
- [Alexa Styles and Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-styles-package.html)