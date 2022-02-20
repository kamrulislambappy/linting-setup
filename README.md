# Linting eslint setup
Automatically lint and format your feedback project according to popular Airbnb style guide. <br />
Follow the description below.
<br />

## Linting setup by Following 4 Step:
#### 1. Install plugin.
#### 2. Install yarn.
#### 3. Linting setup.
#### 3. Run project.
<br />

### There is no Git Bash Terminal on your PC? <br />
👉 Download Git bash terminal. Go link : [https://git-scm.com/downloads](https://git-scm.com/downloads) <br />
👉 Download Hyper terminal. Go link : [https://hyper.is/](https://hyper.is/)
<br /><br />

### Step number  > 1 :
Install Plugin & Editor Setup
<br />

You need to install the below plugins: <br />

**1.** 
```bash 
  ESLint by Dirk Baeumer
```
<br />

![ESLint by Dirk Baeumer](https://github.com/kamrulislambappy/all-images/blob/main/ESLint%20by%20Dirk%20Baeumer.png)

**2.** Prettier - Code formatter by Prettier <br />
![Prettier - Code formatter by Prettier](https://github.com/kamrulislambappy/all-images/blob/main/Prettier%20-%20Code%20formatter%20by%20Prettier.png)

**3.** Material Icon Theme by Phillipp Kief <br />
![Material Icon Theme by Phillipp Kief](https://github.com/kamrulislambappy/all-images/blob/main/Material%20Icon%20Theme%20by%20Phillipp%20Kief.png)

### Settings
Follow the below settings for Visual Studio Code <br />

**1.** Create a new folder called `.vscode` inside the project root folder. <br />
**2.** And create a new file called `settings.json` inside the `.vscode` folder. <br />
**3.** Copy this code below and paste it inside the `settings.json` file and save the file. <br />
```bash
  {
    // Icon Theme
    "workbench.iconTheme": "material-icon-theme",
    
    // config related to code formatting
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true,
    "[javascript]": {
      "editor.formatOnSave": false,
      "editor.defaultFormatter": null
    },
    "[javascriptreact]": {
      "editor.formatOnSave": false,
      "editor.defaultFormatter": null
    },
    "javascript.validate.enable": false, //disable all built-in syntax checking
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true,
      "source.fixAll.tslint": true,
      "source.organizeImports": true
    },
    "eslint.alwaysShowStatus": true,
    // emmet
    "emmet.triggerExpansionOnTab": true,
    "emmet.includeLanguages": {
      "javascript": "javascriptreact"
    }
  }
```
<br />

### Step number  > 2 :
Install yarn
<br />

**1.** Open the terminal from inside your project. <br />
**2.** Type : `npm install --global yarn` `yarn`<br />
- Check yarn version : `yarn --v`
<br />

### Step number  > 3 :
Linting setup 
<br />

**1.** Copy this code and paste step by step <br />
```bash
  yarn add -D prettier
  yarn add -D babel-eslint
  npx install-peerdeps --dev eslint-config-airbnb
  yarn add -D eslint-config-prettier eslint-plugin-prettier
```
<br />

- Or you can install everything by adding a new script, a single command, in the script section of your project:
- Copy this code and go to `package.json` in your project and paste it in the `scripts` section. 
```bash
  "lint": "yarn add -D prettier && yarn add -D babel-eslint && npx install-peerdeps --dev eslint-config-airbnb && yarn add -D eslint-config-prettier eslint-plugin-prettier",
```
<br />

- If your project does not have a `scripts` section. Write this code  `scripts: {}` and paste it inside.
- #### And then simply run the below command in the terminal
```bash
  yarn lint
```
- You will need `(y/n)` yes or no permissions during installation. You give permission.
<br />

### **2.** Manually create linting configuration files <br />
- Create a `.eslintrc` file on the project root and copy the code below and paste it inside the `.eslintrc` file.
```bash
  {
    "extends": [
      "airbnb",
      "airbnb/hooks",
      "eslint:recommended",
      "prettier",
      "plugin:jsx-a11y/recommended"
    ],
    "parser": "babel-eslint",
    "parserOptions": {
      "ecmaVersion": 8
    },
    "env": {
      "browser": true,
      "node": true,
      "es6": true,
      "jest": true
    },
    "rules": {
      "react/react-in-jsx-scope": 0,
      "react-hooks/rules-of-hooks": "error",
      "no-console": 0,
      "react/state-in-constructor": 0,
      "indent": 0,
      "linebreak-style": 0,
      "react/prop-types": 0,
      "jsx-a11y/click-events-have-key-events": 0,
      "react/jsx-filename-extension": [
        1,
        {
          "extensions": [".js", ".jsx"]
        }
      ],
      "prettier/prettier": [
        "error",
        {
          "trailingComma": "es5",
          "singleQuote": true,
          "printWidth": 100,
          "tabWidth": 4,
          "semi": true,
          "endOfLine": "auto"
        }
      ]
    },
    "plugins": ["prettier", "react", "react-hooks"]
  }
```
<br />

### Step number  > 4 :
Run project
<br />

**1.** Type `yarn start`
- If you get any errors, follow the steps below.
1. Create a new file called `.env` inside project root folder.
2. Copy this code below and paste inside `.env` file
```bash
  SKIP_PREFLIGHT_CHECK=true
```
3. Go your terminal and run again! `yarn start`
