# monorepo-demo-nx-pnpm

## Getting Started

```sh
npm install -g pnpm
pnpm install
```

## Develop

![graph](https://user-images.githubusercontent.com/1491961/158563420-15e293a9-5ff6-4677-99ab-e9521e7c0b1e.png)

```sh
pnpm nx dev web-1
# > nx run web-1:dev

pnpm nx build web-1
# > nx run ui:build
# > nx run web-1:build
# https://nx.dev/configuration/packagejson#target-dependencies
# https://nx.dev/using-nx/mental-model

pnpm nx deploy web-1
# > nx run web-1:lint
# > nx run web-1:test
# > nx run ui:build
# > nx run web-1:build
# > nx run web-1:deplo

pnpm nx run-many --target=test --projects=web-1,web-2
# > nx run web-1:test
# > nx run web-2:test

pnpm nx run-many --target=test --all
# > nx run web-1:test
# > nx run web-2:test
# > nx run ui:test

pnpm nx affected --target=test
# (no tasks)

echo "export const foo = 'foo';" >> packages/ui/index.ts
pnpm nx affected --target=test 
# > nx run web-1:test
# > nx run ui:test
# https://nx.dev/using-nx/mental-model#affected-commands

# Graph dependencies within workspace.
# https://nx.dev/cli/dep-graph
pnpm nx graph

# Install a package
pnpm add <pkg> --filter web-1
```