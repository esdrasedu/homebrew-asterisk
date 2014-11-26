# Homebrew Asterisk
This repo contains the Homebrew formulas I use for my [Asterisk][ast] dev
machine. This is pretty much a few packages which, for one reason or
another, aren't the best fit for going into Homebrew itself.

## Installation
    brew tap leedm777/asterisk
    brew install asterisk

## Running asterisk

If you want to just run Asterisk occasionally, just start it up using
`asterisk -c`.

## Running as a service

To install and run Asterisk as a service, add an asterisk group and user:

    sudo dseditgroup -o create asterisk
    sudo dscl . create /Users/asterisk
    sudo dseditgroup -o edit -a asterisk -t user asterisk

Follow the instructions in the "Using launchd" section [here][voip-info], but
replace `/usr/local/asterisk/sbin/asterisk` with
`/usr/local/sbin/asterisk`.

    launchctl load /Library/LaunchDaemons/org.asterisk.asterisk.plist

 [ast]: http://asterisk.org/
 [voip-info]: http://www.voip-info.org/wiki/view/Building+Asterisk+on+MacOSX
