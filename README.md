# Kicksecure APT and Flatpak Repository Configuration #

Configuring APT and Flatpak sources:
- Includes Debian APT repositories (main, updates, backports, fasttrack,
security)
- Incorporates Debian APT components (main, contrib, non-free,
non-free-firmware)
- Integrates the Flathub repository (verified and floss subsets only)

Flatpak:
- Official Flathub repository only.
- Uses subset verified_floss, which means only verified applications and
freedom software can be installed by default.

Provides configuration files:
- /etc/apt/sources.list.d/debian.list for APT sources
- /etc/flatpak/remotes.d/flathub.flatpakrepo for Flatpak sources

A Discussion on Distribution Maintenance Strategies:

The more standard
way would indeed be populating /etc/apt/sources.list at install or build time
and leaving /etc/apt/sources.list.d alone.

The idea of managing
/etc/apt/sources.list.d/debian.list for the user is, the security-focused
distribution maintainers can decide when it is a better "change stable to
oldstable", "keep wheezy as long as needed to work out [eventual!] issues
that would break during upgrade to jessie" and such.

## How to install `anon-apt-sources-list` using apt-get ##

1\. Download the APT Signing Key.

```
wget https://www.kicksecure.com/keys/derivative.asc
```

Users can [check the Signing Key](https://www.kicksecure.com/wiki/Signing_Key) for better security.

2\. Add the APT Signing Key.

```
sudo cp ~/derivative.asc /usr/share/keyrings/derivative.asc
```

3\. Add the derivative repository.

```
echo "deb [signed-by=/usr/share/keyrings/derivative.asc] https://deb.kicksecure.com bookworm main contrib non-free" | sudo tee /etc/apt/sources.list.d/derivative.list
```

4\. Update your package lists.

```
sudo apt-get update
```

5\. Install `anon-apt-sources-list`.

```
sudo apt-get install anon-apt-sources-list
```

## How to Build deb Package from Source Code ##

Can be build using standard Debian package build tools such as:

```
dpkg-buildpackage -b
```

See instructions.

NOTE: Replace `generic-package` with the actual name of this package `anon-apt-sources-list`.

* **A)** [easy](https://www.kicksecure.com/wiki/Dev/Build_Documentation/generic-package/easy), _OR_
* **B)** [including verifying software signatures](https://www.kicksecure.com/wiki/Dev/Build_Documentation/generic-package)

## Contact ##

* [Free Forum Support](https://forums.kicksecure.com)
* [Premium Support](https://www.kicksecure.com/wiki/Premium_Support)

## Donate ##

`anon-apt-sources-list` requires [donations](https://www.kicksecure.com/wiki/Donate) to stay alive!

