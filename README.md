# ORACLE CONSULT GHANA — website starter

A responsive business website with a glassmorphism-inspired visual style and a Decap CMS admin dashboard.

## What's included

- Public landing page: services, about, insights/blog preview, contact form and footer.
- `/admin/` dashboard powered by Decap CMS.
- CMS fields for business name, homepage copy, contact details, logo upload, services, blog posts and media.
- Green, yellow, red and white palette.
- Responsive mobile navigation.
- Netlify contact form support.

## Important: admin publishing needs authentication setup

A static website cannot securely save public changes by itself. The admin uses **Decap CMS with Netlify Identity + Git Gateway** so edits are committed to your Git repository. This starter is designed for Netlify hosting for the admin workflow. The public website itself can be hosted on GitHub Pages or Netlify, but the built-in admin publishing workflow is not plug-and-play on GitHub Pages alone.

### Recommended deployment (Netlify)

1. Create a GitHub repository and upload all files/folders in this project to its root. Keep the `admin`, `assets`, `content` and `uploads` folders.
2. In Netlify, choose **Add new site → Import an existing project** and connect the repository. Set the branch to `main`; build command can be left blank; publish directory is `.`.
3. Open the site's Netlify dashboard and look under **Integrations / Identity**. Enable Netlify Identity if it is available for your account, then enable Git Gateway. Netlify product availability can change; if Identity/Git Gateway is unavailable, use a supported GitHub-backed CMS such as Pages CMS or configure an OAuth-backed Decap CMS backend instead.
4. In Identity settings, set registration to **Invite only** and invite your own email address. Do not leave public sign-ups open.
5. Open `https://YOUR-SITE.netlify.app/admin/` and sign in from the invite email. If it asks you to confirm your identity, follow the email link first.
6. In the CMS, open **Website content → Brand & homepage** and update your contact email, logo and copy. Use **Blog posts** to create articles. Uploads are committed to the repository.
7. When you publish a change, Netlify deploys the updated site.

**Security:** keep registration invite-only, use a strong unique password and do not share admin invitations.

## GitHub Pages option

GitHub Pages can serve the public HTML/CSS/JS, but it cannot run a secure server-side CMS login or commit changes from a static admin page. You can host the public site on GitHub Pages and use an external Git-backed CMS (for example, Pages CMS connected to your repository), or keep the complete admin publishing flow on Netlify. Do not add GitHub personal access tokens to browser-side JavaScript.

## Editing the design manually

- Main page: `index.html`
- Styles and responsive layout: `assets/css/style.css`
- Mobile navigation and optional content hooks: `assets/js/site.js`
- CMS configuration: `admin/config.yml`
- Starter content: `content/site.json`, `content/services.json`, `content/blog/`

## Before launch

- Replace `hello@oracleconsultghana.com` with your actual business email.
- Confirm the services and descriptions match your business.
- Add your real logo in the CMS after authentication is configured.
- Update social links if you want them added.
- Test the contact form on the deployed Netlify site.
- Review the site on mobile and desktop.
- The initial blog articles shown on the landing page are sample copy; replace them with your real posts before launch.

## Known starter limitation

The homepage loads brand/homepage settings and service cards from JSON files, so those edits appear on the public site after deployment. The blog collection is configured in the CMS, but the three editorial cards on the homepage are starter sample copy and are not yet automatically generated from blog entries. Replace those sample cards manually, or add a static-site build step if you want blog posts to populate automatically.
