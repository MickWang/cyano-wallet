# Cyano Wallet - an Ontology wallet

<p>
  <img width="300px" src="/wallet4.png">
</p>

## Overview

WebExtension (a.k.a Chrome plugin) wallet for the **Ontology** blockchain compatible with Chrome and Firefox.

### What does it currently do

- Create a wallet using mnemonic phrase
- Encrypt a Private Key
- Login with Mnemonic phrase, Private Key or a stored account.
- Ledger support
- Trezor support
- View balance
- Send ONG and ONT
- Withdraw (claim) ONG
- Switch networks (Test/Main/Private) with TLS support
- ONT ID support
- Ontology dAPI support
- NEO and ONT address support for normal and Ledger accounts
- Multi account and multi identity support

## Security

When using this extension be responsible. You can follow some of these security tips:

- Divide your assets between **Cold** (little use) and **Hot** (active use) wallet
- Regularly check your balances
- Use hardware wallet for your **Cold** wallet
- Do not use Smart contract whitelisting on your **Cold** wallet

## Installation

### Download

Plugin is currently distributed in Chrome web store at https://chrome.google.com/webstore/detail/ontology-web-wallet/dkdedlpgdmmkkfjabffeganieamfklkm .

### Manual build

To build manually see the steps below. Or you can download pre-build plugin for Chrome from Release page.

### Required Tools and Dependencies

- Node
- Yarn (https://yarnpkg.com/lang/en/docs/install/)

### Developing and Running

Execute these commands in the project's root directory:

Setup:

#### Install yarn

For faster building process and development experience install Yarn

```
npm install --global yarn
```

#### Download

```
git clone 'https://github.com/ontio/cyano-wallet.git'
```

#### Start the extension in watch mode

This will watch for file changes and build the distribution every time something changes. If the extension is loaded as Unpacked Extension in Chrome, one could reload the extension to get the newest build.

```
yarn watch
```

#### Build extension

This will build the extension for installation into browsers.

```
yarn build
```

#### Ledger support

Ledger support is provided by the Ontology TS SDK extension https://github.com/ontio/ontology-ts-sdk-ledger. Because Chrome allows communication with the Ledger only from HTTPS loaded page (which extension is not), there is used a HTTPS iframe embedded. The iframe is hosted on https://drxwrxomfjdx5.cloudfront.net/forwarder.html and the source codes are at https://github.com/ontio/ledger-forwarder . To change the Iframe address navigate to index.tsx and change the call to

```
Ledger.setLedgerTransport(new Ledger.LedgerTransportIframe('https://drxwrxomfjdx5.cloudfront.net/forwarder.html', true));
```

To use your Ledger, you also need the Official Ontology Ledger App installed on your Ledger.

#### Trezor support

Trezor support is provided by the Ontology TS SDK extension https://github.com/ontio/ontology-ts-sdk-trezor. Trezor allows communication with the Trezor Bridge v2 only from https://*.trezor.io page and Node environment, therefore it is not usable from web pages. But it is usable from Web extensions using WebRequest API.

To use your Trezor, you also needs custom firmware located at https://github.com/backslash47/trezor-core . Ontology support is not yet in official firmware.

## Built With

- [TypeScript](https://www.typescriptlang.org/) - Used language
- [Node.js](https://nodejs.org) - JavaScript runtime for building and ingest
- [React](https://reactjs.org/) - The web framework used
- [Semantic UI](https://react.semantic-ui.com/introduction) - The web framework used
- [Ontology TypeScript SDK](https://github.com/ontio/ontology-ts-sdk) - The framework used

## Authors

- **Matus Zamborsky** - _Initial work_ - [Backslash47](https://github.com/backslash47)

## License

This project is licensed under the LGPL License - see the [LICENSE.md](LICENSE.md) file for details.

The application Gem icon is made by Freepik from www.flaticon.com

## Privacy policy

To see detailed privacy policy of this project visit [PRIVACY.md](PRIVACY.md)

## Acknowledgments

Many thanks to the whole Ontology team, who done a great job bringing Ontology to life.

## Donations

Donations greatly appreciated and ONT/ONG can be sent to: AcqSLx1nSLy9uvVDPrWdNJgwNPfA8UUM4H
