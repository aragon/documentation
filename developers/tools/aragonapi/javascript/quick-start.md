# Quick Start

## Quick Start for apps

```
npm i @aragon/api
```

```javascript
const Aragon = require('@aragon/api')

// Set up app
const app = new Aragon()

// Set the app identifier since multiple instances of this can be installed
// (e.g. for our token manager, we use the ticker of the token it manages)
app.identify('Employee counter')

// Listen to events and build app state
const state$ = app.store((state, event) => {
  // Initial state
  if (state === null) state = 0

  // Build state
  if (event.event === 'Decrement') {
    // Calculate the next state
    state--
  }
  if (event.event === 'Increment') {
    state++
  }

  return state
})

// Log out the state
state$.subscribe(console.log)

// Send an intent to the wrapper
app
  .increment()
  .subscribe(
    txHash => console.log(`Success! Incremented in tx ${txHash}`),
    err => console.log(`Could not increment: ${err}`)
  )
```



> <mark style="color:purple;">**Do you have a question? Leave your comments here at our Discourse forum**</mark>** 👇**

{% embed url="https://support.aragon.org/c/dev-support/20" %}
