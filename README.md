## Building Curl

Here's how to build a custom Curl binary (with OpenSSL) which supports client certificate authentication on OS X. If you're not familiar with the issue, you might want to read this: [http://curl.haxx.se/mail/archive-2013-10/0036.html]()

### Install AutoPkg

Get the latest [AutoPkg](https://github.com/autopkg/autopkg) installed and working. Easiest way is to download and install the [pkg release](https://github.com/autopkg/autopkg/releases/latest). To manually install the bleeding edge:

    $ cd <download_location>
    $ git clone https://github.com/autopkg/autopkg.git
    $ cd autopkg
    $ sudo Scripts/install.sh

### Build with AutoPkg

This repository includes an AutoPkg recipe to download the current release version of curl, compile it and package it.

    $ git clone https://github.com/hjuutilainen/curl-for-munki.git
    $ cd curl-for-munki/autopkg
    $ autopkg run -v curlWithSystemOpenSSL.pkg.recipe

