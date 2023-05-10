# Architecture of apps

## Aragon Background Tasks <a href="#aragon-background-tasks" id="aragon-background-tasks"></a>

This spec defines how the Aragon client should handle application background tasks.

#### Motivation <a href="#motivation" id="motivation"></a>

Applications should be able to synchronise state and send notifications even if the application is not open.

#### Defining background tasks <a href="#defining-background-tasks" id="defining-background-tasks"></a>

Applications are already shipped with a standard web manifest (`manifest.json`), and the specification for web manifests also specify how to run background tasks:

> Use the background key to include one or more background scripts, and optionally a background page in your extension.
>
> Background scripts are the place to put code that needs to maintain long-term state, or perform long-term operations, independently of the lifetime of any particular web pages or browser windows.
>
> \[...]
>
> (The `scripts` key is) an array of strings, each of which is a path to a JavaScript source. The path is relative to the manifest.json file itself. These are the background scripts that will be included in the extension.
>
> – [Mozilla Developer Network](https://developer.mozilla.org/en-US/Add-ons/WebExtensions/manifest.json/background)

#### Executing background tasks <a href="#executing-background-tasks" id="executing-background-tasks"></a>

Background tasks for Aragon applications work in exactly the same way, with two modifications: background pages are ignored, and only the first background script is loaded.

#### Flow <a href="#flow" id="flow"></a>

1. The application is registered in the wrapper by `@aragon/wrapper`
2. The wrapper should check if the `manifest.json` defines any background workers
3. If any background workers are defined, the wrapper should execute the defined script in a web worker.

#### Best Practices <a href="#best-practices" id="best-practices"></a>

Background workers should ideally handle event logs and reduce them to an application state. Furthermore, web workers should send notifications in response to events, if necessary.

The front-end portion of Aragon applications should only read the computed state from the web worker, and should not compute state themselves.

## Aragon Sandbox RPC <a href="#aragon-sandbox-rpc" id="aragon-sandbox-rpc"></a>

> **Legend**
>
> * ↔ Data is passed between the wrapper and the client.

#### ↔ `events` <a href="#events" id="events"></a>

Sets up a subscription for events on the proxy attached to the current application.

The wrapper will send events to the listener as they are caught in the event loop until the client unsubscribes.

**Request**

**Parameters**: _None_

**Response**

**Result**: `[event: EthereumEvent]`

#### ↔ `call` <a href="#call" id="call"></a>

Performs a `call`, i.e. simulates a transaction without mutating state. Identical to `eth_call`.

**Request**

**Parameters**: `[method: string, ...params: any]`

**Response**

**Result**: `[returnValues: object]` or an error

#### ↔ `intent` <a href="#intent" id="intent"></a>

Publishes an intent to the wrapper.

The wrapper will process the intent and calculate a transaction path. If no path is found (i.e. the calling entity does not have the necessary permissions) then a JSON-RPC error is sent back.

If a transaction path is found, two things can happen:

* The transaction is signed and the resulting transaction hash is sent back to the client as a response
* The transaction is rejected (i.e. not signed) and a JSON-RPC error is sent back as a response

**Request**

**Parameters**: `[method: string, ...params: any]`

**Response**

**Result**: `[txHash: string]` or an error

#### ↔ `cache` <a href="#cache" id="cache"></a>

Reads or sets a key in the cache.

**Request**

**Parameters**: `[mode: "get" | "set", key: string, value: ?any]`

**Response**

**Result**: `[value: any]`
