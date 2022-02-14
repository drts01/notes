
```sh
mkdir ${HOME}isobuild && cd ${HOME}isobuild
dnf install --assume-yes rpm-ostree lorax git-core

            "add_template": ["ostree-based-installer/lorax-configure-repo.tmpl",
	
                             "ostree-based-installer/lorax-embed-repo.tmpl",
	
                             "ostree-based-installer/lorax-embed-flatpaks.tmpl"],
	
            "add_template_var": [
	
                "ostree_install_repo=https://kojipkgs.fedoraproject.org/compose/ostree/repo/",
	
                "ostree_update_repo=https://ostree.fedoraproject.org",
	
                "ostree_osname=fedora",
	
                "ostree_oskey=fedora-37-primary",
	
                "ostree_contenturl=mirrorlist=https://ostree.fedoraproject.org/mirrorlist",
	
                "ostree_install_ref=fedora/rawhide/x86_64/silverblue",
	
                "ostree_update_ref=fedora/rawhide/x86_64/silverblue",
	
                "flatpak_remote_name=fedora",
	
                # using registry-no-cdn avoids redirects to the CDN;
	
                # needed because of network restrictions on koji runroot
	
                "flatpak_remote_url=oci+https://registry-no-cdn.fedoraproject.org",
	
                "flatpak_remote_refs=runtime/org.fedoraproject.Platform/x86_64/f35 app/org.gnome.baobab/x86_64/stable app/org.gnome.Calculator/x86_64/stable app/org.gnome.Calendar/x86_64/stable app/org.gnome.Characters/x86_64/stable app/org.gnome.clocks/x86_64/stable app/org.gnome.Connections/x86_64/stable app/org.gnome.Contacts/x86_64/stable app/org.gnome.eog/x86_64/stable app/org.gnome.Evince/x86_64/stable app/org.gnome.Extensions/x86_64/stable app/org.gnome.font-viewer/x86_64/stable app/org.gnome.gedit/x86_64/stable app/org.gnome.Logs/x86_64/stable app/org.gnome.Maps/x86_64/stable app/org.fedoraproject.MediaWriter/x86_64/stable app/org.gnome.NautilusPreviewer/x86_64/stable app/org.gnome.Screenshot/x86_64/stable app/org.gnome.Weather/x86_64/stable",
	
            ],
	
            'template_repo': 'https://pagure.io/fedora-lorax-templates.git',
	
            'template_branch': 'main',
	
            # dbus-run-session is needed for Flatpak to talk to flatpak-oci-authenticator
	
            'extra_runroot_pkgs': ['flatpak', 'dbus-daemon'],


lorax
  --product=Fedora \
  --version rawhide \
  --release "$(printf '%(%Y-%m-%d)T')"
  --source https://kojipkgs.fedoraproject.org/compose/rawhide/latest-Fedora-Rawhide/compose/Everything/x86_64/os/
  --variant Silverblue \
  --volid=Fedora-SB-ostree-x86_64-rawhide \
  --nomacboot \
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
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTEwMTI2OTY2MCwtOTA2MjM0OTg0LC04OD
I0MDQyMDUsMTc3NTMxMDc1OSwxMTM1MzE5MjYxXX0=
-->