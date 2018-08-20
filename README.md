# /etc/apt/sources.list.d/debian.list for Anonymity Linux Distributions #

A question of distribution maintenance strategies. The more standard
way would indeed be populating /etc/apt/sources.list at install or build time
and leaving /etc/apt/sources.list.d alone. The idea of managing
/etc/apt/sources.list.d/debian.list for the user is, the anonymity
distribution maintainers can decide when it is a better "change stable to
oldstable", "keep wheezy as long as needed to work out [eventual!] issues
that would break during upgrade to jessie" and such.
## How to install `anon-apt-sources-list` using apt-get ##

1\. Add [Whonix's Signing Key](https://www.whonix.org/wiki/Whonix_Signing_Key).

```
sudo apt-key --keyring /etc/apt/trusted.gpg.d/whonix.gpg adv --keyserver hkp://ipv4.pool.sks-keyservers.net:80 --recv-keys 916B8D99C38EAF5E8ADC7A2A8D66066A2EEACCDA
```

3\. Add Whonix's APT repository.

```
echo "deb http://deb.whonix.org stretch main" | sudo tee /etc/apt/sources.list.d/whonix.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install `anon-apt-sources-list`.

```
sudo apt-get install anon-apt-sources-list
```

## How to Build deb Package ##

Replace `apparmor-profile-torbrowser` with the actual name of this package with `anon-apt-sources-list` and see [instructions](https://www.whonix.org/wiki/Dev/Build_Documentation/apparmor-profile-torbrowser).

## Contact ##

* [Free Forum Support](https://forums.whonix.org)
* [Professional Support](https://www.whonix.org/wiki/Professional_Support)

## Payments ##

`anon-apt-sources-list` requires [payments](https://www.whonix.org/wiki/Payments) to stay alive!
