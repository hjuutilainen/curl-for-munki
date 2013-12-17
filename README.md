## Building Curl

Here's how to build a custom Curl binary (with OpenSSL) which supports client certificate authentication on OS X Mavericks. If you're not familiar with the issue, you might want to read this: [http://curl.haxx.se/mail/archive-2013-10/0036.html]()

### Install Homebrew

Get [Homebrew](http://brew.sh) installed and working. On a clean system it's usually just:

    $ ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
    $ brew doctor

### Install brew-pkg

This will allow us to build a .pkg installer later on. [Brew-pkg](https://github.com/timsutton/brew-pkg) is brought to you by always-awesome Tim Sutton.

    $ brew tap timsutton/formulae
    $ brew install brew-pkg

### Install Curl

Without any arguments, Curl will use the system provided OpenSSL.

    $ brew install curl

It's normal to get a warning like this:

    This formula is keg-only, so it was not symlinked into /usr/local.
    
    Mac OS X already provides this software and installing another version in
    parallel can cause all kinds of trouble.

### Create a pkg with dependencies

    brew pkg --with-deps curl

