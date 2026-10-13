---
name: seo
description: Search Engine Optimization specialist for content strategy, technical SEO, keyword research, and ranking improvements. Use when optimizing website content, improving search rankings, conducting keyword analysis, or implementing SEO best practices. Expert in on-page SEO, meta tags, schema markup, and Core Web Vitals. When the user wants to audit, review, or diagnose SEO issues on their site. Also use when the user mentions SEO audit, technical SEO, why am I not ranking, SEO issues, on-page SEO, meta tags review, or SEO health check. For building pages at scale to target keywords, see programmatic-seo. For adding structured data, see schema-markup. SEO fundamentals, E-E-A-T, Core Web Vitals, and Google algorithm principles. Optimize for search engine visibility and ranking. Use when asked to improve SEO, optimize for search, fix meta tags, add structured data, sitemap optimization, or search engine optimization.
---


# SEO Optimizer

Comprehensive guidance for search engine optimization across content, technical implementation, and strategic planning to improve organic search visibility and rankings.

## When to Use This Skill

Use this skill when:
- Optimizing website content for search engines
- Conducting keyword research and analysis
- Implementing technical SEO improvements
- Creating SEO-friendly meta tags and descriptions
- Auditing websites for SEO issues
- Improving Core Web Vitals and page speed
- Implementing schema markup (structured data)
- Planning content strategy for organic traffic

## SEO Fundamentals

### 1. Keyword Research & Strategy

**Primary Keyword Selection:**
- Focus on search intent (informational, navigational, transactional, commercial)
- Balance search volume with competition
- Consider keyword difficulty and ranking potential
- Target long-tail keywords for quick wins

**Keyword Research Process:**
```
1. Identify seed keywords from business objectives
2. Use tools to expand keyword list (Google Keyword Planner, Ahrefs, SEMrush)
3. Analyze search volume and difficulty
4. Group keywords by topic clusters
5. Map keywords to content types and pages
6. Prioritize based on potential ROI
```

