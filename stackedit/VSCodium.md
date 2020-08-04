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
```sh
codium --install-extension arnohovhannisyan.syncify
```


<!--stackedit_data:
eyJoaXN0b3J5IjpbNzgwMDIwMDQzLDEzMTc4NTM2MTcsLTE0MT
IwODY4MDYsLTEwOTU2MDM5MzEsMTI3NDMxOTY0MywtODU5MDYz
NzQ0XX0=
-->