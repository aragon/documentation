# Govern.js API

{% hint style="danger" %}
**WARNING**

Aragon Govern is **beta software** which is **NOT MAINTAINED** anymore. It's a really cool product though with innovative and nifty smart contracts. So although you might run into an **error** 🐲 here and there, the documentation is definitely worth the read and the play!

And welcome to connect with us through [Discord](https://discord.gg/thyHMDt) or our technical [forum](https://support.aragon.org/c/dev-support/20)!
{% endhint %}

## **Usage with default config**

{% hint style="info" %}
The default config **uses the Govern servers** deployed by Aragon.
{% endhint %}

```javascript
import { dao } from '@aragon/govern'

const response = await dao('0x0...')

console.log(response)
```

## **Usage with custom config**

```javascript
import { dao, configure } from '@aragon/govern'

configure({ governURL: 'https://myOwnGovernServer.io' })

const response = await dao('0x0...')

console.log(response)
```

## dao(name) ⇒ `Promise<Dao>`

Returns details about a DAO by his address.

| Param | Type     | Description         |
| ----- | -------- | ------------------- |
| name  | `string` | The name of the DAO |

Example:

```typescript
import { dao } from '@aragon/govern'

const response = await dao('0x0...')
```

## daos() ⇒ `Promise<Dao[]>`

Returns all DAOs.

Example:

```typescript
import { daos } from '@aragon/govern'

const response = await daos()
```

## query(query, args) ⇒ `Promise<object>`

Returns the desired data.

| Param | Type     | Description            |
| ----- | -------- | ---------------------- |
| query | `string` | GraphQL query          |
| args  | `object` | Object with parameters |

Example:

```typescript
import { query } from '@aragon/govern'

const query = await query(myQuery, {...});
```

## createDao(args, options) ⇒ `Promise<TransactionResponse>`

Create

| Param   | Type               | Description                            |
| ------- | ------------------ | -------------------------------------- |
| args    | `CreateDaoParams`  | Dao name, Dao token, useProxies option |
| options | `CreateDaoOptions` | EIP 1193 provider, Dao factory address |

Examples:

For Node.js:

```typescript
import { createDao } from '@aragon/govern'

const result = await createDao(args, options)
```

## configure(config) ⇒ `void`

Overwrites the default configuration of govern.

| Param  | Type                                                                                                                             | Description                                                                                                                               |
| ------ | -------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| config | [`ConfigurationObject`](https://github.com/aragon/govern/tree/master/packages/govern/internal/configuration/Configuration.ts#L4) | Object with all [config options](https://github.com/aragon/govern/tree/master/packages/govern/internal/configuration/Configuration.ts#L4) |

Example:

```typescript
import { configure } from '@aragon/govern'

configure({ governURL: 'https://myOwnGovernServer.io' })
```
