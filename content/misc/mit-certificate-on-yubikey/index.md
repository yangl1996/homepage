+++
title = "Install MIT Certificate on Yubikey"
+++

## Install MIT Certificate on Yubikey

MIT relies on personal certificates for user authentication. Personally I
regard this method as superior to traditional password authentication, but
sometimes I need to log in on a new machine and it is a hassle to install
the certificate on every machine that I may use. Fortunately, I have a
[Yubikey](https://www.yubico.com/products/yubikey-hardware/) on my keyring,
so I spent time figuring out how to install a certificate on it and use that
to log in MIT websites on macOS.

### Obtain the Certificate

Head over to the [IST website](https://ca.mit.edu/ca/certgen) and generate a
certificate. Then import it into Mac's Keychain. You now should have the
certificate and the corresponding private key listed in the Keychain Access
app, like this:

![Keychain Entry Screenshot](./keychain-entry.png)

Then, select the entry and hit ⇧⌘E (Shift-Command-E) to export the item.
Choose "Personal Info Exchange (.p12)" format. Keychain will then ask for
a passphrase to protect the file, which will be used to encrypt the exported
private key. This passphrase will be needed when importing the private key
into Yubikey.

### Import into Yubikey

Use homebrew to install the Yubico PIV Tools by executing
`brew install yubico-piv-tool`. Then plug in your Yubikey. Now import the
certificate and the private key

```bash
yubico-piv-tool -s 9a -i Certificates.p12 -a import-key -a import-cert -K PKCS12
yubico-piv-tool -a set-ccc
yubico-piv-tool -a set-chuid
```

The certificate has now been used in slot `9a` on your Yubikey, which is used
for PIV authentication.

### Make Mac Recognize the Certificate

To make the key recognizable by the Mac, install OpenSC from Homebrew Cask.
Note that the one from non-Cask Homebrew repository will not work.

```bash
brew cask install opensc
```

### Test

1. Unplug the Yubikey.
2. Plug in the Yubikey.
3. Open Keychain Access App. A new keychain containing your certificate should appear.

### Notes

There are some references[^1][^2][^3][^4] on the internet saying that Apple
adds native support for PIV smartcards in High Sierra, and OpenSC is not
needed anymore. However, I've yet got the time to test that, and will stay
with OpenSC for now.

[^1]: [PIV on macOS - OpenPGP Card](https://openpgpcard.org/pivmacos/)
[^2]: [Configure macOS for smart card-only authentication](https://support.apple.com/en-us/HT208372)
[^3]: `man SmartCardServices`
[^4]: [Document Mac OS PIV tokend use and support](https://github.com/GSA/piv-guides/issues/88)
