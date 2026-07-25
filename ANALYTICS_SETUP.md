# Vercel Web Analytics Setup

This project has been configured with **Vercel Web Analytics** using the official `@vercel/analytics` package.

## What was installed

- Package: `@vercel/analytics` (v2.0.1)
- Dev dependency: `esbuild` for bundling the analytics script

## How it works

1. The analytics initialization code is in `analytics.js`
2. The code is bundled into `dist/analytics.bundle.js` using esbuild
3. The bundled script is loaded in `index.html` in the `<head>` section

## Building

To rebuild the analytics bundle:

```bash
npm run build:analytics
```

Or build everything:

```bash
npm run build
```

## Development

To run a local development server:

```bash
npm run dev
```

This will build the analytics and start an HTTP server on port 8080.

## Deployment

When deploying to Vercel:

1. The `dist/analytics.bundle.js` file should be committed to the repository
2. Vercel will automatically detect and use the Web Analytics
3. Make sure to enable Web Analytics in your Vercel project dashboard

## Verifying Analytics

After deployment:

1. Visit your deployed site
2. Open browser DevTools → Network tab
3. Look for requests to analytics endpoints (typically paths containing `/view` or similar)
4. Check the Vercel Dashboard → Analytics to see collected data

## Files Modified/Created

- `package.json` - Added dependencies and build scripts
- `analytics.js` - Analytics initialization code
- `dist/analytics.bundle.js` - Bundled analytics script (generated)
- `index.html` - Updated to load the analytics bundle
- `.gitignore` - Added to ignore node_modules and other files

## Documentation Reference

Setup follows the official Vercel Analytics quickstart guide:
https://vercel.com/docs/analytics/quickstart

The vanilla JavaScript approach using the `inject()` function from `@vercel/analytics`.
