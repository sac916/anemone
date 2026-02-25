# Anemone Landing Page — Deployment Guide

**Status:** ✅ Ready to Deploy
**Ship Date:** March 5, 2026

---

## 📦 Deliverables (Complete)

### 1. Landing Page (2 formats)

**Static HTML** — `anemone-landing.html`
- Ready to deploy to GitHub Pages immediately
- No build step required
- 23.5 KB gzipped
- Responsive, accessible, SEO-friendly

**React/Next.js** — `ANEMONE_LANDING_PAGE.tsx`
- For modern framework deployment
- Drop-in component
- Full TypeScript support
- Tailwind CSS (if using Next.js)

### 2. Design System

**Generated with ui-ux-pro-max-skill:**
- Style: Flat Design (clean, minimalist, professional)
- Colors: Indigo #4F46E5 (primary), Green #22C55E (CTAs), Light #EEF2FF (background)
- Typography: Fira Code (headings), Fira Sans (body)
- Responsive: 375px, 768px, 1024px, 1440px
- Accessibility: WCAG AA

### 3. Copy & Messaging (Complete)

- Landing page copy (all 9 sections)
- Twitter threads (3 audiences: researchers, makers, enthusiasts)
- Product Hunt copy (headline, tagline, full description)
- Reddit posts (3 communities: MachineLearning, OpenSource, SideProject)
- Email templates (researchers, makers, AI community)
- Discord messaging
- FAQ & objections

### 4. Launch Plan

- Phase 1: Community prep (Feb 25 - Mar 1)
- Phase 2: Launch day (Mar 5)
- Phase 3: Momentum (Mar 5-15)
- Phase 4: Iteration (Mar 15+)

---

## 🚀 Deployment Steps

### Step 1: Add to getgyre.com Repository

```bash
# In the getgyre.com repo
cd /path/to/getgyre-website

# Create anemone subdirectory
mkdir -p public/anemone

# Copy landing page
cp anemone-landing.html public/anemone/index.html

# (Or create as Next.js route)
# cp ANEMONE_LANDING_PAGE.tsx pages/anemone.tsx
```

### Step 2: DNS / Routing

getgyre.com should route to:
- `getgyre.com/` — Gyre OS landing page (existing)
- `anemone.getgyre.com/` — Anemone landing page

**If using subdomain:**
```
anemone.getgyre.com → GitHub Pages CNAME → getgyre.com/anemone/
```

**If using path:**
```
getgyre.com/anemone/ → /public/anemone/index.html
```

### Step 3: Assets & Optimization

The HTML file includes:
- ✅ All CSS inline (no external stylesheets)
- ✅ Google Fonts CDN (Fira Code, Fira Sans)
- ✅ No external scripts (fully static)
- ✅ SEO metadata (title, description)
- ✅ Mobile viewport configuration

**Optional optimizations:**
- Minify CSS (currently readable for debugging)
- Add Open Graph tags for social preview
- Add favicons (🪸 emoji or custom SVG)

### Step 4: Test Deployment

```bash
# Test locally
open anemone-landing.html

# Check responsiveness
# - Mobile: 375px width
# - Tablet: 768px width
# - Desktop: 1024px+ width

# Verify links
# - Install button scrolls to #install
# - How It Works scrolls to story
# - GitHub link works
```

### Step 5: GitHub Actions (Optional CI/CD)

Add to `.github/workflows/deploy.yml`:

```yaml
name: Deploy Anemone Landing

on:
  push:
    branches: [main]
    paths:
      - 'public/anemone/**'

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./public
```

---

## 🎨 Customization (If Needed)

### Change Colors

Find & replace in `anemone-landing.html`:
- `#4F46E5` → Primary color (currently indigo)
- `#22C55E` → CTA color (currently green)
- `#EEF2FF` → Light background (currently light indigo)
- `#312E81` → Text color (currently dark indigo)

### Change Fonts

In the `<style>` section:
```css
@import url('https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600;700&family=Fira+Sans:wght@300;400;500;600;700&display=swap');
```

Replace `Fira+Code` and `Fira+Sans` with other Google Fonts.

### Change Content

