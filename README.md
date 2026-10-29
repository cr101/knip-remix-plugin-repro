# knip remix plugin reproduction

knip's `remix` plugin enables for any `@remix-run/*` dependency, including Remix 3's standalone `@remix-run/headers`. It then treats `app/routes/**` test files as production entries.

```sh
npm install --omit=dev
npx knip@6.43.0 --production --strict
```

Output:

```
Unlisted dependencies (1)
vitest  app/routes/home.test.ts:1:30
```

Adding `"remix": false` to `knip.json` makes the run pass.
