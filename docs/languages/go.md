# Go with Visual Studio Code

Using the Go extension for Visual Studio Code, you get many of the language 
features like Intellisense, Code navigation, Symbol search, bracket matching, 
snippets and a whole lot of other features that will help you in Golang development.

You can install the Go extension from the [marketplace](https://marketplace.visualstudio.com/items?itemName=lukehoban.Go).

## Intellisense

### Auto complete
As you type your Go code, you can see auto complete kick in and provide you with suggested
completion items. This works for even packages that are not imported yet. In the below example,
you can see completion for members from current, imported and unimported packages.

Gif here

By setting `go.autocompleteUnimportedPackages` to `true` in your settings, you can also
get all the importable packages in the suggestions. 

> Tip: Use `kb(editor.action.triggerSuggest)` to trigger the suggestions manually.

### Hover Info
Hovering on any variable, function, struct will give you information on that item like
its documentation, signature etc. 

Gif here

### Signature help
When you open the `(` while calling a function, a pop up provides signature help for the function.

Gif here

>Tip: Use `kb(editor.action.triggerParameterHints)` to manually trigger the signature help when the
cursor is inside the `()` in the function call.

> Note: The default implementatio for Hover Info and Signature Help uses a combination of `godef` and `godoc`.
In certain cases like items from packages that are dot imported, unexported members from current package and structs, this doesnt work. Change the setting `go.docsTool` to `gogetdoc` to get support for these cases as well. 

## Code navigation

Below code navigation features which are self-explainatory are available in the context menu in the editor.

- Go To Defintion
- Peek Definition
- Find All References

You can navigate via symbol search using the below commands from the command palette

- File Outline
- Workspace Symbol search

You can also navigate back and forth between a Go file and its test implementation. 

- Open Test File
- Open Implemention for Test File

## Build, Lint and Vet

On save, the Go extension can kick `go build`, `go vet` and your choice of linting tool (`golint` or `gometalinter`) on the package to which your currently saved file belongs to. You can control these features via the below settings
- go.buildOnSave
- go.buildFlags
- go.vetOnSave
- go.vetFlags
- go.lintOnSave
- go.lintFlags
- go.lintTool

The errors and warnings from running any/all of the above will be shown red/green squiggly lines in the editor. These also show up in the Problems pane.

## Formatting

You can format your Go file using `kb(editor.action.formatDocument)` or by running the command `Format Document` in the command palette. 

Another way is to use the "Format Document" option in the context menu in the editor.

By default, formatting is run when you save your Go file. You can disable this by setting `go.formatOnSave` to `false`.

You can choose among 3 formatting tools: `gofmt`, `goreturns` and `goimports` by changing the setting `go.formatTool`.

## Test

There are commands in the command palette that can run tests in the current package, file or at cursor using `go test`.

There are also commands to generate test skeletons for the functions in the current package, file or at cursor using `gotests`.

Explore these commands by typing `Go: test` in the command pallete. 