All text is inline in the HTML. Edit directly in any section:
- Hero section
- Story section
- Steps section
- Moods section
- FAQ section
- Footer section

---

## 📊 Analytics & Tracking

### Add Google Analytics (Optional)

```html
<!-- In <head> -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_ID');
</script>
```

### Track Install CTAs

```html
<!-- Replace the Install button -->
<button class="btn btn-primary" onclick="gtag('event', 'install_click'); ..." >
  Install Anemone
</button>
```

---

## 🔒 Security Checklist

- ✅ No external dependencies (except Google Fonts)
- ✅ No JavaScript that evaluates user input
- ✅ No third-party tracking (unless you add it)
- ✅ No forms (nothing to inject/attack)
- ✅ HTTPS ready (GitHub Pages is HTTPS by default)

---

## 🧪 QA Checklist (Before Launch)

- [ ] Desktop view looks good (Chrome, Firefox, Safari)
- [ ] Mobile view is responsive (375px, 768px)
- [ ] All buttons/links work
- [ ] Scroll behavior works (smooth scroll to sections)
- [ ] Colors match design system
- [ ] Typography is clean and readable
- [ ] No console errors
- [ ] Images/emojis render correctly
- [ ] FAQ details toggle works
- [ ] Footer links are correct
- [ ] Social links point to correct repos/Discord/Twitter

---

## 📱 Launch Day (March 5)

**Files to Deploy:**
- [ ] `anemone-landing.html` → `anemone.getgyre.com/` (or `/anemone/`)
- [ ] Update `getgyre.com` navigation to link to Anemone landing
- [ ] Push to GitHub (triggers Pages deploy)

**Concurrent Launches:**
- [ ] Product Hunt post (morning, EST)
- [ ] Twitter threads (staggered)
- [ ] Reddit posts (r/MachineLearning, r/OpenSource, r/SideProject)
- [ ] Email outreach (researchers + makers)
- [ ] Discord announcements

---

## 📈 Post-Launch Iteration

### Week 1 Improvements
- Gather feedback (GitHub issues, Product Hunt comments, Twitter DMs)
- Fix bugs immediately
- Add testimonials section (if early users are happy)
- Create quick FAQ video or GIF

### Week 2 Improvements
- Add analytics dashboard (conversion funnel)
- Optimize CTAs based on data
- Add "Featured in..." badges (if covered by media)
- Consider adding blog post section

### Week 3+ 
- Iterate based on user feedback
- Plan Gyre integration messaging
- Update docs based on common questions

---

## 📞 Support & Communication

### Response Plan

**Product Hunt Comments:**
- Response time: <4 hours
- Tone: Friendly, helpful, honest
- Link to docs for technical questions

**GitHub Issues:**
- Response time: <24 hours
- For bugs: acknowledge + prioritize
- For feature requests: add to roadmap

**Twitter/Reddit:**
- Engage in threads
- No hard selling
- Answer genuine questions
- Share wins from early users

---

## ✅ Success Metrics (Launch Week)

**Target:**
- 500+ GitHub stars
- 100+ Product Hunt upvotes
- 50+ active users
- 3+ community blog posts/threads
- 0 critical bugs

**Track:**
- Page views (Google Analytics)
- Install button clicks
- GitHub star growth
- Product Hunt engagement
- Social mentions

---

## 🎯 Next Steps (After Landing Page)

1. **Phase 1 Execution** (Feb 25 - Mar 1)
   - Schedule Twitter threads
   - Send email outreach
   - Prepare Reddit posts

2. **Phase 2 Launch** (Mar 5)
   - Deploy landing page
   - Post Product Hunt
   - Launch social blitz
   - Monitor responses

3. **Phase 3 Momentum** (Mar 5-15)
   - Engage community
   - Fix bugs
   - Gather feedback
   - Plan iteration

4. **Phase 4 Integration** (Mar 15+)
   - Message Gyre integration path
   - Iterate on landing page
   - Build case studies
   - Plan next milestone

---

**Status:** Ready for deployment. All files complete. Awaiting approval to proceed with Phase 1.

*Last Updated: 2026-02-25*
