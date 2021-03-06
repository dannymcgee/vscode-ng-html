# Angular HTML Syntax

This extension adds tokenization for Angular-specific syntax in HTML template files.

The lack of this feature in VS Code (and lack of a good extension at the time) drove me to WebStorm for a while, but I couldn't stomach the awkward JRE-based text rendering or the extremely limited customization options, so I eventually moved back to VS Code and created this extension. (Update: [another extension](https://marketplace.visualstudio.com/items?itemName=ghaschel.vscode-angular-html) was published in the meantime, which may serve your needs if this one does not.) Issue reports and pull requests are welcome!

## Features
* `*ngIf` and `*ngFor` attributes on an HTML element are marked as control keywords
* Any HTML attribute enclosed with parens (`()`), brackets (`[]`), or both (`[()]`) are marked as Angular attributes
* Punctuation in Angular attribute names are given their own tokens so they can be colored differently than the attribute name itself
* Values of an Angular attribute are tokenized as embedded JavaScript instead of a string
* Angular interpolation (`{{ }}`) in an HTML tag or attribute value are tokenized as embedded JavaScript
* Uses standard naming conventions for new tokens, so it should work with your favorite theme out of the box
* Mostly identical to VS Code's HTML grammar, with small modifications made to add the features listed above

## Screenshots
![Screenshot](./screenshots-1.gif)
![Screenshot](./screenshots-2.gif)
![Screenshot](./screenshots-3.gif)

## Inline Templates
Another small extension of mine, [TypeScript Grammar Extended](https://marketplace.visualstudio.com/items?itemName=dannymcgee.ts-grammar-extended), tokenizes template literals in the value of object members with a key of 'template' as embedded HTML. Since this extension replaces the default HTML grammar (see below), using them both in conjunction means that you can get all the benefits of this extension with your 'inline' Angular templates as well.

## A Note on Implementation
Rather than defining "Angular HTML" as a wholly new language with these new features added on, this extension overrides/replaces the default HTML grammar that comes with VS Code.

The advantages are that your Angular template files will continue to benefit from VS Code's HTML language features (like Emmet, autocomplete and snippets), and any productivity extensions you're already using for HTML (like tag auto-closing, auto-renaming, closing tag highlighting, etc.) will continue to work with Angular template files.

Potential disadvantages are that if you *don't want* this extra syntax highlighting in your non-Angular HTML projects (for example, if you're using a library like Mustache or Handlebars whose syntax conflicts with Angular's), you will need to disable this extension for those projects, or selectively enable it only in your Angular workspaces.

## IntelliSense
To get autcomplete, error detection, and other features for embedded JS blocks in your Angular HTML templates, install the official [Angular Language Service extension](https://marketplace.visualstudio.com/items?itemName=Angular.ng-template).

## License
MIT