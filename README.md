## Updating Skype Client flatpak

* check out https://support.skype.com/en/faq/FA34778/release-notes-for-skype-for-windows-mac-linux-and-web for release notes for the latest version
* download latest snap using the link from this one-liner:
```
curl -s -H 'Snap-Device-Series: 16' http://api.snapcraft.io/v2/snaps/info/skype | jq '."channel-map" | map(select(.channel.architecture == "amd64" and .channel.name == "stable")) | .[0].download.url'
```
* get size and SHA256 using `sha256sum`
* update `com.skype.Client.json`'s  last `extra-data` section with new URL, size and SHA256
* add a top `<release>` entry under `<releases>` to the `com.skype.Client.appdata.xml` (`date` attribute value comes from release notes above)
* commit, push & create a PR!
