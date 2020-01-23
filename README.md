# ESLint + Prettier Setup

## About

Tutorial to setup ESLint and Prettier. ESLint scans your code and helps find syntax errors. Prettier will format your code to follow industry standards and best practices. By combining the two to work in tandem you'll have tastiest looking code. All you'll have to do is save, ESLint and Prettier will take care of the rest.

## Steps

### VS Code Settings

First we'll need to install the following Extensions:

[ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

[Prettier](https://https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

Then you'll want to open your Command Palette ( ⌘ + ⇧ + p ) and search for:

> Preferences: Open Settings (JSON)

This will open a file named "settings.json" to which you'll add the following:

```json
"[javascript]": {
  "editor.formatOnSave": false
},
"[javascriptreact]": {
  "editor.formatOnSave": false
},
"[json]": {
  "editor.defaultFormatter": "esbenp.prettier-vscode"
},
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": true
},
"editor.formatOnSave": true,
"prettier.disableLanguages": [
  "javascript",
  "javascriptreact"
]
```

### Project Settings

Every time you start a new project you'll need to run through these steps:

#### Initialize npm

`npm init`

#### Install devDependencies

`npm i -D eslint eslint-config-airbnb eslint-config-prettier eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-prettier eslint-plugin-react prettier`

#### ESLint Config

Run the following in your root folder of the project:

`touch .eslintrc.json`

Add the following configuration to the newly created file ".eslintrc.json":

```json
{
  "extends": ["airbnb", "prettier"],
  "plugins": ["prettier"],
  "rules": {
    "prettier/prettier": ["error"]
  }
}
```

For more ESLint configuration see the [docs](https://eslint.org/docs/user-guide/configuring).

#### Prettier Config

Run the following in your root folder of the project:

`touch .prettierrc`

Add the following configuration to your newly created file ".prettierrc":

```json
{
  "printWidth": 100,
  "singleQuote": false,
  "trailingComma": "es5"
}
```

See the following Prettier [docs](https://prettier.io/docs/en/options.html) for more options.

## Author

[Mike Hume](https://www.github.com/mahume)
