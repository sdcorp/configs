# Example of graphql code generator config. Read the [docs](https://graphql-code-generator.com/docs/getting-started/codegen-config) for more details

```yaml
overwrite: true
schema: 'YOUR_GRAPHQL_SCHEMA_PATH' # source of your graphql schema
documents: 'src/graphql/**/*.graphql' # destination where to render
generates:
  src/generated/graphql.tsx:
    plugins:
      - 'typescript'
      - 'typescript-operations'
      - 'typescript-react-apollo'
    config:
      reactApolloVersion: 3
      withHOC: false
      withComponent: false
      withHooks: true
      withRefetchFn: true
      skipTypename: true
```
