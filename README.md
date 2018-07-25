[![Crowdin](https://d322cqt584bo4o.cloudfront.net/travelflex/localized.svg)](https://crowdin.com/project/travelflex)

[![Build Status](https://travis-ci.org/travelflex/travelflex.svg?branch=master)](https://travis-ci.org/travelflex/travelflex)

TravelFlex as cryptocurrency is built on a new technology called TRF chain, offering scalable, low cost and secure payments. TravelFlex uses byteball network as an underlying platform. Our mission is to provide alternative currency for everyday using, focusing on Asian market to help unbanked people manage their funds better. By doing that, TravelFlex will be the most widely used open source cryptocurrency in the world.

## Main Features

TBD

## Installation

Download and install [NW.js v0.14.7 LTS](https://dl.nwjs.io/v0.14.7) and [Node.js v5.12.0](https://nodejs.org/download/release/v5.12.0/).  These versions are recommended for easiest install but newer versions will work too.  If you already have another version of Node.js installed, you can use [NVM](https://github.com/creationix/nvm) to keep both.

Clone the source:

```sh
git clone https://github.com/travelflex/travelflex.git
cd travelflex
```

If you are building for testnet, switch to testnet branch:
```sh
git checkout testnet
```

Install [bower](http://bower.io/) and [grunt](http://gruntjs.com/getting-started)  if you haven't already:

```sh
npm install -g bower
npm install -g grunt-cli
```

### Build TravelFlex:

If you are using macOS or Linux run:
```sh
make prepare-dev-tn
```
Then run TravelFlex desktop client:
```sh
/path/to/your/nwjs/nwjs .
```
Otherwise run:
```sh
bower install
npm install
grunt
```
If you are on Windows or using NW.js and Node.js versions other than recommended, see [NW.js instructions about building native modules](http://docs.nwjs.io/en/latest/For%20Users/Advanced/Use%20Native%20Node%20Modules/).

After first run, you'll likely encounter runtime error complaining about node_sqlite3.node not being found, copy the file from the neighboring directory to where the program tries to find it, and run again. (e.g. from `travelflex/node_modules/sqlite3/lib/binding/node-v57-darwin-x64` to `travelflex/node_modules/sqlite3/lib/binding/node-webkit-v0.26.2-darwin-x64`)

Then run TravelFlex desktop client:

```sh
/path/to/your/nwjs/nwjs .
```

## Build TravelFlex App Bundles

### Android

- Install Android SDK
- Run `make android-debug`

### macOS and Linux

- run `make prepare-package`

### Windows

- `grunt desktop`
- copy `node_modules` into the app bundle ../byteballbuilds/Byteball/win64, except those that are important only for development (karma, grunt, jasmine)
- `grunt inno64`

## About TravelFlex

TBD

## TravelFlex Backups and Recovery

TravelFlex uses a single extended private key for all wallets, BIP44 is used for wallet address derivation.  There is a BIP39 mnemonic for backing up the wallet key, but it is not enough.  Private payments and co-signers of multisig wallets are stored only in the app's data directory, which you have to back up manually:

* macOS: `~/Library/Application Support/travelflex`
* Linux: `~/.config/travelflex`
* Windows: `%LOCALAPPDATA%\travelflex`


## Translations

TravelFlex uses standard gettext PO files for translations and [Crowdin](https://crowdin.com/project/travelflex) as the front-end tool for translators. To join our team of translators, please create an account at [Crowdin](https://crowdin.com) and translate the TravelFlex documentation and application text into your native language.

To download and build using the latest translations from Crowdin, please use the following commands:

```sh
cd i18n
node crowdin_download.js
```

This will download all partial and complete language translations while also cleaning out any untranslated ones.


## Support

* [GitHub Issues](https://github.com/travelflex/travelflex/issues)
  * Open an issue if you are having problems with this project
* [Email Support](mailto:support@travelflex.org)

## Credits

TravelFlex is based on [Byteball](https://byteball.org/)
## License

MIT.
