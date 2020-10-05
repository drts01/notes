# SSH
* https://infosec.mozilla.org/guidelines/openssh.html

## Keygen

```shell
ssh-keygen -t ed25519 -a 100 -N "" -C "NAME@DOMAIN" -f ID_HOST_ed25519_key
```

```shell
ssh -T git@github.com
`````
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEyMTc0NzM5OSwtMTI2Njk0MjkyMiwyMD
U4MTgwMjc2LC0yMTEwMDI2MDg4LDczMDk5ODExNl19
-->