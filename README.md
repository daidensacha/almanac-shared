# @daidensacha/almanac-shared

Shared constants and helpers for the **Garden Almanac** project.
Used by both **almanac-client** (React frontend) and **almanac-server** (Node/Express backend).

---

## Installation

From the root of your project (once you’ve set up npm workspaces / monorepo):

```bash
npm install @daidensacha/almanac-shared
```

Or if working locally:

```bash
cd almanac-shared
npm link
# then in client or server
npm link @daidensacha/almanac-shared
```

## Exports

Currently included:

- `PASSWORD_REGEX`
- `PASSWORD_MESSAGE`

## Usage

**ESM (client / React / Vite / CRA):**

```js
import { PASSWORD_REGEX, PASSWORD_MESSAGE } from '@daidensacha/almanac-shared';

if (!PASSWORD_REGEX.test(myPassword)) {
  alert(PASSWORD_MESSAGE);
}
```

## CommonJS (server / Node / Express):

```js
const {
  PASSWORD_REGEX,
  PASSWORD_MESSAGE,
} = require('@daidensacha/almanac-shared');

app.post('/signup', (req, res) => {
  if (!PASSWORD_REGEX.test(req.body.password)) {
    return res.status(400).json({ error: PASSWORD_MESSAGE });
  }
});
```

## Roadmap

This package will eventually include more shared helpers, such as: - Input validation rules - Date/time utilities - Category/Tag constants - Shared types (if migrated to TypeScript)

⸻

License

MIT © Daiden Sacha
