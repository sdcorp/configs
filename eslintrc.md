# Eslint config for React+TypeScript project (.eslintrc.js)

```js
module.exports = {
  parser: '@typescript-eslint/parser', // Specifies the ESLint parser
  extends: [
    'plugin:react/recommended', // Uses the recommended rules from @eslint-plugin-react
    'plugin:@typescript-eslint/recommended', // Uses the recommended rules from the @typescript-eslint/eslint-plugin
    'prettier/@typescript-eslint', // Uses eslint-config-prettier to disable ESLint rules from @typescript-eslint/eslint-plugin that would conflict with prettier
    'plugin:prettier/recommended', // Enables eslint-plugin-prettier and eslint-config-prettier. This will display prettier errors as ESLint errors. Make sure this is always the last configuration in the extends array.
    'plugin:import/errors',
    'plugin:import/warnings',
    'plugin:import/typescript',
  ],
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 2018,
    sourceType: 'module',
  },
  plugins: ['react-hooks'],

  // ignore some dir/files from lint checks
  // ignorePatterns: ['*.test.tsx', 'graphql.tsx']

  // Place to specify ESLint rules. Can be used to overwrite rules specified from the extended configs
  rules: {
    // JS
    'no-console': 'error',
    'no-debugger': 'error',
    'no-empty-pattern': 'error',
    'object-shorthand': 'error',
    // TS
    '@typescript-eslint/explicit-function-return-type': 'off',
    '@typescript-eslint/no-empty-function': 'warn',
    '@typescript-eslint/no-explicit-any': 'error',
    '@typescript-eslint/interface-name-prefix': 'off',
    '@typescript-eslint/no-unused-vars': 'error',
    '@typescript-eslint/explicit-module-boundary-types': 'off',
    // react
    'react/prop-types': 'off',
    'react/jsx-sort-props': [
      'warn',
      {
        callbacksLast: true,
        shorthandFirst: true,
        reservedFirst: ['key', 'ref'],
      },
    ],
    'react/style-prop-object': 'error',
    'react/void-dom-elements-no-children': 'error',
    'react/no-this-in-sfc': 'error',
    'react/self-closing-comp': [
      'error',
      {
        component: true,
        html: true,
      },
    ],
    'react/no-multi-comp': 'warn',
    'react/no-deprecated': 'error',
    'react/no-unknown-property': 'warn',
    'react/no-array-index-key': 'warn',
    'react/no-children-prop': 'error',
    'react/function-component-definition': [
      'warn',
      {
        namedComponents: 'arrow-function',
        unnamedComponents: 'arrow-function',
      },
    ],
    'react/jsx-pascal-case': 'error',
    'react/jsx-no-bind': [
      'error',
      {
        ignoreDOMComponents: true,
        ignoreRefs: true,
        allowArrowFunctions: true,
      },
    ],
    'react/jsx-no-duplicate-props': 'error',
    'react/jsx-no-undef': 'error',
    'react/jsx-no-useless-fragment': 'warn',
    'react/state-in-constructor': ['error', 'never'],
    'react/destructuring-assignment': ['warn', 'always'],
    'react/jsx-props-no-spreading': [
      'warn',
      {
        html: 'ignore',
        // 'explicitSpread': 'ignore' | 'enforce',
        // 'exceptions': [<string>]
      },
    ],
    // hooks
    'react-hooks/rules-of-hooks': 'error',
    'react-hooks/exhaustive-deps': 'warn',
    // imports
    'import/no-unresolved': 'warn',
    'import/default': 'off', //? weird issue related with this rule. Disable for now
    'import/newline-after-import': ['warn', { count: 1 }],
    'import/no-named-as-default-member': 'error',
    'import/no-anonymous-default-export': [
      'error',
      {
        allowArray: false,
        allowArrowFunction: false,
        allowAnonymousClass: false,
        allowAnonymousFunction: false,
        allowCallExpression: true, // The true value here is for backward compatibility
        allowLiteral: false,
        allowObject: false,
      },
    ],
    'import/no-default-export': 'error',
    'import/order': [
      'error',
      { groups: ['builtin', 'external', 'internal', 'sibling', 'parent', 'index'], 'newlines-between': 'always' },
    ],
  },
  settings: {
    react: {
      version: 'detect', // Tells eslint-plugin-react to automatically detect the version of React to use
    },
    'import/parsers': {
      '@typescript-eslint/parser': ['.ts', '.tsx'],
    },
    'import/resolver': {
      // use <root>/tsconfig.json
      typescript: {
        alwaysTryTypes: true, // always try to resolve types under `<roo/>@types` directory even it doesn't contain any source code, like `@types/unist`
      },
    },
  },
}
```
