# Viewport Profiles
The viewport defines the screen characeristics of the device your skill is running in.
[Viewport Profiles](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-viewport-profiles-package.html) aggregate different characteristics; this should make it easier for you to code to device with similar characteristics, instead of each individual device.

## Sample
This sample shows you the properties that are aggregated into a profile and shows you how to use 'when' clauses to tailor layouts to a device.

```JSON
{
  "when": "${@viewportProfile == @hubRoundSmall}"
}
```

In this case, the `when` clause evaluates to true if the user's device meets the criteria for the `hubRoundSmall` profile.

```JSON
{
  "when": "${@viewportShape == @viewportShapeRectangle}"
}
```

In this case, the `when` clause evaluates to true for any rectangular viewport.

For a complete list of viewport profiles, click [here](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-viewport-profiles-package.html#profiles).

For a complete list of viewport shapes, click [here](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-viewport-profiles-package.html#shape).

## Tips/Notes

- To play around with the `Video` snippet, following the steps below:

    1. Open the [APL authoring tool](https://developer.amazon.com/alexa/console/ask/displays)

    1. Click on `Start from scratch` and go to the `APL` tab on the left handside.

    1. Copy/paste content in `document.json` into the editor.

- You can get access to viewport profiles by importing the `alexa-viewport-profiles` package or the `alexa-layouts` package. This sample used layouts, so we could show that the layouts automatically tailor to devices.

- In your `when` clauses, avoid hardcoding any numbers, such as checking for specific width or height. Use `@viewportProfile`, `@viewportShape` and `@viewportSize` for your checks as much as possible.

## References
Below are some useful resources to help you get started:

- [APL Authoring Tool](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-authoring-tool.html)
- [Viewport Profile](https://developer.amazon.com/docs/alexa-presentation-language/apl-alexa-viewport-profiles-package.html)
- [Configure Viewport Profile](https://developer.amazon.com/docs/alexa-presentation-language/apl-select-the-viewport-profiles-your-skill-supports.html)
- [APL Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-resources.html)
- [Alexa Styles and Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-styles-package.html)
