# APL State
Each component has a `state`. A state is a collection of defined Boolean properties that are changed as the user interacts with the APL document.

## Sample

```JSON
{
  "type": "button",
  "text": "checked",
  "checked": "true",
  "id": "checkedElementId",
  "spacing": "2vh"
}
```

In this case, the `button` will have the `checked` state set as true which means the component has been checked or toggled on.

## Tips/Notes

To play around with the `Video` snippet, following the steps below:

  1. Open the [APL authoring tool](https://developer.amazon.com/alexa/console/ask/displays)

  1. Click on `Start from scratch` and go to the `APL` tab on the left handside.

  1. Copy/paste content in `document.json` into the editor.

## References
Below are some useful resources to help you get started:

- [APL Authoring Tool](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-authoring-tool.html)
- [Component State](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-style-definition-and-evaluation.html#component_state)
- [APL Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-resources.html)
- [Alexa Styles and Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-styles-package.html)