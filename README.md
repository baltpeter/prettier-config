# @baltpeter/prettier-config

> The Prettier config I use for my projects.

This package contains the Prettier config I use for my projects. You probably don't want to use this unless you're working on a project with me. Starting with version 3.0.0, it is designed for Prettier 3.0.

## Usage

Install this config its peer dependencies:

```sh
yarn add --dev @baltpeter/prettier-config prettier typescript
```

Then, add the following to your `package.json`:

```json
{
    "prettier": "@baltpeter/prettier-config"
}
```

### Making local changes to the config

If you need to make local changes to the config in a project, most probably to add another plugin, you need to create a `.prettierrc.js` file in the root folder and [extend the base config](https://prettier.io/docs/en/configuration.html#sharing-configurations) like this for example:

```js
import baseConfig from '@baltpeter/prettier-config' assert { type: 'json' };

/** @type {import('prettier').Config} */
export default {
    ...baseConfig,

    plugins: [...baseConfig.plugins, 'prettier-plugin-astro'],

    overrides: [
        {
            files: '*.astro',
            options: {
                parser: 'astro',
            },
        },
    ],
};
```
