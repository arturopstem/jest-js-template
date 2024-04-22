# The Odin Poject

## JavaScript Course: Testing JavaScript

- Install eslint, prettier and plugins :

  ```console
  npm i -D eslint@8 prettier eslint-config-prettier @trivago/prettier-plugin-sort-imports eslint-plugin-jest
  ```

- Run ESLint config tool:

  ```console
  npm init @eslint/config
  ```

- Modify the content of `.eslint.json`:

  ```diff
   {
       "env": {
           "es2021": true,
  -        "node": true
  +        "node": true,
  +        "jest/globals": true
       },
  -    "extends": "airbnb-base",
  +    "extends": [
  +        "airbnb-base",
  +        "prettier"
  +    ],
  +    "plugins": [
  +        "jest"
  +    ],
       "overrides": [],
       "parserOptions": {
           "ecmaVersion": "latest",
           "sourceType": "module"
       },
  -    "rules": {}
  +    "rules": {
  +        "no-console": "off"
  +    }
   }
  ```

- Create file `.prettierrc.json` with the following content:

  ```json
  {
    "singleQuote": true,
    "importOrder": ["^@core/(.*)$", "^@server/(.*)$", "^@ui/(.*)$", "^[./]"],
    "importOrderSeparation": true,
    "importOrderSortSpecifiers": true,
    "plugins": ["@trivago/prettier-plugin-sort-imports"]
  }
  ```

- Install @types/jest for Jest type definitions and enhanced VSCode autocompletion/intellisense

  ```console
  npm i -D @types/jest
  ```

- Open _Preferences: Open Workspace Settings (JSON)_ and enable automatic ESLint fixes and code formatting on save, with the following config in `settings.json`:

  ```json
  {
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": "explicit"
    },
    "editor.formatOnSave": true
  }
  ```
