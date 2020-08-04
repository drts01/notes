# Reset Settings

## User
Paths:
* `${HOME}/.config/VSCodium`
* `${HOME}/.vscode-oss`

Clear:
```sh
rm -rf -- ~/.config/VSCod* ~/.vscod*
```
## Market Place

File: `/usr/share/codium/resources/app/product.json`

## Open VSX Registry
```json
"extensionsGallery": {
    "serviceUrl": "https://open-vsx.org/vscode/gallery",
    "itemUrl": "https://open-vsx.org/vscode/item"
}
```

## Visual Studio Marketplace
```json
"extensionsGallery": {
    "serviceUrl": "https://marketplace.visualstudio.com/_apis/public/gallery",
    "cacheUrl": "https://vscode.blob.core.windows.net/gallery/index",
    "itemUrl": "https://marketplace.visualstudio.com/items"
}
```

# Setup

## Initialize
Create config folders.
```sh
codium --list-extensions
```

## Setup Sync

### Install
```sh
codium --install-extension arnohovhannisyan.syncify
```

### Configure
https://arnohovhannisyan.space/vscode-syncify/docs/syncers/repo


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg1ODU5MjU1Myw3ODAwMjAwNDMsMTMxNz
g1MzYxNywtMTQxMjA4NjgwNiwtMTA5NTYwMzkzMSwxMjc0MzE5
NjQzLC04NTkwNjM3NDRdfQ==
-->