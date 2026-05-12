<div align="center">
  <h1>Popii Registry</h1>
  <p><b>The official directory of verified community plugins for the <a href="https://npmjs.com/package/popii">Popii</a> Discord bot framework.</b></p>
  <p>
    <a href="https://npmjs.com/package/popii">Framework</a> ·
    <a href="plugins.json">Browse plugins</a> ·
    <a href="#submitting-a-plugin">Submit yours</a>
  </p>
</div>

---

## Submitting a plugin

Open a pull request adding your entry to `plugins.json`. Before submitting, make sure:

- Your plugin is published on npm as `popii-plugin-<name>`
- Your `package.json` includes a `"popii"` field (see below)
- Your source repository is public
- It works with the current version of Popii

### `plugins.json` entry

```json
{
  "npm": "popii-plugin-yourplugin",
  "displayName": "Your Plugin",
  "description": "One sentence — what does it add to a bot?",
  "author": "your-npm-username",
  "repo": "https://github.com/you/popii-plugin-yourplugin",
  "category": "features",
  "export": "yourPlugin",
  "verified": true
}
\```

> **`export`** is optional. Only include it if the auto-derived name would be wrong — e.g. `popii-plugin-lastfm` derives to `lastfmPlugin` instead of the correct `lastFmPlugin`.

### `package.json` `"popii"` field

```json
{
  "keywords": ["popii-plugin"],
  "popii": {
    "displayName": "Your Plugin",
    "export": "yourPlugin",
    "configSchema": {
      "apiKey": { "type": "string", "required": true, "env": "YOUR_PLUGIN_API_KEY" }
    }
  }
}
\```

The `configSchema` is optional but recommended — it lets `popii add` automatically prompt users for required environment variables during installation.

---

## Categories

| Value | Use for |
|---|---|
| `core` | Infrastructure — storage, logging, auth |
| `features` | User-facing features — economy, giveaways, moderation |
| `integrations` | Third-party services — Last.fm, Stripe, analytics |
| `utilities` | Developer tools — rate limiting, caching, testing |
| `ui` | UX enhancements — pagination, forms, embeds |
