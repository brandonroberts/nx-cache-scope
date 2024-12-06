# NxCacheScope

This reproduces an issue where an app with an npm scope is not restored from cache when output to `node_modules`.

## Steps

1. npm install
2. Run `npx nx build my-app`
3. Check `node_modules/my-app`
4. Delete `node_modules/my-app` folder
5. Run `npx nx build my-app`
6. Note that `node_modules/my-app` is restored
7. Run `npx nx build my-scoped-app`
8. Check `node_modules/@my-scoped-app`
9. Delete `node_modules/@my-scoped-app` folder
10. Run `npx nx build my-scoped-app`
11. Note that `node_modules/@my-scoped-app` is not restored even though the cache output says it was.
