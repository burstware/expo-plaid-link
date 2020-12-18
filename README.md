<p align="center">
  <a href="https://burstware.com">
      <img src="https://s3-us-west-2.amazonaws.com/burstware.com/img/burstware+horizontal.png" width="30%" />
  </a>
</p>

# Plaid Link Expo

[![NPM](https://img.shields.io/badge/npm-1.0.2-blue)](https://www.npmjs.org/@burstware/react-native-portal)

Use the official [Plaid Link](https://plaid.com/docs/link/) flow inside your expo app.

<p align="center">
  <a href="https://www.burstware.com/expo-plaid-link">
      <img src="https://plaid.com/assets/img/products/link-example-img.png" width="30%" />
  </a>
</p>

## Installation

```bash
npm i --save @burstware/expo-plaid-link
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
      onSuccess={(success) => console.log(success)}
    />
  )
}
```
