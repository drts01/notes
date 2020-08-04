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

File: `${HOME}/.config/VSCodium/User/globalStorage/arnohovhannisyan.syncify/settings.json`
```json
{
	"syncer": "repo",
	"repo": {
		"url": "https://github.com/CMeza99/settings-vscodium.git",
		"profiles": [
			{
				"branch": "master",
				"name": "main"
			}
		],
		"currentProfile": "main"
	},
	"file": {
		"path": ""
	},
	"ignoredItems": [
		"**/workspaceStorage",
		"**/globalStorage/state.vscdb*",
		"**/globalStorage/arnohovhannisyan.syncify",
		"**/.git"
	],
	"autoUploadDelay": 20,
	"watchSettings": true,
	"syncOnStartup": false,
	"hostname": "",
	"forceDownload": false,
	"forceUpload": false
}
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQzODI1NjA3NiwxMzAyODAzNjkxLC04NT
g1OTI1NTMsNzgwMDIwMDQzLDEzMTc4NTM2MTcsLTE0MTIwODY4
MDYsLTEwOTU2MDM5MzEsMTI3NDMxOTY0MywtODU5MDYzNzQ0XX
0=
-->