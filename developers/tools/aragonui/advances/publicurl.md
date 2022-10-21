# PublicUrl

PublicURL is used to access your local path to aragonUI’s assets (e.g. fonts, etc.), so they load properly. It is mostly used internally.

### Usage <a href="#usage" id="usage"></a>

```jsx
import { PublicUrl } from '@aragon/ui'

function App() {
  return (
    <PublicUrl>
      {url => (
        <img src={`${url}/example.png`} />
      )}
    </PublicUrl>
  )
}
```
