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
