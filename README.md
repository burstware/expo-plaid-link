<p align="center">
  <a href="https://burstware.com">
      <img src="https://s3-us-west-2.amazonaws.com/burstware.com/img/burstware+horizontal.png" width="30%" />
  </a>
</p>

# Expo Plaid Link

[![NPM](https://img.shields.io/badge/npm-1.0.4-blue)](https://www.npmjs.org/@burstware/expo-plaid-link)

Use the official [Plaid Link](https://plaid.com/docs/link/) flow inside your expo app.

<p align="center">
  <a href="https://www.burstware.com/expo-plaid-link">
      <img src="https://plaid.com/assets/img/products/link-example-img.png" width="30%" />
  </a>
</p>

## Installation

```bash
yarn add @burstware/expo-plaid-link
```

## Usage

```typescript
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

_See `types.ts` for data structure format for `onEvent` (see type `LinkEvent`), `onExit` (see type `LinkExit`), and `onSuccess` (see type `LinkSuccess`) function return values._

## Demo

1. `git clone git@github.com:burstware/expo-plaid-link.git`
2. Create a file in the root of the project called `config.ts` with a link token:

```
export default {
  TEST_LINK_TOKEN: 'link-development-deadbeef-7b58-4877-8b44-123456789abcdef',
}
```
3. Update the `main` entry in `package.json` to `"main": "node_modules/expo/AppEntry.js",`
4. `yarn start`
