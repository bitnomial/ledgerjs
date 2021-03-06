<img src="https://user-images.githubusercontent.com/211411/34776833-6f1ef4da-f618-11e7-8b13-f0697901d6a8.png" height="100" />

[Github](https://github.com/LedgerHQ/ledgerjs/),
[API Doc](http://ledgerhq.github.io/ledgerjs/),
[Ledger Devs Slack](https://ledger-dev.slack.com/)

## @ledgerhq/hw-transport-webauthn

Allows to communicate with Ledger Hardware Wallets.

**[Web]** **(WebAuthn)** – WebAuthn api. [check browser support](https://caniuse.com/webauthn).

### Known limitation

There is a "blink" at each time there is a communication with the device due to WebAuthn. WebAuthn is meant for authentification and we use it for communication, ideally prefer WebUSB.

## API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

#### Table of Contents

-   [TransportWebAuthn](#transportwebauthn)
    -   [Examples](#examples)
    -   [exchange](#exchange)
        -   [Parameters](#parameters)
    -   [setScrambleKey](#setscramblekey)
        -   [Parameters](#parameters-1)
        -   [Examples](#examples-1)

### TransportWebAuthn

**Extends Transport**

WebAuthn Transport implementation

#### Examples

```javascript
import TransportWebAuthn from "@ledgerhq/hw-transport-webauthn";
...
TransportWebAuthn.create().then(transport => ...)
```

#### exchange

Exchange with the device using APDU protocol.

##### Parameters

-   `apdu` **[Buffer](https://nodejs.org/api/buffer.html)** 

Returns **[Promise](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Promise)&lt;[Buffer](https://nodejs.org/api/buffer.html)>** a promise of apdu response

#### setScrambleKey

A scramble key is a string that xor the data exchanged.
It depends on the device app you need to exchange with.
For instance it can be "BTC" for the bitcoin app, "B0L0S" for the dashboard.

##### Parameters

-   `scrambleKey` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** 

##### Examples

```javascript
transport.setScrambleKey("B0L0S")
```
