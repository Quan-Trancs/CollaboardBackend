# Fix npm Warning in Railway

If you're seeing this warning:
```
npm warn config production Use `--omit=dev` instead.
```

## Quick Fix in Railway Dashboard

1. Go to your Railway project dashboard
2. Click on your service → Settings
3. Under **Build** section:
   - Change **Build Command** to: `npm ci && npm run build`
4. Add environment variable:
   - Key: `NPM_CONFIG_PRODUCTION`
   - Value: `false`

Or update via Railway CLI:
```bash
railway variables set NPM_CONFIG_PRODUCTION=false
```

## Why This Works

- `npm ci` doesn't use the deprecated `--production` flag
- Setting `NPM_CONFIG_PRODUCTION=false` ensures devDependencies are installed (needed for TypeScript build)
- `npm ci` is faster and more reliable than `npm install` in CI/CD

## Alternative: Update Build Command

If the above doesn't work, you can also explicitly override in build command:

**Build Command**: `NPM_CONFIG_PRODUCTION=false npm ci && npm run build`

## Note for TypeScript Projects

TypeScript projects need devDependencies (like `typescript`, `tsx`) during the build phase, so we must install them. The production flag would skip these and cause build failures.

