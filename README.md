# prettier-config-keep

[Prettier](https://prettier.io/) code formatter configuration shared across Keep
Network projects.

## Usage

### Setting up a project

1. Install dependencies:

  ```sh
    npm install --save-dev github:keep-network/prettier-config-keep prettier
  ```

2. Define `prettier` property in `package.json`:

  ```json
  "prettier": "@keep-network/prettier-config-keep"
  ```

3. Define `scripts` property in `package.json`:

  ```json
  "scripts": {
    "format": "prettier --check .",
    "format:fix": "prettier --write ."
  }
  ```

4. Run `npm run format` or `npm run format:fix`

### Plugins

To handle `*.sh` or `*.toml` files you need to install dedicated plugins:

- for `sh`: `npm install --save-dev prettier-plugin-sh`
- for `toml`: `npm install --save-dev prettier-plugin-toml`

And configure the plugins usage in `.prettierrc.js`, e.g.:

```js
module.exports = {
  ...require("@keep-network/prettier-config-keep"),
  plugins: ["prettier-plugin-sh", "prettier-plugin-toml"],
}
```
