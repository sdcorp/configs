# Part of package.json (with npm scripts, husky, lint-staged) for React, TypeSript

```json
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",
    "format": "prettier -c --write \"src/**/*.{js,jsx}\"",
    "format:styles": "prettier -c --write \"src/**/*.{css,scss}\"",
    "fast-format": "pretty-quick --staged",
    "lint": "node_modules/.bin/eslint src/ --ext .js,.jsx",
    "lint:fix": "node_modules/.bin/eslint src/ --ext .js,.jsx --fix",
    "lint:errors": "node_modules/.bin/eslint src/ --ext .js,.jsx --fix --quiet",
    "storybook": "start-storybook -p 9009 -s public",
    "build-storybook": "build-storybook -s public"
  },
  "eslintConfig": {
    "extends": "react-app"
  }
  "lint-staged": {
    "*.{html, scss, css, graphql}": [
      "npm run fast-format",
      "git add"
    ],
    "*.{js,ts,jsx,tsx}": [
      "npm run fast-format",
      "npm run lint:errors",
    ]
  },
  "husky": {
    "hooks": {
      "pre-commit": "tsc --noEmit && lint-staged",
      "post-commit": "git update-index --again"
    }
  }
```
