# aenigma

![aenigma logo](logo/aenigma_logo.png?raw=true)

**aenigma** provisions a **fully functional** and **secure** out of the box **XMPP server** you can get running today.

It does for XMPP what [Mail-in-a-Box](https://github.com/mail-in-a-box/mailinabox) has done for email, [Streisand](https://github.com/StreisandEffect/streisand) for VPNs, and [Easyengine](https://easyengine.io/) for wordpress.

The installation takes you on a 15 minute, clearly worded, step-by-step setup and takes care of everything automagically.

As soon as you're up and running join our conference at os@xc.os.vu !

## Features

* **State of the art configuration**
* **Latest and most robust security** by default
* **One touch deployment**: just clone and run the setup script
* Has a guided, **step-by-step install** that makes sure you get everything perfect on the first run
* Always based on the **latest version of ejabberd**, a modern, scalable, and robust XMPP server
* Passes all of the [XEP-0375 compliance checks](https://github.com/iNPUTmice/ComplianceTester) and those performed by the Conversations client
* Natively supports **Signal-level encrypted conversations** with all the required modules for **OMEMO E2EE**
* Allows you to and guides you through using your **top level domain as the xmpp domain [@example.im]** while hosting the server on a subdomain [xmpp.example.im] as its hostname by using SRV records without any XMPP client UI/UX or TLS conflicts.
* **Supports IPv6** out of the box
* **Validates all required IPv4 and IPv6 DNS settings** [even those for specific modules such as pubsub] and tells you exactly the correct values for every record
* Sets up **UFW rules** for all configured services
* Provisions and automatically renews **free and fully valid TLS [SSL] certificates** for everything [ejabberd and web] thanks to LetsEncrypt
* Installs nginx and makes the ejabberd **web admin interface securely available** at `https://[hostname]`
* Easily allows for the **website for your top level domain** to be **hosted on the same server** as well
* Listens for **XMPP c2s [aka client to server], HTTP_upload, and SSH connections *also* on port 443** [thanks to SSLH] to allow XMPP clients and administrative workstations behind restrictive firewalls to connect without the need to circumvent the firewall with VPNs or Tor
* Configures ejabberd **Shared Roster Groups** to easily allow admins to see all users registered on their own rosters
* Automaticaly **backups up** all ejabberd files and database **locally and [optionally] to S3** and includes a script for a **guided, consistent, and complete restore**.

## Non-features

* Keeps backwards compatibility with legacy XMPP servers by using a not very restrictive ciphersuite for s2s [aka server to server] connections, but you can enable the latest ciphers suggested by cipherli.st [although not recommended] by changing two lines in the config file.

## New features

###  v0.5x

* Full XEP-0375 thanks to ejabberd 18.0x
* Ubuntu 18.04 [bionic beaver] support [and requirement]
* Newly implemented openspace [bash-functions](https://github.com/openspace42/bash-functions)
* So much more, see the [releases](https://github.com/openspace42/aenigma/releases) page for details

## Install

The only supported distro is **Ubuntu**.

* Requirements: LTS release [because of EasyEngine]
* Tested on: 16.04, 18.04 [but as mentioned above EE doesn't support 18.04 for now]
* Recommended: **16.04** [will change this to 18.04 as soon as EE supports it]

Want to test aenigma out on Debian? That would be great, and things should already mostly work! Edit out the checks in the installer and please report back on how everything works! Thank you!

Any distro NOT based on Debian / Ubuntu will NEVER work because our bash-framework is entirely and fundamentally designed to work with these distros only.

```
apt update
apt install git
```

```
git clone https://github.com/openspace42/aenigma
sudo bash aenigma/setup
```

## Restore a previous install on a fresh new machine:
### [either from S3 or another standalone backup from your old instance]

```
apt update
apt install git
```

```
git clone https://github.com/openspace42/aenigma
sudo bash aenigma/tools/aenigma-restore
```

## Recommended clients:

### For Android:

**Conversations** [[github](https://github.com/siacs/Conversations)] [[f-droid](https://f-droid.org/packages/eu.siacs.conversations/)] [[website](https://conversations.im/)]

### For iOS:

**ChatSecure** [[github](https://github.com/chatsecure)] [[app store](https://itunes.apple.com/us/app/chatsecure/id464200063)] [[website](https://chatsecure.org/)]

### For Linux:

**Dino** [still in beta | OMEMO only partially working] [[github](https://github.com/dino/dino)]

## Credits

Very special thankyous to:

Torn [autistici.org] for inspiring in me the idea of a federated messaging network

Gio [eigenlab / LibreMesh] for leading me towards XMPP instead after talking about related projects.

Palinuro + MiBoFra [frozenbox.org / parrotsec.org] for actually getting me started on XMPP.

Daniel Gultsch + Holger Weiß for their excellent work and for their very precious advice and opinions about XMPP at large and its future.

Also, anyone involved in the XMPP community, and aenigma beta testers of course!

Thanks to all of you. Let's make this happen. It's about time [finally].
