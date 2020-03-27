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

1. To play around with the `Video` snippet, following the steps below:

    1. Open the [APL authoring tool](https://developer.amazon.com/alexa/console/ask/displays)

    1. Click on `Start from scratch` and go to the `APL` tab on the left handside.

    1. Copy/paste content in `document.json` into the editor.

1. Note these rules around component state:

    - Use the `SetValue` command to change to change the `checked` and `disabled` states. This is the recommended way to change these states.

    - Although the `SetState` command can be used to change the `checked` and `disabled` states, it is recommended that you use `SetValue`.

    - A `disabled` component can not have the `hover`, `pressed`, or `focused` states set to
    true. Setting the `disabled` state true on a component will set it's `hover`, `pressed`, and `focused` states to false.

    ```JSON
    "onMount": [
      {
        "type": "SetValue",
        "value": "true",
        "state": "disabled",
        "componentId": "disabledElementId"
      }
    ]
    ```

## References
Below are some useful resources to help you get started:

- [APL Authoring Tool](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-authoring-tool.html)
- [Component State](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-style-definition-and-evaluation.html#component_state)
- [APL Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-resources.html)
- [Alexa Styles and Resources](https://developer.amazon.com/en-US/docs/alexa/alexa-presentation-language/apl-alexa-styles-package.html)