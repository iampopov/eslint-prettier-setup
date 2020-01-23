# ESLint + Prettier Setup

## About

Tutorial to setup [ESLint](https://eslint.org/) and [Prettier](https://prettier.io/). ESLint scans your code to help find syntax errors. Prettier will format your code to follow industry standards and best practices. By combining the two to work in tandem you'll have the tastiest looking code. All you'll have to do is save, then let ESLint and Prettier will take care of the rest.

## Steps

You can begin by cloning the repo to your computer or by hitting the Star at the top of this page for future reference.

### VS Code

#### Extensions

First we'll need to install the following Extensions:

[ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

[Prettier](https://https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

#### Workspace Settings

Then you'll want to open your Command Palette (`⌘` `⇧` `p`) and search for:

> Preferences: Open Settings (JSON)

This will open a file named "settings.json" to which you'll add the following code snippet:

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

You can also copy the code [here](https://raw.githubusercontent.com/mahume/eslint-prettier-setup/master/.vscode/settings.json).

_Just make sure all of your JSON settings live inside of one object, all keys have double quotes, and you don't have any trailing commas._

**IMPORTANT**: Make sure that you delete or disable any auto save functionality settings.

```json
"files.autoSave": "afterDelay",
"files.autoSaveDelay": 1000,
```

### Project Settings

Every time you start a new project you'll need to run through these steps:

#### Initialize npm

```bash
npm init
```

#### Install devDependencies

```bash
npm i -D eslint eslint-config-airbnb eslint-config-prettier eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-prettier eslint-plugin-react prettier
```

#### ESLint Config

Create the following file in the root folder of your project:

```bash
touch .eslintrc.json
```

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

Create the following file in the root folder of your project:

```bash
touch .prettierrc
```

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
