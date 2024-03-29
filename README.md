

# Expo Plaid Link

[![NPM](https://img.shields.io/badge/npm-1.0.7-blue)](https://www.npmjs.org/@burstware/expo-plaid-link)

Use the [Plaid Link](https://plaid.com/docs/link/) flow inside your expo app.

<p align="center">
  <a href="https://github.com/burstware/expo-plaid-link/">
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


## Example Callback Functions
```javascript
const onEventCallback = (event: LinkEvent) => {
  console.log(`Event occurred: ${event.eventName}`, event.metadata);
  // Additional event handling based on the event can be added here
};


const onExitCallback = (exitInfo: LinkExit) => {
  if (exitInfo.error.errorCode) {
    // Here, errorCode is checked to determine if there was an error
    console.error(`Exited with error: ${exitInfo.error.errorMessage} (Code: ${exitInfo.error.errorCode})`);
  } else {
    console.log(`Exited without error. Status: ${exitInfo.metadata.status}`);
  }
  // Additional exit handling logic can be added here
};


const onSuccessCallback = (successInfo: LinkSuccess) => {
  console.log(`Connection successful. Public Token: ${successInfo.publicToken}`, successInfo.metadata);
  // This is where you might handle the successful connection, like sending the publicToken to your server
};


```


_See `const.js` for data structure format for `onEvent` (see type `LinkEvent`), `onExit` (see type `LinkExit`), and `onSuccess` (see type `LinkSuccess`) function return values._


