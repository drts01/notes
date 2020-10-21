# GPG2
## Expired
```shell
gpg2 --quick-set-expire \
  $(gpg2 --fingerprint --with-colons 'carlos@digitalr00ts.com' \
    | grep -F pub -A1 | tail -1 | cut -d':' -f10) \
  1y
```
# SSH
* https://infosec.mozilla.org/guidelines/openssh.html

## Keygen

```shellc
```

```shell
ssh -T git@github.com
`````
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3ODQ3MzUxODAsLTEyMzg2MDQwNDcsLT
IwOTAxMTAzMzcsMjEyMTc0NzM5OSwtMTI2Njk0MjkyMiwyMDU4
MTgwMjc2LC0yMTEwMDI2MDg4LDczMDk5ODExNl19
-->