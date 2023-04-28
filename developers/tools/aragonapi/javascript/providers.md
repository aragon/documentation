# Providers

{% hint style="info" %}
A **provider** is used to **send and receive messages between the wrapper and the app**. This is required as apps are sandboxed in an iframe while the wrapper is running in the native context.
{% endhint %}

### Import <a href="#import" id="import"></a>

Providers are usually being imported from `@aragon/api` or `@aragon/wrapper`.

#### ES6 <a href="#es6" id="es6"></a>

```javascript
import { providers } from '@aragon/api'
import { providers } from '@aragon/wrapper'
```

#### ES5 (CommonJS) <a href="#es5-commonjs" id="es5-commonjs"></a>

```javascript
const providers = require('@aragon/api').providers
const providers = require('@aragon/wrapper').providers
```

### MessagePortMessage <a href="#messageportmessage" id="messageportmessage"></a>

A provider communicates through the [MessageChannel PostMessage API](https://developer.mozilla.org/en-US/docs/Web/API/MessagePort/postMessage). It is suitable to use in background scripts since WebWorkers are natively compatible with the MessageChannel API.

**Parameters**

1. `target`: The object (that implements the [MessageChannel PostMessage API](https://developer.mozilla.org/en-US/docs/Web/API/MessagePort/postMessage)) to send messages to. (optional, default `self`)

### WindowMessage <a href="#windowmessage" id="windowmessage"></a>

A provider that communicates through the [Window PostMessage API](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage). It is suitable to use in front-ends connected through an iframe by passing [window.parent](https://developer.mozilla.org/en-US/docs/Web/API/Window/parent).

**Example**

```javascript
const provider = new WindowMessage(window.parent)
```

**Parameters**

1. [`target`](https://hack.aragon.org/docs/%60Object%60): The object (that implements the [Window PostMessage API](https://developer.mozilla.org/en-US/docs/Web/API/Window/postMessage)) to send messages to.

