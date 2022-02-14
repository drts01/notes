
## Silverblue Experiment

- Lorax [[docs](https://weldr.io/lorax/)][[source](https://github.com/weldr/lorax)]\
  Lorax is used to build the Anaconda Installer boot.iso.
- Config: https://pagure.io/pungi-fedora/blob/main/f/fedora.conf#_769-796

```sh
mkdir ${HOME}isobuild && cd ${HOME}isobuild
dnf install --assume-yes rpm-ostree lorax git-core
git clone --branch main --depth=1 https://pagure.io/fedora-lorax-templates.git
lorax \
  --product Fedora \
  --version rawhide \
  --release "$(printf '%(%Y-%m-%d)T')" \
  --source https://kojipkgs.fedoraproject.org/compose/rawhide/latest-Fedora-Rawhide/compose/Everything/x86_64/os/ \
  --variant Silverblue \
  --volid Fedora-SB-ostree-x86_64-rawhide \
  --nomacboot \
  --logfile $(pwd)/lorax.log \
  --tmp $(pwd)/tmp \
  --add-template $(pwd)/fedora-lorax-templates/ostree-based-installer/lorax-configure-repo.tmpl \
  --add-template $(pwd)/fedora-lorax-templates/ostree-based-installer/lorax-embed-repo.tmpl \
  --add-template $(pwd)/fedora-lorax-templates/ostree-based-installer/lorax-embed-flatpaks.tmpl \
  --add-template-var ostree_install_repo=ostree_install_repo=https://kojipkgs.fedoraproject.org/compose/ostree/repo/ \
  --add-template-var ostree_update_repo=ostree_update_repo=https://ostree.fedoraproject.org \
  --add-template-var ostree_osname=fedora \
  --add-template-var ostree_oskey=fedora-37-primary \
  --add-template-var ostree_contenturl=mirrorlist=https://ostree.fedoraproject.org/mirrorlist \
  --add-template-var ostree_install_ref=fedora/rawhide/x86_64/silverblue \
  --add-template-var ostree_update_ref=fedora/rawhide/x86_64/silverblue \
  --add-template-var flatpak_remote_name=fedora \
  --add-template-var flatpak_remote_url=oci+https://registry-no-cdn.fedoraproject.org \
  --rootfs-size 8 \
  --skip-branding \
  ./results/
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc2ODc1NTQ3MywtMTczNDE0NTg4NywtMT
EwMzA0Mzc1NSwxMjA0NTE1MDMwLC05MDYyMzQ5ODQsLTg4MjQw
NDIwNSwxNzc1MzEwNzU5LDExMzUzMTkyNjFdfQ==
-->