
![Find and Replace for Sketch](https://raw.githubusercontent.com/thierryc/Sketch-Find-And-Replace/master/Ressources/logo-256.png)
# Find and Replace for Sketch

Finds text in selected layer(s) and all layers contained within - and replaces it with different text. Features partial, case sensitive and full-document matching.

Now works with symbol overrides. 🎉

Ready for Sketch 48, 47, 46.

New in 1.20: Find and replace in Master Symbol (selection mode only).

![Find and Replace dialog](./Screenshots/screenshot.png)

## Installation

Download and unzip, then double-click on the `Find and Replace.sketchplugin` file.
Sketch will copy it to the plugins folder and install it automatically.

### Install with Sketch Runner

With Sketch Runner, just go to the `install` command and search for `Find and Replace`. Runner allows you to manage plugins and do much more to speed up your workflow in Sketch. [Download Runner here](http://www.sketchrunner.com).

![Sketch Runner screenshot](./Screenshots/sketch-runner.png)

## Update > 1.6

Use Sketch Automatic Update (Sketch 45+)

## Usage
**Menu** - You can access it from the menu **Plugins → Find and Replace**
**Keyboard** - Alternatively, use the keyboard shortcut **cmd + shift + f**

**Complex documents** - If you have an extremely complex document, and set the scope to the entire document, it might take a few seconds longer to process it all. Don't panic if you get a beach ball, it hasn't crashed Sketch, it just has to go through every layer in every artboard in every page and do a comparison.

## Options

### Search scope
How much of your document it will actually search

* If you have selected layers to search in, then **Selected layers** will be chosen automatically.
* You can also choose to search all layers in the **Current page**
* Or you can search the **Whole document** and it will search every layer in every artboard in every page of your document.

### Case matching
Whether it matches exactly as you typed or not

**Case insensitive** by default ("john" will match "John")

**Case sensitive** it will match exactly as you typed it ("john" won't match "John").

### Case replacement
How it deals with capitalisation when replacing

**Intelligent** by default - In intelligent mode and, in conjunction with other search options, it will analyse the current capitalisation and try to match your replacement if possible.

* For example, if you find "smith" and replace with "Street" it will match the "Smith" in "John Smith" and change it to "John Street", preserving the capitalisation.

* It might also match "Blacksmith", but rather than change it to "BlackStreet" it would recognise that it wasn't capitalised to begin with and change it to "Blackstreet".

* If it was "John SMITH", it would recognise the all-capitals presentation of "SMITH" and change it to "John STREET" to preserve the capitalisation.

**Standard** - Replaces exactly what you typed, so could change "John Smith" to "John Street", "Blacksmith" to "BlackStreet" and "John SMITH" to "John Street"

### Where to match
Where in your text layer it should match the search term

**Exact match only** will match your Find text against a text layer if it is *exactly* the same (example "John Smith" will match text layers that read "John Smith"). If you have whitespace (or line breaks) at the start or end, this will *not* match and you should use "Anywhere in layer" as your option (or remove the whitespace - what's the point?!)

**Anywhere in layer** will do a partial match (example "Smith" will match against "John Smith" and replace the word "Smith" only).

**At start of layer** will only match at the start of the text layer ("John" will match against "John Smith", but "Smith" won't). If you have whitespace at the start, this will *not* match.

**At end of layer** will only match at the end of the text layer ("Smith" will match against "John Smith", but "John" won't). If you have whitespace at the end, this will *not* match.

### Match whole words or phrases only
Whether it matches whole or partial words

**Yes** (default) will match whole words ("oh" will not match "John")

**No** will match partial words ("oh" will match "John", if you wanted to change him to "Joan" for example)

## Other features

**Default find text** - If you have a text field selected, it will use that text as the default find text

**Remembers your settings** - Remembers your settings for next time you do a find/replace (doesn't remember find/replace/scope as these will change each time)

## Regex new feature

Get the Regex Power ! ⚡️

### "John Smith" to "Smith John"

Find
```
(\w+)\s+(\w+)
```

Replace with
```
$2 $1
```

Result: Smith John.


#### Replace all double spaces

Find
```
\s{2,}

```

Replace with
```
(one space)

```

Follow me on twitter for more tips.

https://twitter.com/Autre_planete


## Issues or ideas

If you have any problems, or ideas, please open an issue!

### Credits and Thanks

Created by [Martin Steven - @mscodemonkey](https://github.com/mscodemonkey) - Thank you Martin.

Maintained and improved by [Autre Planete - @thierryc](https://github.com/thierryc).

Thanks to [Aby Nimbalkar - @abynim](https://github.com/abynim) - for the SketchPlugin-Remember code to save user settings.

Thanks to [Autre Planete - @thierryc](https://github.com/thierryc) - for writing the code to change text within symbol overrides.

Thanks to [Vincenzo Petito - @vincenzopetito](https://github.com/vincenzopetito) - for code within [Shapr](https://github.com/vincenzopetito/Shapr) showing how to focus the text field on start and tabbing between input fields found within the dialog.

Thanks to [Sean Dellis - @seandellis](https://github.com/seandellis) - for his help, test sketch doc and issues review.

### Disclaimer

I take no responsibility for what you find and replace, or for any changes made unintentionally due to this software erroring. I do test it before I release it so the chances of bugs are minimised, but still, use wisely and completely at your own risk. Remember, cmd-z is your saviour.*
