
```sh
mkdir ${HOME}isobuild && cd ${HOME}isobuild
dnf install --assume-yes rpm-ostree lorax git-core

```
lorax  --product=Fedora \
		--version=33 \
		--release=20180410 \
		--source=https://kojipkgs.fedoraproject.org/compose/33/latest-Fedora-33/compose/Everything/x86_64/os/ \
		--variant=Silverblue \
		--nomacboot \
		--volid=Fedora-SB-ostree-x86_64-33 \
		--add-template=$(pwd)/fedora-lorax-templates/ostree-based-installer/lorax-configure-repo.tmpl \
		--add-template=$(pwd)/fedora-lorax-templates/ostree-based-installer/lorax-embed-repo.tmpl \
		--add-template-var=ostree_install_repo=file://$(pwd)/repo \
		--add-template-var=ostree_update_repo=file://$(pwd)/repo \
		--add-template-var=ostree_osname=fedora \
		--add-template-var=ostree_oskey=fedora-33-primary \
		--add-template-var=ostree_contenturl=mirrorlist=https://ostree.fedoraproject.org/mirrorlist \
		--add-template-var=ostree_install_ref=fedora/33/x86_64/silverblue \
		--add-template-var=ostree_update_ref=fedora/33/x86_64/silverblue \
		--logfile=$(pwd)/lorax.log \
		--tmp=$(pwd)/tmp \
		--rootfs-size=8 \
		$(pwd)/ostree_installer
```
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTEzMzA0MzkyN119
-->