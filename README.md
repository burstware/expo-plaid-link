<p align="center">
  <a href="https://burstware.com">
      <img src="https://s3-us-west-2.amazonaws.com/burstware.com/img/burstware+horizontal.png" width="30%" />
  </a>
</p>

# Expo Plaid Link

[![NPM](https://img.shields.io/badge/npm-1.1.0-blue)](https://www.npmjs.org/@burstware/expo-plaid-link)
[![Slack](https://img.shields.io/badge/chat-slack-green)](https://form.typeform.com/to/vyAEGkWC)

Use the [Plaid Link](https://plaid.com/docs/link/) flow inside your expo app.

<p align="center">
  <a href="https://www.burstware.com/expo-plaid-link">
      <img src="https://plaid.com/assets/img/products/link-example-img.png" width="30%" />
  </a>
</p>

## Installation

```bash
expo install @burstware/expo-plaid-link
```

## Usage

```javascript
import React from 'react'
import PlaidLink from '@burstware/expo-plaid-link'
import Config from './config'

export default function App() {
  return (
    <PlaidLink
      linkToken={Config.TEST_LINK_TOKEN}
      onEvent={(event) => console.log(event)}
      onExit={(exit) => console.log(exit)}
      onSuccess={(success) => console.log(success.publicToken)}
    />
  )
}
```

_See `const.js` for data structure format for `onEvent` (see type `LinkEvent`), `onExit` (see type `LinkExit`), and `onSuccess` (see type `LinkSuccess`) function return values._
