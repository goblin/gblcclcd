Goblin's Crypto-Coin LiveCD

This is a LiveCD with a lot of useful crypto-coin related software.
Currently considered crypto-coins are Bitcoin, Ethereum, Zcash
and Bitcoin Cash.

It's meant to be helpful in cold storage scenarios, but it can
also be helpful when online.

Based on Debian Live.

To rebuild the ISO:

1. download and build this repo: https://github.com/goblin/debianize-github
   (you'll need a fresh Debian Stretch container for all this)
2. go up a directory to where you have both gblcclcd and debianize-github
3. run:
```
mkdir -p gblcclcd/config/packages.chroot
find debianize-github/DEBS/ -name '*.deb' -and -not -name '*-dbgsym_*' \
		 | xargs -Ixxx cp xxx gblcclcd/config/packages.chroot/
cd gblcclcd
sudo apt-get install live-build live-config
sudo lb build
```

DISCLAIMER
This live CD contains highly experimental software. NO WARRANTY is
provided whatsoever. Use at your own risk.
