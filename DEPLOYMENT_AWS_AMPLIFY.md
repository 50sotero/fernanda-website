# AWS Amplify Deployment Guide

Complete guide to deploy your Hugo psychology portfolio website on AWS Amplify.

## Prerequisites

- AWS account (free tier eligible)
- GitHub repository with your code pushed
- Hugo site working locally

## Step 1: Create AWS Account

1. Go to [aws.amazon.com](https://aws.amazon.com)
2. Click "Create an AWS Account"
3. Follow the signup process (credit card required but won't be charged for free tier usage)
4. Verify your email and complete registration

## Step 2: Access AWS Amplify Console

1. Log in to [AWS Console](https://console.aws.amazon.com)
2. Search for "Amplify" in the services search bar
3. Click on **AWS Amplify**

## Step 3: Connect Your Repository

1. In Amplify Console, click **"New app"** → **"Host web app"**
2. Choose your Git provider:
   - **GitHub** (recommended)
   - GitLab
   - Bitbucket
   - AWS CodeCommit
3. Click **"Continue"**

### For GitHub:

1. Authorize AWS Amplify to access your GitHub account
2. Select your repository: `fernanda-website`
3. Select the branch: `main`
4. Click **"Next"**

## Step 4: Configure Build Settings

AWS Amplify should auto-detect Hugo, but verify these settings:

### Build Settings (YAML)

Amplify will show a build configuration. Use this:

```yaml
version: 1
frontend:
  phases:
    preBuild:
      commands:
        - echo "Installing Hugo..."
        - wget -O /tmp/hugo.deb https://github.com/gohugoio/hugo/releases/download/v0.139.0/hugo_extended_0.139.0_linux-amd64.deb
        - sudo dpkg -i /tmp/hugo.deb || true
        - sudo apt-get update && sudo apt-get install -y libc6 libstdc++6
        - sudo dpkg -i /tmp/hugo.deb
    build:
      commands:
        - echo "Building site..."
        - hugo version
        - hugo --gc --minify
  artifacts:
    baseDirectory: public
    files:
      - '**/*'
  cache:
    paths:
      - resources/_gen/**
```

**Or use the simplified version:**

```yaml
version: 1
frontend:
  phases:
    preBuild:
      commands:
        - npm install -g @aws-amplify/cli
    build:
      commands:
        - wget -O /tmp/hugo.deb https://github.com/gohugoio/hugo/releases/download/v0.139.0/hugo_extended_0.139.0_linux-amd64.deb
        - sudo dpkg -i /tmp/hugo.deb || true
        - sudo apt-get update && sudo apt-get install -y libc6 libstdc++6
        - sudo dpkg -i /tmp/hugo.deb
        - hugo --gc --minify
  artifacts:
    baseDirectory: public
    files:
      - '**/*'
```

### Alternative: Use Amplify's Auto-Detection

1. If Amplify detects Hugo automatically, it will show:
   - **App name**: `fernanda-website` (or customize)
   - **Environment**: `main`
   - **Build settings**: Auto-detected
2. Review the settings and click **"Save and deploy"**

## Step 5: Deploy

1. Click **"Save and deploy"**
2. Amplify will:
   - Clone your repository
   - Install dependencies
   - Build your Hugo site
   - Deploy to a global CDN
3. Wait 3-5 minutes for the first deployment

## Step 6: Access Your Site

Once deployment completes:

1. You'll see a green checkmark ✅
2. Your site URL will be: `https://main.xxxxxxxxxxxx.amplifyapp.com`
3. Click the URL to view your site
4. **Bookmark this URL** - it's your live site!

## Step 7: Custom Domain (Optional)

### Add Custom Domain:

1. In Amplify Console, go to **"App settings"** → **"Domain management"**
2. Click **"Add domain"**
3. Enter your domain (e.g., `fernanda-psychologist.com`)
4. Follow the DNS verification steps:
   - Add CNAME record to your domain provider
   - Wait for verification (5-10 minutes)
5. SSL certificate is automatically provisioned (free)

### Domain Provider Instructions:

**For common providers:**

- **GoDaddy**: DNS Management → Add CNAME record
- **Namecheap**: Advanced DNS → Add CNAME record
- **Cloudflare**: DNS → Add CNAME record

**CNAME Record:**
```
Type: CNAME
Name: @ (or www)
Value: [Your Amplify domain from step 6]
TTL: Auto (or 3600)
```

## Step 8: Automatic Deployments

✅ **Automatic deployments are already configured!**

Every time you push to `main` branch:
1. Amplify detects the change
2. Automatically rebuilds your site
3. Deploys the new version
4. Your site updates in 2-3 minutes

**No manual action needed!**

## Build Configuration File (Optional)

You can also create `amplify.yml` in your repo root for more control:

```yaml
version: 1
frontend:
  phases:
    preBuild:
      commands:
        - echo "Installing Hugo Extended..."
        - wget -O /tmp/hugo.deb https://github.com/gohugoio/hugo/releases/download/v0.139.0/hugo_extended_0.139.0_linux-amd64.deb
        - sudo dpkg -i /tmp/hugo.deb || true
        - sudo apt-get update
        - sudo apt-get install -y libc6 libstdc++6
        - sudo dpkg -i /tmp/hugo.deb
        - hugo version
    build:
      commands:
        - echo "Building Hugo site..."
        - hugo --gc --minify
  artifacts:
    baseDirectory: public
    files:
      - '**/*'
  cache:
    paths:
      - resources/_gen/**
```

## Troubleshooting

### Build Fails: "Hugo not found"

**Solution:** The build settings above install Hugo manually. Make sure the preBuild phase runs before the build phase.

### Build Fails: "SCSS compilation error"

**Solution:** Ensure you're using Hugo Extended version (required for SCSS). The build settings above install the extended version.

### Build Succeeds but Site Shows 404

**Solution:** 
1. Check `baseDirectory: public` in build settings
2. Verify Hugo outputs to `public/` directory
3. Check Amplify Console → App settings → Build settings

### Slow Build Times

**Solution:**
- Add cache paths in `amplify.yml` (see above)
- Reduce build frequency if not needed for every commit

### Custom Domain Not Working

**Solution:**
1. Wait 24-48 hours for DNS propagation
2. Verify CNAME record is correct
3. Check SSL certificate status in Amplify Console
4. Clear browser cache

## Monitoring & Analytics

### View Build History:

1. Go to Amplify Console
2. Click on your app
3. See all deployments in the left sidebar
4. Click any deployment to see logs

### View Site Analytics:

1. Amplify Console → Your App → **"Analytics"**
2. See:
   - Page views
   - Unique visitors
   - Top pages
   - Geographic distribution

## Free Tier Limits

**AWS Amplify Free Tier:**
- ✅ 15 GB storage
- ✅ 5 GB/month data transfer
- ✅ 1,000 build minutes/month
- ✅ Unlimited apps
- ✅ Free SSL certificates

**For a personal portfolio site, this is typically enough!**

## Cost Estimation

**Typical monthly usage:**
- Storage: ~50 MB (well under 15 GB)
- Data transfer: ~500 MB (well under 5 GB)
- Build minutes: ~10 minutes/month (well under 1,000)

**Cost: $0/month** (stays within free tier)

## Next Steps

1. ✅ Site is live on Amplify
2. ✅ Automatic deployments configured
3. 🔄 (Optional) Add custom domain
4. 🔄 (Optional) Set up analytics
5. 🔄 (Optional) Configure environment variables if needed

## Support

- **AWS Amplify Docs**: https://docs.amplify.aws
- **Hugo Docs**: https://gohugo.io/documentation/
- **AWS Support**: Free tier includes basic support

---

**Your site is now live on AWS Amplify! 🎉**

Every push to `main` will automatically deploy your updates.
