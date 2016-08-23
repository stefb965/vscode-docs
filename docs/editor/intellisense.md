---
Order: 4
Area: editor
TOCTitle: IntelliSense
ContentId: 80f4fa1e-d4c5-42cf-8b12-4b8e88c41c3e
PageTitle: IntelliSense in Visual Studio Code
DateApproved: 8/15/2016
MetaDescription:  Learn about Visual Studio Code IntelliSense (intelligent code completion). 
---

# IntelliSense

IntelliSense is a general term for a variety of code editing features, including: code completion, parameter info, quick info, and list members. IntelliSense is described in a number of ways such as "code completion", "content assist", and "code hinting."

![IntelliSense demo](images/intellisense/intellisense.gif)

## Where is IntelliSense for my language? 

VS Code IntelliSense is provided for JavaScript, TypeScript, JSON, HTML, CSS, Less, and Sass out of the box. Other languages have word completions and can be configured to have IntelliSense by installing a language extension. 

Below are the most popular language extensions in the [Marketplace](https://marketplace.visualstudio.com/vscode). Click on an extension tile below to read the description and reviews to decide which extension is best for you. 

> **Tip:** For configuring and troubleshooting JavaScript IntelliSense see [here](/docs/languages/javascript.md#configuring-intellisense).

<div class="marketplace-extensions-languages"></div>

## IntelliSense Features

VS Code IntelliSense features are powered by a language service. A language service provides intelligent code completions based on language semantics and an analysis of your code. If a language service knows possible completions, the IntelliSense suggestions will pop up as you type. If you continue typing characters, the list of members (variables, methods, etc.) is filtered to include only members containing your typed characters. Pressing `kbstyle(Tab)` or `kbstyle(Enter)` will insert the selected member. 

You can trigger IntelliSense in any editor window by typing `kb(editor.action.triggerSuggest)` or by typing a trigger character (such as `.` in JavaScript). 

![intellisense in package json](images/intellisense/intellisense_packagejson.gif)

> **Tip:** The suggestions filtering supports CamelCase so you can type the upper case letters of a method name to limit the suggestions. For example, "cra" will quickly bring up "createApplication".

> **Tip:** You can turn off IntelliSense while you type. See [Customize IntelliSense below](/docs/editor/intellisense.md#customize-intellisense).

As provided by the language service, you can see **quick info** for each method. 

![quick info](images/intellisense/quick_outline.png)

After choosing a method you are provided with **parameter info**. 

![parameter info](images/intellisense/paramater_info.png)

> **Tip:** When applicable, a language service will surface the underlying types in the quick info and method signatures. In the image above, you can see several `any` types. Because JavaScript is dynamic and doesn't need or enforce types, `any` suggests that the variable can be of any type. 


## Types of Completions

The JavaScript code below illustrates IntelliSense completions. IntelliSense gives both inferred proposals and the global identifiers of the project. The inferred symbols are presented first, followed by the global identifiers (shown by the document icon). 

![intellisense icons](images/intellisense/intellisense_icons.png)

VS Code IntelliSense offers different types of completions, including language, snippets, and textual completions. 

|       |         |
| ----- | ------- |
| ![method icon](images/intellisense/method_icon.png) | Methods, Functions, or Constructors |
| ![variable icon](images/intellisense/variable_icon.png) | Variables | 
| ![class](images/intellisense/class_icon.png) | Classes |
| ![interface](images/intellisense/interface_icon.png) | Interfaces |
| ![module](images/intellisense/module_icon.png) | Modules |
| ![property](images/intellisense/property_icon.png) | Properties and Attributes |
| ![symbol](images/intellisense/enum_icon.png) | Enums |
| ![symbol](images/intellisense/symbol_icon.png) | Symbols |
| ![keyword](images/intellisense/keyword_icon.png) | Keywords |
| ![value](images/intellisense/value_icon.png) | Values |
| ![global identifiers](images/intellisense/file_icon.png) | Global Identifiers |
| ![a square with ellipses forming the bottom show snippet prefix](images/intellisense/snippet_icon.png) | Snippet Prefixes |
| ![a square with letters abc word completion](images/intellisense/word_completion_icon.png) | Words |

## Customize IntelliSense

You can customize your IntelliSense experience in settings and key bindings. 

### Settings

The settings shown below are the default settings. You can change these settings in your settings.json file as described [here](/docs/customization/userandworkspace.md). 

```javascript
{

    // Controls if quick suggestions should show up while typing
    "editor.quickSuggestions": true,

    // Controls if suggestions should be accepted with "Enter" - in addition to "Tab". Helps to avoid ambiguity between inserting new lines and accepting suggestions. 
    "editor.acceptSuggestionOnEnter": true,

    // Controls the delay in ms after which quick suggestions will show up. 
    "editor.quickSuggestionsDelay": 10
    
    // Enable word based suggestions
    "editor.wordBasedSuggestions": true
}
```

### Key Bindings

The key bindings shown below are the default key bindings. You can change these key bindings in your `keybindings.json` file as described [here](/docs/customization/keybindings.md). 

> **Note:** The key bindings below are the most popular key bindings for IntelliSense. There are many more key bindings relating to IntelliSense. Simply open key bindings and search for "suggest." 

```json
{

   { 
       "key": "ctrl+space",            
       "command": "editor.action.triggerSuggest",
        "when": "editorHasCompletionItemProvider && editorTextFocus && !editorReadonly" 
    },
    { 
        "key": "tab",                   
        "command": "acceptQuickFixSuggestion",
        "when": "editorFocus && quickFixWidgetVisible" 
    },
    { 
        "key": "enter",                 
        "command": "acceptQuickFixSuggestion",
        "when": "editorFocus && quickFixWidgetVisible" 
    },
}
```


## Troubleshooting IntelliSense

If you find IntelliSense has stopped working, the language service may have crashed. Simply restart VS Code and this should solve the issue. If you continue to lack IntelliSense features after installing a language extension, open an issue in the repository of the language extension. 

> **Tip:** For configuring and troubleshooting JavaScript IntelliSense see [here](/docs/languages/javascript.md#configuring-intellisense).

> **Note:** Not all language extensions give all or even some IntelliSense features. Read the extension's README to find the right fit for you. 

> **Tip:** You can find the issue repository for most extensions in the [Marketplace](https://marketplace.visualstudio.com/vscode). Navigate to the extension's detail page and click `Support`. 


## Next Steps

IntelliSense is straight forward enough. Let's keep going. 

* [JavaScript](/docs/languages/javascript.md) - Get the most out of your JavaScript development, including configuring IntelliSense.
* [Node.js](/docs/runtimes/nodejs.md#intellisense-and-typings) - See an example of IntelliSense in action in the Node.js walkthrough. 
* [Debugging](/docs/editor/debugging.md) - Learn how to setup debugging for your application. 

## Common Questions

* Why am I not getting any suggestions? (see image below)

![image of IntelliSense not working](images/intellisense/intellisense_error.png)

This issue can be caused by a variety of reasons. First, try restarting VS Code. If the problem persists, consult the language extension's documentation. For JavaScript specific troubleshooting, please navigate to the [JavaScript language document](/docs/languages/javascript.md). 

* Why am I not seeing method and variable suggestions? (see image below)

![image of IntelliSense showing no useful suggestions](images/intellisense/missing_typings.png)

This issue is caused by missing typings files in JavaScript. You can learn how to solve this issue in the [JavaScript language document](/docs/languages/javascript.md). For other languages, please consult the extension's documentation. 