**Content Optimization Formula:**
- Primary keyword: 1-2% density (natural placement)
- Include in: Title tag, H1, first paragraph, URL, meta description
- Use semantic variations and related terms
- Maintain natural readability (don't keyword stuff)

### 2. On-Page SEO

**Title Tag Optimization:**
```html
<!-- Good: Descriptive, includes keyword, under 60 characters -->
<title>Ultimate Guide to React Hooks - Learn useEffect & useState</title>

<!-- Bad: Too long, keyword stuffing, generic -->
<title>React Hooks Guide React Hooks Tutorial React Hooks Examples Learn React</title>
```

**Best Practices:**
- Keep under 60 characters (displayed in SERPs)
- Place primary keyword near the beginning
- Include brand name if space permits
- Make compelling and click-worthy
- Unique for every page

**Meta Description:**
```html
<!-- Good: Compelling, includes keywords, call-to-action, 150-160 chars -->
<meta name="description" content="Master React Hooks with our comprehensive guide. Learn useState, useEffect, and custom hooks with practical examples. Start building better React apps today.">

<!-- Bad: Too short, no value proposition -->
<meta name="description" content="React Hooks guide and tutorial">
```

**Header Structure:**
```html
<!-- Proper hierarchy -->
<h1>Main Page Title (Primary Keyword)</h1>
  <h2>Section Heading (Related Keywords)</h2>
    <h3>Subsection</h3>
    <h3>Subsection</h3>
  <h2>Another Section</h2>
    <h3>Subsection</h3>
```

**URL Structure:**
```
✅ Good URLs:
- /blog/react-hooks-guide
- /products/running-shoes
- /learn/javascript-async-await

❌ Bad URLs:
- /blog?p=12345
- /products/cat-1/subcat-2/item-999
- /page.php?id=abc&ref=xyz
```

**Image Optimization:**
```html
<!-- Optimized image -->
<img
  src="/images/react-hooks-diagram-800w.webp"
  alt="React Hooks lifecycle diagram showing useState and useEffect"
  width="800"
  height="600"
  loading="lazy"
/>
```

**Best Practices:**
- Use descriptive, keyword-rich alt text
- Compress images (WebP format preferred)
- Specify dimensions to prevent layout shift
- Use lazy loading for below-fold images
- Include captions when relevant

### 3. Content Quality

**E-E-A-T Principles (Experience, Expertise, Authoritativeness, Trust):**
- Demonstrate author expertise with credentials
- Cite authoritative sources
- Keep content accurate and up-to-date
- Show real experience and original insights
- Include author bios and bylines

**Content Structure for SEO:**
```markdown
# Main Title (H1) - Primary Keyword

Brief introduction with primary keyword in first 100 words.

## What is [Topic]? (H2) - Answer core question

Comprehensive explanation with examples.

## Why [Topic] Matters (H2) - Value proposition

Benefits and use cases.

## How to [Action] (H2) - Practical guide

Step-by-step instructions with visuals.

## Best Practices (H2) - Advanced tips

Expert recommendations.

## Common Mistakes to Avoid (H2)

Troubleshooting and pitfalls.

## Conclusion

Summary and call-to-action.
```

**Content Length Guidelines:**
- Blog posts: 1,500-2,500 words (comprehensive topics)
- Product pages: 300-500 words minimum
- Category pages: 500-1,000 words
- Homepage: 500+ words

### 4. Technical SEO

**Schema Markup (Structured Data):**
```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "Complete Guide to React Hooks",
  "image": "https://example.com/images/react-hooks.jpg",
  "datePublished": "2024-01-15",
  "dateModified": "2024-02-01",
  "author": {
    "@type": "Person",
    "name": "Jane Developer"
  },
  "publisher": {
    "@type": "Organization",
    "name": "Tech Academy",
    "logo": {
      "@type": "ImageObject",
      "url": "https://example.com/logo.png"
    }
  }
}
```

**Common Schema Types:**
- Article (blog posts)
- Product (e-commerce)
- FAQ (question/answer pages)
- HowTo (tutorials and guides)
- Organization (company info)
- LocalBusiness (location-based businesses)
- BreadcrumbList (navigation paths)
- Review/AggregateRating (ratings and reviews)

**Robots.txt Configuration:**
```
User-agent: *
Disallow: /admin/
Disallow: /private/
Disallow: /api/
Allow: /api/public/

Sitemap: https://example.com/sitemap.xml
```

**XML Sitemap Structure:**
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://example.com/</loc>
    <lastmod>2024-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://example.com/blog/react-hooks-guide</loc>
    <lastmod>2024-01-10</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
</urlset>
```

**Canonical Tags:**
```html
<!-- Prevent duplicate content issues -->
<link rel="canonical" href="https://example.com/original-page">

<!-- Handle URL parameters -->
<link rel="canonical" href="https://example.com/products/shoes">
<!-- Even if accessed via: /products/shoes?color=red&size=10 -->
```

### 5. Core Web Vitals

**Largest Contentful Paint (LCP) - Target: < 2.5s**
- Optimize images and videos
- Use CDN for static assets
- Minimize render-blocking resources
- Implement lazy loading

**First Input Delay (FID) - Target: < 100ms**
- Minimize JavaScript execution time
- Break up long tasks
- Use web workers for heavy computations
- Defer non-critical JavaScript

**Cumulative Layout Shift (CLS) - Target: < 0.1**
- Set size attributes on images and videos
- Avoid inserting content above existing content
- Use transform animations instead of layout-triggering properties
- Reserve space for ads and embeds

**Page Speed Optimization:**
```html
<!-- Preload critical resources -->
<link rel="preload" href="/fonts/main.woff2" as="font" crossorigin>

<!-- Defer non-critical CSS -->
<link rel="preload" href="/styles/non-critical.css" as="style" onload="this.onload=null;this.rel='stylesheet'">

<!-- Async/defer JavaScript -->
<script src="/js/analytics.js" async></script>
<script src="/js/main.js" defer></script>
```

### 6. Mobile SEO

**Mobile-First Optimization:**
- Responsive design (mobile-friendly test passed)
- Touch-friendly buttons (minimum 48x48px)
- Readable font sizes (16px minimum)
- Proper viewport configuration
- Fast mobile page speed

**Viewport Configuration:**
```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

### 7. Internal Linking Strategy

**Best Practices:**
- Use descriptive anchor text (avoid "click here")
- Link to relevant, contextual pages
- Maintain logical hierarchy and flow
- Include 3-5 internal links per 1,000 words
- Update old content with links to new content

**Example:**
```markdown
Learn more about [advanced React patterns](/guides/react-patterns)
or check out our [useState hook tutorial](/tutorials/usestate-guide).
```

## SEO Content Checklist

**Before Publishing:**
- [ ] Primary keyword in title tag (under 60 chars)
- [ ] Meta description (150-160 chars, compelling)
- [ ] H1 tag with primary keyword
- [ ] URL slug optimized and readable
- [ ] Images compressed with descriptive alt text
- [ ] 3-5 internal links to relevant content
- [ ] External links to authoritative sources
- [ ] Content length appropriate for topic depth
- [ ] Schema markup implemented
- [ ] Mobile-friendly and responsive
- [ ] Page speed optimized (< 3s load time)
- [ ] No broken links
- [ ] Canonical tag set correctly
- [ ] Social sharing meta tags (Open Graph, Twitter Card)

## Advanced SEO Strategies

### Topic Clusters & Pillar Pages

**Structure:**
```
Pillar Page: "Complete Guide to React"
  ├── Cluster: "React Hooks Tutorial"
  ├── Cluster: "React Context API Guide"
  ├── Cluster: "React Performance Optimization"
  └── Cluster: "React Testing Best Practices"
```

**Implementation:**
- Create comprehensive pillar content (3,000+ words)
- Develop 8-12 cluster articles supporting the pillar
- Link all clusters back to pillar page
- Link pillar page to all clusters
- Use consistent keyword themes

### Featured Snippet Optimization

**Question-Based Content:**
```markdown
## What is React?

React is a JavaScript library for building user interfaces,
developed by Facebook. It allows developers to create reusable
UI components and efficiently update the DOM through a virtual
DOM implementation.
```

**List-Based Content:**
```markdown
## Top 5 React Best Practices

1. Use functional components with hooks
2. Implement proper state management
3. Optimize performance with React.memo
4. Follow component composition patterns
5. Write comprehensive tests
```

**Table-Based Content:**
| Framework | Performance | Learning Curve | Ecosystem |
|-----------|-------------|----------------|-----------|
| React     | Excellent   | Moderate       | Extensive |
| Vue       | Excellent   | Easy           | Growing   |
| Angular   | Good        | Steep          | Mature    |

## Local SEO (for businesses with physical locations)

**Google Business Profile Optimization:**
- Complete all business information
- Regular posts and updates
- Respond to reviews
- Add high-quality photos
- Verify business hours

**Local Schema Markup:**
```json
{
  "@type": "LocalBusiness",
  "name": "Tech Solutions Inc",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "123 Main St",
    "addressLocality": "San Francisco",
    "addressRegion": "CA",
    "postalCode": "94102"
  },
  "telephone": "+1-415-555-0123"
}
```

## Monitoring & Analytics

**Key Metrics to Track:**
- Organic traffic trends
- Keyword rankings
- Click-through rates (CTR)
- Bounce rate and dwell time
- Core Web Vitals scores
- Backlink profile growth
- Conversion rates from organic traffic

**Tools:**
- Google Search Console (performance, indexing issues)
- Google Analytics 4 (traffic, behavior, conversions)
- PageSpeed Insights (Core Web Vitals)
- Ahrefs/SEMrush (keywords, backlinks, competition)
- Screaming Frog (technical audits)

When optimizing for SEO, prioritize user experience and value delivery. Search engines increasingly reward content that genuinely helps users and provides authoritative, trustworthy information.


---

<!-- merged-in: business-marketing/seo-audit, business-marketing/seo-fundamentals, development/seo -->


# Merged section: seo-audit (from business-marketing/seo-audit)
Supporting files from this skill live in `references/seo-audit/`, `scripts/seo-audit/`, `data/seo-audit/` (whichever exist).

# SEO Audit

You are an expert in search engine optimization. Your goal is to identify SEO issues and provide actionable recommendations to improve organic search performance.

## Initial Assessment

Before auditing, understand:

1. **Site Context**
   - What type of site? (SaaS, e-commerce, blog, etc.)
   - What's the primary business goal for SEO?
   - What keywords/topics are priorities?

2. **Current State**
   - Any known issues or concerns?
   - Current organic traffic level?
   - Recent changes or migrations?

3. **Scope**
   - Full site audit or specific pages?
   - Technical + on-page, or one focus area?
   - Access to Search Console / analytics?

---

## Audit Framework

### Priority Order
1. **Crawlability & Indexation** (can Google find and index it?)
2. **Technical Foundations** (is the site fast and functional?)
3. **On-Page Optimization** (is content optimized?)
4. **Content Quality** (does it deserve to rank?)
5. **Authority & Links** (does it have credibility?)

---

## Technical SEO Audit

### Crawlability

**Robots.txt**
- Check for unintentional blocks
- Verify important pages allowed
- Check sitemap reference

**XML Sitemap**
- Exists and accessible
- Submitted to Search Console
- Contains only canonical, indexable URLs
- Updated regularly
- Proper formatting

**Site Architecture**
- Important pages within 3 clicks of homepage
- Logical hierarchy
- Internal linking structure
- No orphan pages

**Crawl Budget Issues** (for large sites)
- Parameterized URLs under control
- Faceted navigation handled properly
- Infinite scroll with pagination fallback
- Session IDs not in URLs

### Indexation

**Index Status**
- site:domain.com check
- Search Console coverage report
- Compare indexed vs. expected

**Indexation Issues**
- Noindex tags on important pages
- Canonicals pointing wrong direction
- Redirect chains/loops
- Soft 404s
- Duplicate content without canonicals

**Canonicalization**
- All pages have canonical tags
- Self-referencing canonicals on unique pages
- HTTP → HTTPS canonicals
- www vs. non-www consistency
- Trailing slash consistency

### Site Speed & Core Web Vitals

**Core Web Vitals**
- LCP (Largest Contentful Paint): < 2.5s
- INP (Interaction to Next Paint): < 200ms
- CLS (Cumulative Layout Shift): < 0.1

**Speed Factors**
- Server response time (TTFB)
- Image optimization
- JavaScript execution
- CSS delivery
- Caching headers
- CDN usage
- Font loading

**Tools**
- PageSpeed Insights
- WebPageTest
- Chrome DevTools
- Search Console Core Web Vitals report

### Mobile-Friendliness

- Responsive design (not separate m. site)
- Tap target sizes
- Viewport configured
- No horizontal scroll
- Same content as desktop
- Mobile-first indexing readiness

### Security & HTTPS

- HTTPS across entire site
- Valid SSL certificate
- No mixed content
- HTTP → HTTPS redirects
- HSTS header (bonus)

### URL Structure

- Readable, descriptive URLs
- Keywords in URLs where natural
- Consistent structure
- No unnecessary parameters
- Lowercase and hyphen-separated

---

## On-Page SEO Audit

### Title Tags

**Check for:**
- Unique titles for each page
- Primary keyword near beginning
- 50-60 characters (visible in SERP)
- Compelling and click-worthy
- Brand name placement (end, usually)

**Common issues:**
- Duplicate titles
- Too long (truncated)
- Too short (wasted opportunity)
- Keyword stuffing
- Missing entirely

### Meta Descriptions

**Check for:**
- Unique descriptions per page
- 150-160 characters
- Includes primary keyword
- Clear value proposition
- Call to action

**Common issues:**
- Duplicate descriptions
- Auto-generated garbage
- Too long/short
- No compelling reason to click

### Heading Structure

**Check for:**
- One H1 per page
- H1 contains primary keyword
- Logical hierarchy (H1 → H2 → H3)
- Headings describe content
- Not just for styling

**Common issues:**
- Multiple H1s
- Skip levels (H1 → H3)
- Headings used for styling only
- No H1 on page

### Content Optimization

**Primary Page Content**
- Keyword in first 100 words
- Related keywords naturally used
- Sufficient depth/length for topic
- Answers search intent
- Better than competitors

**Thin Content Issues**
- Pages with little unique content
- Tag/category pages with no value
- Doorway pages
- Duplicate or near-duplicate content

### Image Optimization

**Check for:**
- Descriptive file names
- Alt text on all images
- Alt text describes image
- Compressed file sizes
- Modern formats (WebP)
- Lazy loading implemented
- Responsive images

### Internal Linking

**Check for:**
- Important pages well-linked
- Descriptive anchor text
- Logical link relationships
- No broken internal links
- Reasonable link count per page

**Common issues:**
- Orphan pages (no internal links)
- Over-optimized anchor text
- Important pages buried
- Excessive footer/sidebar links

### Keyword Targeting

**Per Page**
- Clear primary keyword target
- Title, H1, URL aligned
- Content satisfies search intent
- Not competing with other pages (cannibalization)

**Site-Wide**
- Keyword mapping document
- No major gaps in coverage
- No keyword cannibalization
- Logical topical clusters

---

## Content Quality Assessment

### E-E-A-T Signals

**Experience**
- First-hand experience demonstrated
- Original insights/data
- Real examples and case studies

**Expertise**
- Author credentials visible
- Accurate, detailed information
- Properly sourced claims

**Authoritativeness**
- Recognized in the space
- Cited by others
- Industry credentials

**Trustworthiness**
- Accurate information
- Transparent about business
- Contact information available
- Privacy policy, terms
- Secure site (HTTPS)

### Content Depth

- Comprehensive coverage of topic
- Answers follow-up questions
- Better than top-ranking competitors
- Updated and current

### User Engagement Signals

- Time on page
- Bounce rate in context
- Pages per session
- Return visits

---

## Common Issues by Site Type

### SaaS/Product Sites
- Product pages lack content depth
- Blog not integrated with product pages
- Missing comparison/alternative pages
- Feature pages thin on content
- No glossary/educational content

### E-commerce
- Thin category pages
- Duplicate product descriptions
- Missing product schema
- Faceted navigation creating duplicates
- Out-of-stock pages mishandled

### Content/Blog Sites
- Outdated content not refreshed
- Keyword cannibalization
- No topical clustering
- Poor internal linking
- Missing author pages

### Local Business
- Inconsistent NAP
- Missing local schema
- No Google Business Profile optimization
- Missing location pages
- No local content

---

## Output Format

### Audit Report Structure

**Executive Summary**
- Overall health assessment
- Top 3-5 priority issues
- Quick wins identified

**Technical SEO Findings**
For each issue:
- **Issue**: What's wrong
- **Impact**: SEO impact (High/Medium/Low)
- **Evidence**: How you found it
- **Fix**: Specific recommendation
- **Priority**: 1-5 or High/Medium/Low

**On-Page SEO Findings**
Same format as above

**Content Findings**
Same format as above

**Prioritized Action Plan**
1. Critical fixes (blocking indexation/ranking)
2. High-impact improvements
3. Quick wins (easy, immediate benefit)
4. Long-term recommendations

---

## Tools Referenced

**Free Tools**
- Google Search Console (essential)
- Google PageSpeed Insights
- Bing Webmaster Tools
- Rich Results Test
- Mobile-Friendly Test
- Schema Validator

**Paid Tools** (if available)
- Screaming Frog
- Ahrefs / Semrush
- Sitebulb
- ContentKing

---

## Questions to Ask

If you need more context:
1. What pages/keywords matter most?
2. Do you have Search Console access?
3. Any recent changes or migrations?
4. Who are your top organic competitors?
5. What's your current organic traffic baseline?

---

## Related Skills

- **programmatic-seo**: For building SEO pages at scale
- **schema-markup**: For implementing structured data
- **page-cro**: For optimizing pages for conversion (not just ranking)
- **analytics-tracking**: For measuring SEO performance


# Merged section: seo-fundamentals (from business-marketing/seo-fundamentals)
Supporting files from this skill live in `references/seo-fundamentals/`, `scripts/seo-fundamentals/`, `data/seo-fundamentals/` (whichever exist).

# SEO Fundamentals

> Principles for search engine visibility.

---

## 1. E-E-A-T Framework

| Principle | Signals |
|-----------|---------|
| **Experience** | First-hand knowledge, real examples |
| **Expertise** | Credentials, depth of knowledge |
| **Authoritativeness** | Backlinks, mentions, industry recognition |
| **Trustworthiness** | HTTPS, transparency, accurate info |

---

## 2. Core Web Vitals

| Metric | Target | Measures |
|--------|--------|----------|
| **LCP** | < 2.5s | Loading performance |
| **INP** | < 200ms | Interactivity |
| **CLS** | < 0.1 | Visual stability |

---

## 3. Technical SEO Principles

### Site Structure

| Element | Purpose |
|---------|---------|
| XML sitemap | Help crawling |
| robots.txt | Control access |
| Canonical tags | Prevent duplicates |
| HTTPS | Security signal |

### Performance

| Factor | Impact |
|--------|--------|
| Page speed | Core Web Vital |
| Mobile-friendly | Ranking factor |
| Clean URLs | Crawlability |

---

## 4. Content SEO Principles

### Page Elements

| Element | Best Practice |
|---------|---------------|
| Title tag | 50-60 chars, keyword front |
| Meta description | 150-160 chars, compelling |
| H1 | One per page, main keyword |
| H2-H6 | Logical hierarchy |
| Alt text | Descriptive, not stuffed |

### Content Quality

| Factor | Importance |
|--------|------------|
| Depth | Comprehensive coverage |
| Freshness | Regular updates |
| Uniqueness | Original value |
| Readability | Clear writing |

---

## 5. Schema Markup Types

| Type | Use |
|------|-----|
| Article | Blog posts, news |
| Organization | Company info |
| Person | Author profiles |
| FAQPage | Q&A content |
| Product | E-commerce |
| Review | Ratings |
| BreadcrumbList | Navigation |

---

## 6. AI Content Guidelines

### What Google Looks For

| ✅ Do | ❌ Don't |
|-------|----------|
| AI draft + human edit | Publish raw AI content |
| Add original insights | Copy without value |
| Expert review | Skip fact-checking |
| Follow E-E-A-T | Keyword stuffing |

---

## 7. Ranking Factors (Prioritized)

| Priority | Factor |
|----------|--------|
| 1 | Quality, relevant content |
| 2 | Backlinks from authority sites |
| 3 | Page experience (Core Web Vitals) |
| 4 | Mobile optimization |
| 5 | Technical SEO fundamentals |

---

## 8. Measurement

| Metric | Tool |
|--------|------|
| Rankings | Search Console, Ahrefs |
| Traffic | Analytics |
| Core Web Vitals | PageSpeed Insights |
| Indexing | Search Console |
| Backlinks | Ahrefs, Semrush |

---

> **Remember:** SEO is a long-term game. Quality content + technical excellence + patience = results.


# Merged section: seo (from development/seo)
Supporting files from this skill live in `references/seo/`, `scripts/seo/`, `data/seo/` (whichever exist).

# SEO optimization

Search engine optimization based on Lighthouse SEO audits and Google Search guidelines. Focus on technical SEO, on-page optimization, and structured data.

## SEO fundamentals

Search ranking factors (approximate influence):

| Factor | Influence | This Skill |
|--------|-----------|------------|
| Content quality & relevance | ~40% | Partial (structure) |
| Backlinks & authority | ~25% | ✗ |
| Technical SEO | ~15% | ✓ |
| Page experience (Core Web Vitals) | ~10% | See [Core Web Vitals](../core-web-vitals/SKILL.md) |
| On-page SEO | ~10% | ✓ |

---

## Technical SEO

### Crawlability

**robots.txt:**
```text
# /robots.txt
User-agent: *
Allow: /

# Block admin/private areas
Disallow: /admin/
Disallow: /api/
Disallow: /private/

# Don't block resources needed for rendering
# ❌ Disallow: /static/

Sitemap: https://example.com/sitemap.xml
```

**Meta robots:**
```html
<!-- Default: indexable, followable -->
<meta name="robots" content="index, follow">

<!-- Noindex specific pages -->
<meta name="robots" content="noindex, nofollow">

<!-- Indexable but don't follow links -->
<meta name="robots" content="index, nofollow">

<!-- Control snippets -->
<meta name="robots" content="max-snippet:150, max-image-preview:large">
```

**Canonical URLs:**
```html
<!-- Prevent duplicate content issues -->
<link rel="canonical" href="https://example.com/page">

<!-- Self-referencing canonical (recommended) -->
<link rel="canonical" href="https://example.com/current-page">

<!-- For paginated content -->
<link rel="canonical" href="https://example.com/products">
<!-- Or use rel="prev" / rel="next" for explicit pagination -->
```

### XML sitemap

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://example.com/</loc>
    <lastmod>2024-01-15</lastmod>
    <changefreq>daily</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://example.com/products</loc>
    <lastmod>2024-01-14</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.8</priority>
  </url>
</urlset>
```

**Sitemap best practices:**
- Maximum 50,000 URLs or 50MB per sitemap
- Use sitemap index for larger sites
- Include only canonical, indexable URLs
- Update `lastmod` when content changes
- Submit to Google Search Console

### URL structure

```
✅ Good URLs:
https://example.com/products/blue-widget
https://example.com/blog/how-to-use-widgets

❌ Poor URLs:
https://example.com/p?id=12345
https://example.com/products/item/category/subcategory/blue-widget-2024-sale-discount
```

**URL guidelines:**
- Use hyphens, not underscores
- Lowercase only
- Keep short (< 75 characters)
- Include target keywords naturally
- Avoid parameters when possible
- Use HTTPS always

### HTTPS & security

```html
<!-- Ensure all resources use HTTPS -->
<img src="https://example.com/image.jpg">

<!-- Not: -->
<img src="http://example.com/image.jpg">
```

**Security headers for SEO trust signals:**
```
Strict-Transport-Security: max-age=31536000; includeSubDomains
X-Content-Type-Options: nosniff
X-Frame-Options: DENY
```

---

## On-page SEO

### Title tags

```html
<!-- ❌ Missing or generic -->
<title>Page</title>
<title>Home</title>

<!-- ✅ Descriptive with primary keyword -->
<title>Blue Widgets for Sale | Premium Quality | Example Store</title>
```

**Title tag guidelines:**
- 50-60 characters (Google truncates ~60)
- Primary keyword near the beginning
- Unique for every page
- Brand name at end (unless homepage)
- Action-oriented when appropriate

### Meta descriptions

```html
<!-- ❌ Missing or duplicate -->
<meta name="description" content="">

<!-- ✅ Compelling and unique -->
<meta name="description" content="Shop premium blue widgets with free shipping. 30-day returns. Rated 4.9/5 by 10,000+ customers. Order today and save 20%.">
```

**Meta description guidelines:**
- 150-160 characters
- Include primary keyword naturally
- Compelling call-to-action
- Unique for every page
- Matches page content

### Heading structure

```html
<!-- ❌ Poor structure -->
<h2>Welcome to Our Store</h2>
<h4>Products</h4>
<h1>Contact Us</h1>

<!-- ✅ Proper hierarchy -->
<h1>Blue Widgets - Premium Quality</h1>
  <h2>Product Features</h2>
    <h3>Durability</h3>
    <h3>Design</h3>
  <h2>Customer Reviews</h2>
  <h2>Pricing</h2>
```

**Heading guidelines:**
- Single `<h1>` per page (the main topic)
- Logical hierarchy (don't skip levels)
- Include keywords naturally
- Descriptive, not generic

### Image SEO

```html
<!-- ❌ Poor image SEO -->
<img src="IMG_12345.jpg">

<!-- ✅ Optimized image -->
<img src="blue-widget-product-photo.webp"
     alt="Blue widget with chrome finish, side view showing control panel"
     width="800"
     height="600"
     loading="lazy">
```

**Image guidelines:**
- Descriptive filenames with keywords
- Alt text describes the image content
- Compressed and properly sized
- WebP/AVIF with fallbacks
- Lazy load below-fold images

### Internal linking

```html
<!-- ❌ Non-descriptive -->
<a href="/products">Click here</a>
<a href="/widgets">Read more</a>

<!-- ✅ Descriptive anchor text -->
<a href="/products/blue-widgets">Browse our blue widget collection</a>
<a href="/guides/widget-maintenance">Learn how to maintain your widgets</a>
```

**Linking guidelines:**
- Descriptive anchor text with keywords
- Link to relevant internal pages
- Reasonable number of links per page
- Fix broken links promptly
- Use breadcrumbs for hierarchy

---

## Structured data (JSON-LD)

### Organization

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Example Company",
  "url": "https://example.com",
  "logo": "https://example.com/logo.png",
  "sameAs": [
    "https://twitter.com/example",
    "https://linkedin.com/company/example"
  ],
  "contactPoint": {
    "@type": "ContactPoint",
    "telephone": "+1-555-123-4567",
    "contactType": "customer service"
  }
}
</script>
```

### Article

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "How to Choose the Right Widget",
  "description": "Complete guide to selecting widgets for your needs.",
  "image": "https://example.com/article-image.jpg",
  "author": {
    "@type": "Person",
    "name": "Jane Smith",
    "url": "https://example.com/authors/jane-smith"
  },
  "publisher": {
    "@type": "Organization",
    "name": "Example Blog",
    "logo": {
      "@type": "ImageObject",
      "url": "https://example.com/logo.png"
    }
  },
  "datePublished": "2024-01-15",
  "dateModified": "2024-01-20"
}
</script>
```

### Product

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Blue Widget Pro",
  "image": "https://example.com/blue-widget.jpg",
  "description": "Premium blue widget with advanced features.",
  "brand": {
    "@type": "Brand",
    "name": "WidgetCo"
  },
  "offers": {
    "@type": "Offer",
    "price": "49.99",
    "priceCurrency": "USD",
    "availability": "https://schema.org/InStock",
    "url": "https://example.com/products/blue-widget"
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.8",
    "reviewCount": "1250"
  }
}
</script>
```

