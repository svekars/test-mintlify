# Mintlify Documentation Setup

This is a complete Mintlify setup for Stripe-like API documentation.

## What's Included

- ✅ Professional configuration in `mint.json`
- ✅ Getting started pages (introduction, quickstart, authentication)
- ✅ API reference examples (users endpoints)
- ✅ Guide examples (webhooks, rate-limits, errors)
- ✅ Stripe-inspired color scheme (#635bff)
- ✅ Multi-language code examples
- ✅ Interactive API playground
- ✅ Mobile responsive design

## Quick Start

### 1. Install Mintlify CLI

```bash
npm install -g mintlify
```

### 2. Start Dev Server

```bash
cd 1-mintlify
mintlify dev
```

Visit http://localhost:3000 to see your docs!

### 3. Deploy

```bash
# Deploy to Mintlify hosting (free tier available)
mintlify deploy
```

## File Structure

```
1-mintlify/
├── mint.json                 # Main configuration
├── introduction.mdx          # Homepage
├── quickstart.mdx           # Quick start guide
├── authentication.mdx        # Auth documentation
├── api-reference/
│   └── users/
│       ├── list.mdx         # GET /users
│       └── create.mdx       # POST /users
└── guides/
    ├── webhooks.mdx         # Webhook guide
    ├── rate-limits.mdx      # Rate limiting
    └── errors.mdx           # Error handling
```

## Customization

### Colors

Edit the `colors` section in `mint.json`:

```json
{
  "colors": {
    "primary": "#635bff",
    "light": "#8b85ff",
    "dark": "#4239cc"
  }
}
```

### Navigation

Update the `navigation` array in `mint.json` to organize your docs:

```json
{
  "navigation": [
    {
      "group": "Get Started",
      "pages": ["introduction", "quickstart"]
    }
  ]
}
```

### API Endpoints

Add new API endpoints by creating MDX files in `api-reference/`:

```mdx
---
title: "List Users"
api: "GET https://api.example.com/v1/users"
description: "Retrieve a list of users"
---

Your content here...
```

## Features

### Interactive Code Examples

Use `<CodeGroup>` for multi-language examples:

```mdx
<CodeGroup>

```bash cURL
curl https://api.example.com/v1/users
```

```python Python
import requests
response = requests.get('https://api.example.com/v1/users')
```

</CodeGroup>
```

### Components

Mintlify provides many useful components:

- `<Card>` - Feature cards
- `<CardGroup>` - Grid of cards
- `<Steps>` - Step-by-step guides
- `<Tabs>` - Tabbed content
- `<Accordion>` - Collapsible sections
- `<Info>`, `<Warning>`, `<Tip>`, `<Note>` - Callouts

### API Parameters

Document parameters with `<ParamField>`:

```mdx
<ParamField query="limit" type="integer" default="10">
  A limit on the number of objects to be returned
</ParamField>
```

### Response Fields

Document responses with `<ResponseField>`:

```mdx
<ResponseField name="id" type="string">
  Unique identifier for the user
</ResponseField>
```

## OpenAPI Integration

Mintlify can automatically generate API docs from OpenAPI specs:

1. Place your `openapi.yaml` in the root directory
2. Reference it in `mint.json`:

```json
{
  "openapi": ["openapi.yaml"]
}
```

3. Mintlify will auto-generate API reference pages!

## Analytics

Add analytics to `mint.json`:

```json
{
  "analytics": {
    "ga": {
      "trackingId": "G-XXXXXXXXXX"
    },
    "plausible": {
      "domain": "docs.example.com"
    }
  }
}
```

## Custom Domain

To use a custom domain:

1. Deploy to Mintlify: `mintlify deploy`
2. Add a CNAME record: `docs.example.com` → `your-site.mintlify.app`
3. Configure in Mintlify dashboard

## Environment Variables

For API playground, set your test API key in `.env`:

```
NEXT_PUBLIC_API_KEY=sk_test_...
```

## Advanced Features

### Search

Built-in search is automatically enabled. No configuration needed!

### Versioning

Create multiple versions:

```json
{
  "versions": ["v1", "v2"],
  "navigation": {
    "v1": [...],
    "v2": [...]
  }
}
```

### Internationalization

Add multiple languages:

```json
{
  "i18n": {
    "defaultLocale": "en",
    "locales": ["en", "es", "fr"]
  }
}
```

## Deployment Options

### Option 1: Mintlify Hosting (Recommended)

```bash
mintlify deploy
```

- Free tier available
- Automatic SSL
- CDN included
- Built-in analytics

### Option 2: Self-Hosting

Build static files and host anywhere:

```bash
mintlify build
```

Deploy the `_site` folder to:
- Vercel
- Netlify
- AWS S3 + CloudFront
- GitHub Pages

## Support

- [Mintlify Documentation](https://mintlify.com/docs)
- [Component Reference](https://mintlify.com/docs/components)
- [Discord Community](https://discord.gg/mintlify)
- [GitHub Issues](https://github.com/mintlify/mint)

## Pricing

- **Free**: Up to 3 team members, unlimited docs
- **Starter**: $120/month - More team members, analytics
- **Growth**: $250/month - Custom domain, SSO
- **Enterprise**: Custom pricing - SLA, dedicated support

## Tips

1. **Use the playground**: Test API calls directly in docs
2. **Add screenshots**: Upload to `images/` directory
3. **Link between pages**: Use relative paths like `/quickstart`
4. **Add metadata**: Use frontmatter for SEO
5. **Keep it simple**: Stripe-like docs are clean and focused

## Next Steps

1. Customize the colors and branding
2. Add your actual API endpoints
3. Write comprehensive guides
4. Add code examples in all languages
5. Deploy and share with your team!
