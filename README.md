# Meta-X

Emacs-esque `M-x` commands for your entire OS.

Built on Electron and Vanilla JavaScript; I know, I know "Electron!?" Well, it's Fast Enough&trade; and it works.

## Support

- [x] Ubuntu Linux
- [x] macOS
- [ ] Windows 10 (testing pending)

## Installation

1. `git clone https://github.com/calebmpeterson/META-x.git`
2. `cd META-x`
3. `yarn install`
4. `yarn start` (or `yarn dev` if you want devtools to open)

**An NPM package is coming soon...**

## Configuration

**Meta-x** config is kept in `~/.meta-x/` directory. This makes it easy to keep your config under source control.

### Settings

All configuration options are contained in `~/.meta-x/config.json`

#### Hotkey

The `hotkey` setting is used to map which global keyboard shortcut launches **Meta-x** on your current selection.

All available keys and modifiers can be viewed [here](https://www.electronjs.org/docs/api/accelerator#available-modifiers)

### Custom Commands

Custom commands are `common.js` modules placed in `~/.meta-x/`.

#### Example Command

To get a calculator capable of all operations/syntax available to you in JavaScript, create `~/.meta-x/calc.js` with the following content:

```js
module.exports = (selection) => eval(selection);
```

#### Non-transforming Commands

To create a command which does not transform the current selection simply return `undefined` from the command module's exported function:

```js
module.exports = (selection) => {
  // Do something side-effect'ish here
  // ...

  // The current selection will not be transformed
  return undefined;
};
```

#### Using NPM Packages

You can use `npm` packages by simply installing them in your `~/.meta-x/`

For example:

```js
> cd ~/.meta-x/
> yarn add lodash
```

## License

**Meta-x** is released under the MIT license.

## Contributing

Issues and Pull Requests are welcome!

### Roadmap

- [x] autocomplete labels
- [x] name (and adjust .directory references)
- [x] GitHub repo
- [x] license
- [x] close the window on `ESC` key press
- [x] configurable hot-key
- [x] usage instructions
- [x] built-in commands
- [x] installation instructions
- [x] Test on macOS
- [x] Improve UI performance (with `choose` on macOS and `dmenu` on Linux)
- [ ] Test on Windows 10
- [ ] add support for command arguments
- [ ] publish to NPM
