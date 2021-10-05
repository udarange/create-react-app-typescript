
# Setup TypeScript + ESLint + Prettier + AirBnB Style with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## How to start
### Creating a TypeScript app
```
npx create-react-app my-app --template typescript
cd my-app
```

### ESLint + AirBnB
```
npx eslint --init
? How would you like to use ESLint? To check syntax, find problems, and enforce code style
? What type of modules does your project use? JavaScript modules (import/export)
? Which framework does your project use? React
? Does your project use TypeScript? No
? Where does your code run? Browser
? How would you like to define a style for your project? Use a popular style guide
? Which style guide do you want to follow? Airbnb: https://github.com/airbnb/javascript
? What format do you want your config file to be in? JSON
```

Go to `./.eslintrc.json`, replace the below lines
```
"parser": "babel-eslint"
```
Add below under rules section,
```
"rules": {
    ...
    "react/jsx-filename-extension": [1, { "extensions": [".js", ".jsx", ".ts", ".tsx"] }],
    "import/no-unresolved": 0,
    "import/extensions": 0
    ...
}
```


Add this new script to `package.json` file under `scripts`
```
"lint": "eslint --fix src/**/*.{js,jsx,ts,tsx}"
```
Now you can simply fix all the lint issues by executing the below command.
```
npm run lint
```


### Prettier

Prettier is a code formatter
```
npm install prettier eslint-plugin-prettier eslint-config-prettier --save-dev
```
Add a few things to ./.eslintrc.json
* Add "prettier" to the plugins section.
* Add "prettier" to the extends section.
* Add "prettier/prettier": "warn" to the rules section.

Creating a ./.prettierrc file to configure Prettier in the root directory.
```
.prettierrc.js
```

## Finally, your `.prettierrc.js` file should look like this,
```
module.exports = {
  singleQuote: false,
  printWidth: 120,
  endOfLine: "auto",
  trailingComma : "none",
};
```

Add this new script to `package.json` file under `scripts`
```
"format": "prettier --write src/**/*.{js,jsx,ts,tsx}"
```
Now you can simply format all files by executing the below command.
```
npm run format
```

## Finally, your `.eslintrc.json` file should look like this,
```
{
    "env": {
        "browser": true,
        "es2021": true
    },
    "parser": "babel-eslint",
    "extends": [
        "plugin:react/recommended",
        "airbnb",
        "prettier"
    ],
    "parserOptions": {
        "ecmaFeatures": {
            "jsx": true
        },
        "ecmaVersion": 12,
        "sourceType": "module"
    },
    "plugins": [
        "react",
        "@typescript-eslint",
        "prettier"
    ],
    "rules": {
        "prettier/prettier": "warn",
        "react/jsx-filename-extension": [1, { "extensions": [".js", ".jsx", ".ts", ".tsx"] }],
        "import/no-unresolved": 0,
        "import/extensions": 0
    }
}
```


**Note: Don't forget to run `npm run format` before starting the project.

In the project directory, you can run:
1. `npm run start`
2. `npm run build`

To learn React, check out the [React documentation](https://reactjs.org/).

# SASS

**Sass provides much more power with features like**:

-   Variables
-   Nesting
-   Mixins

file extention
> .scss

