# SVP Homepage SEO Changes — Claude Code Prompt

> Paste this entire prompt into Claude Code when working on the svitvideoproduction.ca homepage source files.

---

I need you to make the following SEO changes to the homepage HTML file. Make every change exactly as specified. Do not reformat, restructure, or modify anything else on the page.

---

**1. Replace the title tag**

Find:
```
<title>Drone Videography Toronto | Commercial Aerial Video & Photography | Svit Video Production</title>
```
Replace with:
```
<title>Drone Videography Toronto | Svit Video Production</title>
```

---

**2. Replace the meta description**

Find:
```
<meta name="description" content="Toronto's certified drone videography company for real estate and commercial projects. Fast turnaround, fully insured, GTA-wide coverage. Free quote in minutes. ☎ (647) 290-6941">
```
Replace with:
```
<meta name="description" content="Toronto's certified drone videography company for real estate & commercial projects. Fully insured, 48-hr delivery. Free quote: (647) 290-6941.">
```
Do not touch the `<meta name="author" content="Alex Svit">` line.

---

**3. Add canonical tag**

Search for `rel="canonical"` in the source. If it exists and reads exactly `https://svitvideoproduction.ca/` — leave it. If it is missing or different, add this line to `<head>`:
```
<link rel="canonical" href="https://svitvideoproduction.ca/" />
```

---

**4. Replace the existing LocalBusiness schema block**

Search for the existing `application/ld+json` script block that contains `"@type": "LocalBusiness"` or `"@type": "ProfessionalService"`. Replace that entire script block with:
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "ProfessionalService",
  "name": "Svit Video Production",
  "image": "https://cdn.svitvideoproduction.ca/img/home/logo-simple-white.svg",
  "logo": "https://cdn.svitvideoproduction.ca/img/home/logo-simple-white.svg",
  "url": "https://svitvideoproduction.ca/",
  "telephone": "+16472906941",
  "email": "info@svp.video",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "Toronto",
    "addressRegion": "ON",
    "addressCountry": "CA"
  },
  "areaServed": [
    {"@type": "City", "name": "Toronto"},
    {"@type": "City", "name": "North York"},
    {"@type": "City", "name": "Scarborough"},
    {"@type": "City", "name": "Etobicoke"},
    {"@type": "City", "name": "Mississauga"},
    {"@type": "City", "name": "Brampton"},
    {"@type": "City", "name": "Vaughan"},
    {"@type": "City", "name": "Markham"},
    {"@type": "City", "name": "Richmond Hill"},
    {"@type": "City", "name": "Oakville"},
    {"@type": "City", "name": "Burlington"}
  ],
  "priceRange": "$$",
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday","Tuesday","Wednesday","Thursday","Friday"],
      "opens": "08:00",
      "closes": "19:00"
    },
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Saturday"],
      "opens": "08:00",
      "closes": "17:00"
    }
  ],
  "description": "Toronto's certified drone videography company for real estate agents, developers, and contractors. Transport Canada Advanced Operations certified. Fully insured.",
  "sameAs": [
    "https://maps.app.goo.gl/7PuM1bQqqdinTpfp7",
    "https://www.instagram.com/svitvideoproduction",
    "https://www.facebook.com/SVP.videography",
    "https://www.linkedin.com/company/svit-video-production",
    "https://threads.net/svitvideoproduction"
  ]
}
</script>
```

---

**5. Add Service schema**

Check if a `"@type": "Service"` JSON-LD block already exists. If it does not exist, paste the following as a new script block immediately before `</body>`:
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Service",
  "name": "Drone Videography Toronto",
  "description": "Cinematic 4K drone videography and aerial photography for real estate agents, developers, and corporate clients across Toronto and the GTA. Transport Canada Advanced Operations certified. Fully insured. 48-hour delivery.",
  "provider": {
    "@type": "ProfessionalService",
    "name": "Svit Video Production",
    "url": "https://svitvideoproduction.ca/",
    "telephone": "+16472906941"
  },
  "areaServed": [
    {"@type": "City", "name": "Toronto"},
    {"@type": "City", "name": "Mississauga"},
    {"@type": "City", "name": "Vaughan"},
    {"@type": "City", "name": "Markham"},
    {"@type": "City", "name": "Scarborough"},
    {"@type": "City", "name": "Etobicoke"},
    {"@type": "City", "name": "Richmond Hill"},
    {"@type": "City", "name": "Oakville"},
    {"@type": "City", "name": "Burlington"}
  ],
  "hasOfferCatalog": {
    "@type": "OfferCatalog",
    "name": "Aerial Drone Services",
    "itemListElement": [
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "Aerial Photo Package", "description": "10-15 MLS-ready aerial stills. Same-day raw access. 48-hour delivery."}},
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "Aerial Video Package", "description": "Up to 45 seconds of 4K stabilized aerial video. Cinematic colour-grading. 48-hour delivery."}},
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "Combo Package", "description": "Full aerial photo and video coverage. 10-15 stills and up to 45 seconds of 4K drone video."}},
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "Construction Progress Documentation", "description": "Multi-site aerial documentation for construction projects. Milestone captures, investor-ready footage."}}
    ]
  }
}
</script>
```

---

**6. Fix the Alex photo alt text**

Find the `<img>` tag with `alt="Alex Svit flying a Drone"` and change only the alt attribute to:
```
alt="Alex Svit, certified drone pilot — Svit Video Production"
```

---

**7. Fix decorative icon alt text**

For every `<img>` tag whose `src` contains any of the following filenames, set `alt=""`:
```
icon-play.svg
icon-chat.svg
icon-menu.svg
icon-arrow-right.svg
icon-quote.svg
icon-phone.svg
icon-mail.svg
icon-location.svg
icon-threads.svg
icon-facebook.svg
icon-linkedin.svg
icon-instagram.svg
```

---

**8. Add 301 redirects for three legacy pages**

These three URLs must redirect permanently to the homepage. Use whichever redirect method is appropriate for the server setup (Apache .htaccess or Nginx config):

Apache:
```
Redirect 301 /drone-services/real-estate https://svitvideoproduction.ca/
Redirect 301 /drone-services/photo-and-video https://svitvideoproduction.ca/
Redirect 301 /aerial-videography-services https://svitvideoproduction.ca/
```
Nginx:
```
rewrite ^/drone-services/real-estate$ https://svitvideoproduction.ca/ permanent;
rewrite ^/drone-services/photo-and-video$ https://svitvideoproduction.ca/ permanent;
rewrite ^/aerial-videography-services$ https://svitvideoproduction.ca/ permanent;
```

---

**9. Create sitemap.xml**

Create a file called `sitemap.xml` in the same directory as `index.html` with this content:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://svitvideoproduction.ca/</loc>
    <changefreq>monthly</changefreq>
    <priority>1.0</priority>
  </url>
</urlset>
```

---

**10. Verify FAQ schema**

Search the source for the `FAQPage` JSON-LD block. Confirm the `name` and `text` values inside each Question and Answer object match the live FAQ text on the page exactly. If they match — no action needed. If they don't match — flag which question has a discrepancy and do not edit it.

---

After making all changes, show me a summary of what was changed and what was already correct so nothing was touched.
