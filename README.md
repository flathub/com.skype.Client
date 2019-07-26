## Updating Skype Client flatpak

* check out https://support.skype.com/en/faq/FA34778/release-notes-for-skype-for-windows-mac-linux-and-web for release notes for the latest version
* get size and SHA256 of target version from https://repo.skype.com/deb/pool/main/s/skypeforlinux/ with `curl -v <link.to.deb> | sha256sum`
* update `com.skype.Client.json`'s  last `extra-data` section with new URL, size and SHA256
* add a top `<release>` entry under `<releases>` to the `com.skype.Client.appdata.xml` (`date` attribute value comes from release notes above)
* commit, push & create a PR!
