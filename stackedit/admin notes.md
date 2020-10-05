# GPG2
## Expired
```shell
gpg2 \
  $(gpg2 \
    --fingerprint
    --with-colons 'carlos@digitalr00ts.com' \
    | grep -F pub -A1 \
    | tail -1 \
    | cut -d':' -f10) \
  
```
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
eyJoaXN0b3J5IjpbMjAyMjUzMjE5MSwyMTIxNzQ3Mzk5LC0xMj
Y2OTQyOTIyLDIwNTgxODAyNzYsLTIxMTAwMjYwODgsNzMwOTk4
MTE2XX0=
-->