### FAQ

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "What colors are available?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Our widgets come in blue, red, and green."
      }
    },
    {
      "@type": "Question",
      "name": "What is the warranty?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "All widgets include a 2-year warranty."
      }
    }
  ]
}
</script>
```

### Breadcrumbs

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Home",
      "item": "https://example.com"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "Products",
      "item": "https://example.com/products"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "Blue Widgets",
      "item": "https://example.com/products/blue-widgets"
    }
  ]
}
</script>
```

### Validation

Test structured data at:
- [Google Rich Results Test](https://search.google.com/test/rich-results)
- [Schema.org Validator](https://validator.schema.org/)

---

## Mobile SEO

### Responsive design

```html
<!-- ❌ Not mobile-friendly -->
<meta name="viewport" content="width=1024">

<!-- ✅ Responsive viewport -->
<meta name="viewport" content="width=device-width, initial-scale=1">
```

### Tap targets

```css
/* ❌ Too small for mobile */
.small-link {
  padding: 4px;
  font-size: 12px;
}

/* ✅ Adequate tap target */
.mobile-friendly-link {
  padding: 12px;
  font-size: 16px;
  min-height: 48px;
  min-width: 48px;
}
```

### Font sizes

```css
/* ❌ Too small on mobile */
body {
  font-size: 10px;
}

/* ✅ Readable without zooming */
body {
  font-size: 16px;
  line-height: 1.5;
}
```

---

## International SEO

### Hreflang tags

```html
<!-- For multi-language sites -->
<link rel="alternate" hreflang="en" href="https://example.com/page">
<link rel="alternate" hreflang="es" href="https://example.com/es/page">
<link rel="alternate" hreflang="fr" href="https://example.com/fr/page">
<link rel="alternate" hreflang="x-default" href="https://example.com/page">
```

### Language declaration

```html
<html lang="en">
<!-- or -->
<html lang="es-MX">
```

---

## SEO audit checklist

### Critical
- [ ] HTTPS enabled
- [ ] robots.txt allows crawling
- [ ] No `noindex` on important pages
- [ ] Title tags present and unique
- [ ] Single `<h1>` per page

### High priority
- [ ] Meta descriptions present
- [ ] Sitemap submitted
- [ ] Canonical URLs set
- [ ] Mobile-responsive
- [ ] Core Web Vitals passing

### Medium priority
- [ ] Structured data implemented
- [ ] Internal linking strategy
- [ ] Image alt text
- [ ] Descriptive URLs
- [ ] Breadcrumb navigation

### Ongoing
- [ ] Fix crawl errors in Search Console
- [ ] Update sitemap when content changes
- [ ] Monitor ranking changes
- [ ] Check for broken links
- [ ] Review Search Console insights

---

## Tools

| Tool | Use |
|------|-----|
| Google Search Console | Monitor indexing, fix issues |
| Google PageSpeed Insights | Performance + Core Web Vitals |
| Rich Results Test | Validate structured data |
| Lighthouse | Full SEO audit |
| Screaming Frog | Crawl analysis |

## References

- [Google Search Central](https://developers.google.com/search)
- [Schema.org](https://schema.org/)
- [Core Web Vitals](../core-web-vitals/SKILL.md)
- [Web Quality Audit](../web-quality-audit/SKILL.md)
