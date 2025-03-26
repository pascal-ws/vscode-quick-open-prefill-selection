# Fork for customizations
- Background: I use [CTRL] + [Q] to execute this with a prefix '@' to search for definitions in this file quickly. Therefore, I've added a prefix in the source file. Note that when enabling the extension, omit the "editorHasSelection" to start with the prefix directly.

See Readme here: https://github.com/ColCh/vscode-quick-open-prefill-selection

# Notes for building/packing for VSCode (VSIX)

```pwsh
git clone https://github.com/pascal-ws/vscode-quick-open-prefill-selection
cd vscode-quick-open-prefill-selection
npm install
npm run package
mv "dist" "out"
vsce pack
# will ask for a license, accept y
```

https://code.visualstudio.com/api/working-with-extensions/bundling-extension

https://code.visualstudio.com/api/working-with-extensions/publishing-extension


# Notes for installation: 
- In VSCode, go to extensions > ... > install from VSIX > Use your VSIX 
- Restart extensions (popup)
- Open keybindings file CTRL+K CTRL+S
- Change to JSON view

```json
[
    {
        "key": "ctrl+shift+q",
        "command": "extension.quickOpen.withPrefill",
        "when": "editorTextFocus"
    }
]
```

