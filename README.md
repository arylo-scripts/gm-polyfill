# gm-polyfill

Typed wrappers and fallbacks for common userscript APIs.

## Install

```sh
npm install @arylo-scripts/gm-polyfill
```

## Usage

```ts
import {
  GM_addStyle,
  GM_getValue,
  GM_setValue,
  GM_xmlhttpRequestAsync,
} from '@arylo-scripts/gm-polyfill'

GM_addStyle('body { color: red; }')

const theme = GM_getValue('theme', 'light')
GM_setValue('theme', 'dark')

const response = await GM_xmlhttpRequestAsync({
  method: 'GET',
  url: 'https://example.com/api',
})
```

`GM_addStyle` falls back to inserting a `<style>` element when the userscript
runtime does not provide `window.GM_addStyle`.

## API

- `GM_addStyle(cssContent)`
- `GM_getResourceText(name)`
- `GM_getValue(key, defaultValue)`
- `GM_setClipboard(content, type, callback)`
- `GM_setValue(key, value)`
- `GM_xmlhttpRequest(details)`
- `GM_xmlhttpRequestAsync(details)`

## Development

```sh
npm install
npm run lint
npm run build
```
