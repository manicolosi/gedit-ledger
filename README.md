# gedit-ledger

## Summary

[Ledger](http://www.ledger-cli.org/) support for the
[gedit](https://projects.gnome.org/gedit/) text editor, including:

* Basic syntax highlighting
* Transaction snippet
* Git commit command script for version control

I through this together in a few hours, so don't expect everything to be
perfect. The syntax highlighting doesn't cover all the syntax that ledger
supports and doesn't help catch any mistakes.

The git commit probably doesn't belong here, but it's used for version
controlling my ledger files, so here it is.

The goal of this project was to get some ledger support for a basic text editor
so that my wife can update our ledger file. I personally use vim and the excellent
[vim-ledger](https://github.com/ledger/vim-ledger) plugin.

## Installation

Clone this repo and copy the files for gedit and gtksourceview (the syntax
highlighting engine gedit uses):

```
mkdir -p ~/.local/share/gtksourceview-3.0/language-specs
cp ledger.lang ~/.local/share/gtksourceview-3.0/language-specs
cp git-commit ~/.config/gedit/tools
cp ledger.xml ~/.config/gedit/snippets
```

Oh, don't forget to enable the Snippets and Tools plugins in gedit preferences.
If you're using git to version control your ledger files, enable the git plugin
that shows added/removed/modified lines.

You may want to assign a hotkey to the transaction snippet and the git-commit tool,
too.

## TODO

* Syntax highlighting
  * Catch common mistakes (not having the correct spacing and match `()` and
    `[]` for virtual accounts)
  * Non-dollar commodities
  * Commodity transactions like: `2 BTC @ $800`
  * Non-transaction statements
* More snippets
  * For alternative secondary accounts
  * Splits
* Get rid of the git commit command script and find some other way to support
  Git in gedit
