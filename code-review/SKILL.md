---
name: code-review
description: Comprehensive code review skill for TypeScript, JavaScript, Python, Swift, Kotlin, Go. Includes automated code analysis, best practice checking, security scanning, and review checklist generation. Use when reviewing pull requests, providing code feedback, identifying issues, or ensuring code quality standards. Find bugs, security vulnerabilities, and code quality issues in local branch changes. Use when asked to review changes, find bugs, security review, or audit code on the current branch. Pragmatic coding standards - concise, direct, no over-engineering, no unnecessary comments Comprehensive web quality audit covering performance, accessibility, SEO, and best practices. Use when asked to audit my site, review web quality, run lighthouse audit, check page quality, or optimize my website. Optimize Core Web Vitals (LCP, INP, CLS) for better page experience and search ranking. Use when asked to improve Core Web Vitals, fix LCP, reduce CLS, optimize INP, page experience optimization, or fix layout shifts.
---


# Code Reviewer

Complete toolkit for code reviewer with modern tools and best practices.

## Quick Start

### Main Capabilities

This skill provides three core capabilities through automated scripts:

```bash
# Script 1: Pr Analyzer
python scripts/pr_analyzer.py [options]

# Script 2: Code Quality Checker
python scripts/code_quality_checker.py [options]

# Script 3: Review Report Generator
python scripts/review_report_generator.py [options]
```

## Core Capabilities

### 1. Pr Analyzer

Automated tool for pr analyzer tasks.

**Features:**
- Automated scaffolding
- Best practices built-in
- Configurable templates
- Quality checks

**Usage:**
```bash
python scripts/pr_analyzer.py <project-path> [options]
```

### 2. Code Quality Checker

Comprehensive analysis and optimization tool.

**Features:**
- Deep analysis
- Performance metrics
- Recommendations
- Automated fixes

**Usage:**
```bash
python scripts/code_quality_checker.py <target-path> [--verbose]
```

### 3. Review Report Generator

Advanced tooling for specialized tasks.

**Features:**
- Expert-level automation
- Custom configurations
- Integration ready
- Production-grade output

**Usage:**
```bash
python scripts/review_report_generator.py [arguments] [options]
```

## Reference Documentation

### Code Review Checklist

Comprehensive guide available in `references/code_review_checklist.md`:

- Detailed patterns and practices
- Code examples
- Best practices
- Anti-patterns to avoid
- Real-world scenarios

### Coding Standards

Complete workflow documentation in `references/coding_standards.md`:

- Step-by-step processes
- Optimization strategies
- Tool integrations
- Performance tuning
- Troubleshooting guide

### Common Antipatterns

Technical reference guide in `references/common_antipatterns.md`:

- Technology stack details
- Configuration examples
- Integration patterns
- Security considerations
- Scalability guidelines

## Tech Stack

**Languages:** TypeScript, JavaScript, Python, Go, Swift, Kotlin
**Frontend:** React, Next.js, React Native, Flutter
**Backend:** Node.js, Express, GraphQL, REST APIs
**Database:** PostgreSQL, Prisma, NeonDB, Supabase
**DevOps:** Docker, Kubernetes, Terraform, GitHub Actions, CircleCI
**Cloud:** AWS, GCP, Azure

## Development Workflow

### 1. Setup and Configuration

```bash
# Install dependencies
npm install
# or
pip install -r requirements.txt

# Configure environment
cp .env.example .env
```

### 2. Run Quality Checks

```bash
# Use the analyzer script
python scripts/code_quality_checker.py .

# Review recommendations
# Apply fixes
```

### 3. Implement Best Practices

Follow the patterns and practices documented in:
- `references/code_review_checklist.md`
- `references/coding_standards.md`
- `references/common_antipatterns.md`

## Best Practices Summary

### Code Quality
- Follow established patterns
- Write comprehensive tests
- Document decisions
- Review regularly

### Performance
- Measure before optimizing
- Use appropriate caching
- Optimize critical paths
- Monitor in production

### Security
- Validate all inputs
- Use parameterized queries
- Implement proper authentication
- Keep dependencies updated

### Maintainability
- Write clear code
- Use consistent naming
- Add helpful comments
- Keep it simple

## Common Commands

```bash
# Development
npm run dev
npm run build
npm run test
npm run lint

# Analysis
python scripts/code_quality_checker.py .
python scripts/review_report_generator.py --analyze

# Deployment
docker build -t app:latest .
docker-compose up -d
kubectl apply -f k8s/
```

## Troubleshooting

### Common Issues

Check the comprehensive troubleshooting section in `references/common_antipatterns.md`.

### Getting Help

- Review reference documentation
- Check script output messages
- Consult tech stack documentation
- Review error logs

## Resources

- Pattern Reference: `references/code_review_checklist.md`
- Workflow Guide: `references/coding_standards.md`
- Technical Guide: `references/common_antipatterns.md`
- Tool Scripts: `scripts/` directory


---

<!-- merged-in: sentry/find-bugs, development/clean-code, development/web-quality-audit, development/core-web-vitals -->


# Merged section: find-bugs (from sentry/find-bugs)
Supporting files from this skill live in `references/find-bugs/`, `scripts/find-bugs/`, `data/find-bugs/` (whichever exist).

# Find Bugs

Review changes on this branch for bugs, security vulnerabilities, and code quality issues.

## Phase 1: Complete Input Gathering

1. Get the FULL diff: `git diff master...HEAD`
2. If output is truncated, read each changed file individually until you have seen every changed line
3. List all files modified in this branch before proceeding

## Phase 2: Attack Surface Mapping

For each changed file, identify and list:

* All user inputs (request params, headers, body, URL components)
* All database queries
* All authentication/authorization checks
* All session/state operations
* All external calls
* All cryptographic operations

## Phase 3: Security Checklist (check EVERY item for EVERY file)

* [ ] **Injection**: SQL, command, template, header injection
* [ ] **XSS**: All outputs in templates properly escaped?
* [ ] **Authentication**: Auth checks on all protected operations?
* [ ] **Authorization/IDOR**: Access control verified, not just auth?
* [ ] **CSRF**: State-changing operations protected?
* [ ] **Race conditions**: TOCTOU in any read-then-write patterns?
* [ ] **Session**: Fixation, expiration, secure flags?
* [ ] **Cryptography**: Secure random, proper algorithms, no secrets in logs?
* [ ] **Information disclosure**: Error messages, logs, timing attacks?
* [ ] **DoS**: Unbounded operations, missing rate limits, resource exhaustion?
* [ ] **Business logic**: Edge cases, state machine violations, numeric overflow?

## Phase 4: Verification

For each potential issue:

* Check if it's already handled elsewhere in the changed code
* Search for existing tests covering the scenario
* Read surrounding context to verify the issue is real

## Phase 5: Pre-Conclusion Audit

Before finalizing, you MUST:

1. List every file you reviewed and confirm you read it completely
2. List every checklist item and note whether you found issues or confirmed it's clean
3. List any areas you could NOT fully verify and why
4. Only then provide your final findings

## Output Format

**Prioritize**: security vulnerabilities > bugs > code quality

**Skip**: stylistic/formatting issues

For each issue:

* **File:Line** - Brief description
* **Severity**: Critical/High/Medium/Low
* **Problem**: What's wrong
* **Evidence**: Why this is real (not already fixed, no existing test, etc.)
* **Fix**: Concrete suggestion
* **References**: OWASP, RFCs, or other standards if applicable

If you find nothing significant, say so - don't invent issues.

Do not make changes - just report findings. I'll decide what to address.


# Merged section: clean-code (from development/clean-code)
Supporting files from this skill live in `references/clean-code/`, `scripts/clean-code/`, `data/clean-code/` (whichever exist).

# Clean Code - Pragmatic AI Coding Standards

> **CRITICAL SKILL** - Be **concise, direct, and solution-focused**.

---

## Core Principles

| Principle | Rule |
|-----------|------|
| **SRP** | Single Responsibility - each function/class does ONE thing |
| **DRY** | Don't Repeat Yourself - extract duplicates, reuse |
| **KISS** | Keep It Simple - simplest solution that works |
| **YAGNI** | You Aren't Gonna Need It - don't build unused features |
| **Boy Scout** | Leave code cleaner than you found it |

---

## Naming Rules

| Element | Convention |
|---------|------------|
| **Variables** | Reveal intent: `userCount` not `n` |
| **Functions** | Verb + noun: `getUserById()` not `user()` |
| **Booleans** | Question form: `isActive`, `hasPermission`, `canEdit` |
| **Constants** | SCREAMING_SNAKE: `MAX_RETRY_COUNT` |

> **Rule:** If you need a comment to explain a name, rename it.

---

## Function Rules

| Rule | Description |
|------|-------------|
| **Small** | Max 20 lines, ideally 5-10 |
| **One Thing** | Does one thing, does it well |
| **One Level** | One level of abstraction per function |
| **Few Args** | Max 3 arguments, prefer 0-2 |
| **No Side Effects** | Don't mutate inputs unexpectedly |

---

## Code Structure

| Pattern | Apply |
|---------|-------|
| **Guard Clauses** | Early returns for edge cases |
| **Flat > Nested** | Avoid deep nesting (max 2 levels) |
| **Composition** | Small functions composed together |
| **Colocation** | Keep related code close |

---

## AI Coding Style

| Situation | Action |
|-----------|--------|
| User asks for feature | Write it directly |
| User reports bug | Fix it, don't explain |
| No clear requirement | Ask, don't assume |

---

## Anti-Patterns (DON'T)

| ❌ Pattern | ✅ Fix |
|-----------|-------|
| Comment every line | Delete obvious comments |
| Helper for one-liner | Inline the code |
| Factory for 2 objects | Direct instantiation |
| utils.ts with 1 function | Put code where used |
| "First we import..." | Just write code |
| Deep nesting | Guard clauses |
| Magic numbers | Named constants |
| God functions | Split by responsibility |

---

## 🔴 Before Editing ANY File (THINK FIRST!)

**Before changing a file, ask yourself:**

| Question | Why |
|----------|-----|
| **What imports this file?** | They might break |
| **What does this file import?** | Interface changes |
| **What tests cover this?** | Tests might fail |
| **Is this a shared component?** | Multiple places affected |

**Quick Check:**
```
File to edit: UserService.ts
└── Who imports this? → UserController.ts, AuthController.ts
└── Do they need changes too? → Check function signatures
```

> 🔴 **Rule:** Edit the file + all dependent files in the SAME task.
> 🔴 **Never leave broken imports or missing updates.**

---

## Summary

| Do | Don't |
|----|-------|
| Write code directly | Write tutorials |
| Let code self-document | Add obvious comments |
| Fix bugs immediately | Explain the fix first |
| Inline small things | Create unnecessary files |
| Name things clearly | Use abbreviations |
| Keep functions small | Write 100+ line functions |

> **Remember: The user wants working code, not a programming lesson.**

---

## 🔴 Self-Check Before Completing (MANDATORY)

**Before saying "task complete", verify:**

| Check | Question |
|-------|----------|
| ✅ **Goal met?** | Did I do exactly what user asked? |
| ✅ **Files edited?** | Did I modify all necessary files? |
| ✅ **Code works?** | Did I test/verify the change? |
| ✅ **No errors?** | Lint and TypeScript pass? |
| ✅ **Nothing forgotten?** | Any edge cases missed? |

> 🔴 **Rule:** If ANY check fails, fix it before completing.

---

## Verification Scripts (MANDATORY)

> 🔴 **CRITICAL:** Each agent runs ONLY their own skill's scripts after completing work.

### Agent → Script Mapping

| Agent | Script | Command |
|-------|--------|---------|
| **frontend-specialist** | UX Audit | `python ~/.claude/skills/frontend-design/scripts/ux_audit.py .` |
| **frontend-specialist** | A11y Check | `python ~/.claude/skills/frontend-design/scripts/accessibility_checker.py .` |
| **backend-specialist** | API Validator | `python ~/.claude/skills/api-patterns/scripts/api_validator.py .` |
| **mobile-developer** | Mobile Audit | `python ~/.claude/skills/mobile-design/scripts/mobile_audit.py .` |
| **database-architect** | Schema Validate | `python ~/.claude/skills/database-design/scripts/schema_validator.py .` |
| **security-auditor** | Security Scan | `python ~/.claude/skills/vulnerability-scanner/scripts/security_scan.py .` |
| **seo-specialist** | SEO Check | `python ~/.claude/skills/seo-fundamentals/scripts/seo_checker.py .` |
| **seo-specialist** | GEO Check | `python ~/.claude/skills/geo-fundamentals/scripts/geo_checker.py .` |
| **performance-optimizer** | Lighthouse | `python ~/.claude/skills/performance-profiling/scripts/lighthouse_audit.py <url>` |
| **test-engineer** | Test Runner | `python ~/.claude/skills/testing-patterns/scripts/test_runner.py .` |
| **test-engineer** | Playwright | `python ~/.claude/skills/webapp-testing/scripts/playwright_runner.py <url>` |
| **Any agent** | Lint Check | `python ~/.claude/skills/lint-and-validate/scripts/lint_runner.py .` |
| **Any agent** | Type Coverage | `python ~/.claude/skills/lint-and-validate/scripts/type_coverage.py .` |
| **Any agent** | i18n Check | `python ~/.claude/skills/i18n-localization/scripts/i18n_checker.py .` |

> ❌ **WRONG:** `test-engineer` running `ux_audit.py`
> ✅ **CORRECT:** `frontend-specialist` running `ux_audit.py`

---

### 🔴 Script Output Handling (READ → SUMMARIZE → ASK)

**When running a validation script, you MUST:**

1. **Run the script** and capture ALL output
2. **Parse the output** - identify errors, warnings, and passes
3. **Summarize to user** in this format:

```markdown
## Script Results: [script_name.py]

### ❌ Errors Found (X items)
- [File:Line] Error description 1
- [File:Line] Error description 2

### ⚠️ Warnings (Y items)
- [File:Line] Warning description

### ✅ Passed (Z items)
- Check 1 passed
- Check 2 passed

**Should I fix the X errors?**
```

4. **Wait for user confirmation** before fixing
5. **After fixing** → Re-run script to confirm

> 🔴 **VIOLATION:** Running script and ignoring output = FAILED task.
> 🔴 **VIOLATION:** Auto-fixing without asking = Not allowed.
> 🔴 **Rule:** Always READ output → SUMMARIZE → ASK → then fix.


# Merged section: web-quality-audit (from development/web-quality-audit)
Supporting files from this skill live in `references/web-quality-audit/`, `scripts/web-quality-audit/`, `data/web-quality-audit/` (whichever exist).

# Web quality audit

Comprehensive quality review based on Google Lighthouse audits. Covers Performance, Accessibility, SEO, and Best Practices across 150+ checks.

## How it works

1. Analyze the provided code/project for quality issues
2. Categorize findings by severity (Critical, High, Medium, Low)
3. Provide specific, actionable recommendations
4. Include code examples for fixes

## Audit categories

### Performance (40% of typical issues)

**Core Web Vitals** — Must pass for good page experience:
* **LCP (Largest Contentful Paint) < 2.5s.** The largest visible element must render quickly. Optimize images, fonts, and server response time.
* **INP (Interaction to Next Paint) < 200ms.** User interactions must feel instant. Reduce JavaScript execution time and break up long tasks.
* **CLS (Cumulative Layout Shift) < 0.1.** Content must not jump around. Set explicit dimensions on images, embeds, and ads.

**Resource Optimization:**
* **Compress images.** Use WebP/AVIF with fallbacks. Serve correctly sized images via `srcset`.
* **Minimize JavaScript.** Remove unused code. Use code splitting. Defer non-critical scripts.
* **Optimize CSS.** Extract critical CSS. Remove unused styles. Avoid `@import`.
* **Efficient fonts.** Use `font-display: swap`. Preload critical fonts. Subset to needed characters.

**Loading Strategy:**
* **Preconnect to origins.** Add `<link rel="preconnect">` for third-party domains.
* **Preload critical assets.** LCP images, fonts, and above-fold CSS.
* **Lazy load below-fold content.** Images, iframes, and heavy components.
* **Cache effectively.** Long cache TTLs for static assets. Immutable caching for hashed files.

### Accessibility (30% of typical issues)

**Perceivable:**
* **Text alternatives.** Every `<img>` has meaningful `alt` text. Decorative images use `alt=""`.
* **Color contrast.** Minimum 4.5:1 for normal text, 3:1 for large text (WCAG AA).
* **Don't rely on color alone.** Use icons, patterns, or text alongside color indicators.
* **Captions and transcripts.** Video has captions. Audio has transcripts.

**Operable:**
* **Keyboard accessible.** All functionality available via keyboard. No keyboard traps.
* **Focus visible.** Clear focus indicators on all interactive elements.
* **Skip links.** Provide "Skip to main content" for keyboard users.
* **Sufficient time.** Users can extend time limits. No auto-advancing content without controls.

**Understandable:**
* **Page language.** Set `lang` attribute on `<html>`.
* **Consistent navigation.** Same navigation structure across pages.
* **Error identification.** Form errors clearly described and associated with fields.
* **Labels and instructions.** All form inputs have associated labels.

**Robust:**
* **Valid HTML.** No duplicate IDs. Properly nested elements.
* **ARIA used correctly.** Prefer native elements. ARIA roles match behavior.
* **Name, role, value.** Interactive elements have accessible names and correct roles.

### SEO (15% of typical issues)

**Crawlability:**
* **Valid robots.txt.** Doesn't block important resources.
* **XML sitemap.** Lists all important pages. Submitted to Search Console.
* **Canonical URLs.** Prevent duplicate content issues.
* **No noindex on important pages.** Check meta robots and headers.

**On-Page SEO:**
* **Unique title tags.** 50-60 characters. Primary keyword included.
* **Meta descriptions.** 150-160 characters. Compelling and unique.
* **Heading hierarchy.** Single `<h1>`. Logical heading structure.
* **Descriptive link text.** Not "click here" or "read more".

**Technical SEO:**
* **Mobile-friendly.** Responsive design. Tap targets ≥ 48px.
* **HTTPS.** Secure connection required.
* **Fast loading.** Performance directly impacts ranking.
* **Structured data.** JSON-LD for rich snippets (Article, Product, FAQ, etc.).

### Best practices (15% of typical issues)

**Security:**
* **HTTPS everywhere.** No mixed content. HSTS enabled.
* **No vulnerable libraries.** Keep dependencies updated.
* **CSP headers.** Content Security Policy to prevent XSS.
* **No exposed source maps.** In production builds.

**Modern Standards:**
* **No deprecated APIs.** Replace `document.write`, synchronous XHR, etc.
* **Valid doctype.** Use `<!DOCTYPE html>`.
* **Charset declared.** `<meta charset="UTF-8">` as first element in `<head>`.
* **No browser errors.** Clean console. No CORS issues.

**UX Patterns:**
* **No intrusive interstitials.** Especially on mobile.
* **Clear permission requests.** Only ask when needed, with context.
* **No misleading buttons.** Buttons do what they say.

## Severity levels

| Level | Description | Action |
|-------|-------------|--------|
| **Critical** | Security vulnerabilities, complete failures | Fix immediately |
| **High** | Core Web Vitals failures, major a11y barriers | Fix before launch |
| **Medium** | Performance opportunities, SEO improvements | Fix within sprint |
| **Low** | Minor optimizations, code quality | Fix when convenient |

## Audit output format

When performing an audit, structure findings as:

```markdown
## Audit results

### Critical issues (X found)
- **[Category]** Issue description. File: `path/to/file.js:123`
  - **Impact:** Why this matters
  - **Fix:** Specific code change or recommendation

### High priority (X found)
...

### Summary
- Performance: X issues (Y critical)
- Accessibility: X issues (Y critical)
- SEO: X issues
- Best Practices: X issues

### Recommended priority
1. First fix this because...
2. Then address...
3. Finally optimize...
```

## Quick checklist

### Before every deploy
- [ ] Core Web Vitals passing
- [ ] No accessibility errors (axe/Lighthouse)
- [ ] No console errors
- [ ] HTTPS working
- [ ] Meta tags present

### Weekly review
- [ ] Check Search Console for issues
- [ ] Review Core Web Vitals trends
- [ ] Update dependencies
- [ ] Test with screen reader

### Monthly deep dive
- [ ] Full Lighthouse audit
- [ ] Performance profiling
- [ ] Accessibility audit with real users
- [ ] SEO keyword review

## References

For detailed guidelines on specific areas:
- [Performance Optimization](../performance/SKILL.md)
- [Core Web Vitals](../core-web-vitals/SKILL.md)
- [Accessibility](../accessibility/SKILL.md)
- [SEO](../seo/SKILL.md)
- [Best Practices](../best-practices/SKILL.md)


# Merged section: core-web-vitals (from development/core-web-vitals)
Supporting files from this skill live in `references/core-web-vitals/`, `scripts/core-web-vitals/`, `data/core-web-vitals/` (whichever exist).

# Core Web Vitals optimization

Targeted optimization for the three Core Web Vitals metrics that affect Google Search ranking and user experience.

## The three metrics

| Metric | Measures | Good | Needs work | Poor |
|--------|----------|------|------------|------|
| **LCP** | Loading | ≤ 2.5s | 2.5s – 4s | > 4s |
| **INP** | Interactivity | ≤ 200ms | 200ms – 500ms | > 500ms |
| **CLS** | Visual Stability | ≤ 0.1 | 0.1 – 0.25 | > 0.25 |

Google measures at the **75th percentile** — 75% of page visits must meet "Good" thresholds.

---

## LCP: Largest Contentful Paint

LCP measures when the largest visible content element renders. Usually this is:
- Hero image or video
- Large text block
- Background image
- `<svg>` element

### Common LCP issues

**1. Slow server response (TTFB > 800ms)**
```
Fix: CDN, caching, optimized backend, edge rendering
```

**2. Render-blocking resources**
```html
<!-- ❌ Blocks rendering -->
<link rel="stylesheet" href="/all-styles.css">

<!-- ✅ Critical CSS inlined, rest deferred -->
<style>/* Critical above-fold CSS */</style>
<link rel="preload" href="/styles.css" as="style" 
      onload="this.onload=null;this.rel='stylesheet'">
```

**3. Slow resource load times**
```html
<!-- ❌ No hints, discovered late -->
<img src="/hero.jpg" alt="Hero">

<!-- ✅ Preloaded with high priority -->
<link rel="preload" href="/hero.webp" as="image" fetchpriority="high">
<img src="/hero.webp" alt="Hero" fetchpriority="high">
```

**4. Client-side rendering delays**
```javascript
// ❌ Content loads after JavaScript
useEffect(() => {
  fetch('/api/hero-text').then(r => r.json()).then(setHeroText);
}, []);

// ✅ Server-side or static rendering
// Use SSR, SSG, or streaming to send HTML with content
export async function getServerSideProps() {
  const heroText = await fetchHeroText();
  return { props: { heroText } };
}
```

### LCP optimization checklist

```markdown
- [ ] TTFB < 800ms (use CDN, edge caching)
- [ ] LCP image preloaded with fetchpriority="high"
- [ ] LCP image optimized (WebP/AVIF, correct size)
- [ ] Critical CSS inlined (< 14KB)
- [ ] No render-blocking JavaScript in <head>
- [ ] Fonts don't block text rendering (font-display: swap)
- [ ] LCP element in initial HTML (not JS-rendered)
```

### LCP element identification
```javascript
// Find your LCP element
new PerformanceObserver((list) => {
  const entries = list.getEntries();
  const lastEntry = entries[entries.length - 1];
  console.log('LCP element:', lastEntry.element);
  console.log('LCP time:', lastEntry.startTime);
}).observe({ type: 'largest-contentful-paint', buffered: true });
```

---

## INP: Interaction to Next Paint

INP measures responsiveness across ALL interactions (clicks, taps, key presses) during a page visit. It reports the worst interaction (at 98th percentile for high-traffic pages).

### INP breakdown

Total INP = **Input Delay** + **Processing Time** + **Presentation Delay**

| Phase | Target | Optimization |
|-------|--------|--------------|
| Input Delay | < 50ms | Reduce main thread blocking |
| Processing | < 100ms | Optimize event handlers |
| Presentation | < 50ms | Minimize rendering work |

### Common INP issues

**1. Long tasks blocking main thread**
```javascript
// ❌ Long synchronous task
function processLargeArray(items) {
  items.forEach(item => expensiveOperation(item));
}

// ✅ Break into chunks with yielding
async function processLargeArray(items) {
  const CHUNK_SIZE = 100;
  for (let i = 0; i < items.length; i += CHUNK_SIZE) {
    const chunk = items.slice(i, i + CHUNK_SIZE);
    chunk.forEach(item => expensiveOperation(item));
    
    // Yield to main thread
    await new Promise(r => setTimeout(r, 0));
    // Or use scheduler.yield() when available
  }
}
```

**2. Heavy event handlers**
```javascript
// ❌ All work in handler
button.addEventListener('click', () => {
  // Heavy computation
  const result = calculateComplexThing();
  // DOM updates
  updateUI(result);
  // Analytics
  trackEvent('click');
});

// ✅ Prioritize visual feedback
button.addEventListener('click', () => {
  // Immediate visual feedback
  button.classList.add('loading');
  
  // Defer non-critical work
  requestAnimationFrame(() => {
    const result = calculateComplexThing();
    updateUI(result);
  });
  
  // Use requestIdleCallback for analytics
  requestIdleCallback(() => trackEvent('click'));
});
```

**3. Third-party scripts**
```javascript
// ❌ Eagerly loaded, blocks interactions
<script src="https://heavy-widget.com/widget.js"></script>

// ✅ Lazy loaded on interaction or visibility
const loadWidget = () => {
  import('https://heavy-widget.com/widget.js')
    .then(widget => widget.init());
};
button.addEventListener('click', loadWidget, { once: true });
```

**4. Excessive re-renders (React/Vue)**
```javascript
// ❌ Re-renders entire tree
function App() {
  const [count, setCount] = useState(0);
  return (
    <div>
      <Counter count={count} />
      <ExpensiveComponent /> {/* Re-renders on every count change */}
    </div>
  );
}

// ✅ Memoized expensive components
const MemoizedExpensive = React.memo(ExpensiveComponent);

function App() {
  const [count, setCount] = useState(0);
  return (
    <div>
      <Counter count={count} />
      <MemoizedExpensive />
    </div>
  );
}
```

### INP optimization checklist

```markdown
- [ ] No tasks > 50ms on main thread
- [ ] Event handlers complete quickly (< 100ms)
- [ ] Visual feedback provided immediately
- [ ] Heavy work deferred with requestIdleCallback
- [ ] Third-party scripts don't block interactions
- [ ] Debounced input handlers where appropriate
- [ ] Web Workers for CPU-intensive operations
```

### INP debugging
```javascript
// Identify slow interactions
new PerformanceObserver((list) => {
  for (const entry of list.getEntries()) {
    if (entry.duration > 200) {
      console.warn('Slow interaction:', {
        type: entry.name,
        duration: entry.duration,
        processingStart: entry.processingStart,
        processingEnd: entry.processingEnd,
        target: entry.target
      });
    }
  }
}).observe({ type: 'event', buffered: true, durationThreshold: 16 });
```

---

## CLS: Cumulative Layout Shift

CLS measures unexpected layout shifts. A shift occurs when a visible element changes position between frames without user interaction.

**CLS Formula:** `impact fraction × distance fraction`

### Common CLS causes

**1. Images without dimensions**
```html
<!-- ❌ Causes layout shift when loaded -->
<img src="photo.jpg" alt="Photo">

<!-- ✅ Space reserved -->
<img src="photo.jpg" alt="Photo" width="800" height="600">

<!-- ✅ Or use aspect-ratio -->
<img src="photo.jpg" alt="Photo" style="aspect-ratio: 4/3; width: 100%;">
```

**2. Ads, embeds, and iframes**
```html
<!-- ❌ Unknown size until loaded -->
<iframe src="https://ad-network.com/ad"></iframe>

<!-- ✅ Reserve space with min-height -->
<div style="min-height: 250px;">
  <iframe src="https://ad-network.com/ad" height="250"></iframe>
</div>

<!-- ✅ Or use aspect-ratio container -->
<div style="aspect-ratio: 16/9;">
  <iframe src="https://youtube.com/embed/..." 
          style="width: 100%; height: 100%;"></iframe>
</div>
```

**3. Dynamically injected content**
```javascript
// ❌ Inserts content above viewport
notifications.prepend(newNotification);

// ✅ Insert below viewport or use transform
const insertBelow = viewport.bottom < newNotification.top;
if (insertBelow) {
  notifications.prepend(newNotification);
} else {
  // Animate in without shifting
  newNotification.style.transform = 'translateY(-100%)';
  notifications.prepend(newNotification);
  requestAnimationFrame(() => {
    newNotification.style.transform = '';
  });
}
```

**4. Web fonts causing FOUT**
```css
/* ❌ Font swap shifts text */
@font-face {
  font-family: 'Custom';
  src: url('custom.woff2') format('woff2');
}

/* ✅ Optional font (no shift if slow) */
@font-face {
  font-family: 'Custom';
  src: url('custom.woff2') format('woff2');
  font-display: optional;
}

/* ✅ Or match fallback metrics */
@font-face {
  font-family: 'Custom';
  src: url('custom.woff2') format('woff2');
  font-display: swap;
  size-adjust: 105%; /* Match fallback size */
  ascent-override: 95%;
  descent-override: 20%;
}
```

**5. Animations triggering layout**
```css
/* ❌ Animates layout properties */
.animate {
  transition: height 0.3s, width 0.3s;
}

/* ✅ Use transform instead */
.animate {
  transition: transform 0.3s;
}
.animate.expanded {
  transform: scale(1.2);
}
```

### CLS optimization checklist

```markdown
- [ ] All images have width/height or aspect-ratio
- [ ] All videos/embeds have reserved space
- [ ] Ads have min-height containers
- [ ] Fonts use font-display: optional or matched metrics
- [ ] Dynamic content inserted below viewport
- [ ] Animations use transform/opacity only
- [ ] No content injected above existing content
```

### CLS debugging
```javascript
// Track layout shifts
new PerformanceObserver((list) => {
  for (const entry of list.getEntries()) {
    if (!entry.hadRecentInput) {
      console.log('Layout shift:', entry.value);
      entry.sources?.forEach(source => {
        console.log('  Shifted element:', source.node);
        console.log('  Previous rect:', source.previousRect);
        console.log('  Current rect:', source.currentRect);
      });
    }
  }
}).observe({ type: 'layout-shift', buffered: true });
```

---

## Measurement tools

### Lab testing
- **Chrome DevTools** → Performance panel, Lighthouse
- **WebPageTest** → Detailed waterfall, filmstrip
- **Lighthouse CLI** → `npx lighthouse <url>`

### Field data (real users)
- **Chrome User Experience Report (CrUX)** → BigQuery or API
- **Search Console** → Core Web Vitals report
- **web-vitals library** → Send to your analytics

```javascript
import {onLCP, onINP, onCLS} from 'web-vitals';

function sendToAnalytics({name, value, rating}) {
  gtag('event', name, {
    event_category: 'Web Vitals',
    value: Math.round(name === 'CLS' ? value * 1000 : value),
    event_label: rating
  });
}

onLCP(sendToAnalytics);
onINP(sendToAnalytics);
onCLS(sendToAnalytics);
```

---

## Framework quick fixes

### Next.js
```jsx
// LCP: Use next/image with priority
import Image from 'next/image';
<Image src="/hero.jpg" priority fill alt="Hero" />

// INP: Use dynamic imports
const HeavyComponent = dynamic(() => import('./Heavy'), { ssr: false });

// CLS: Image component handles dimensions automatically
```

### React
```jsx
// LCP: Preload in head
<link rel="preload" href="/hero.jpg" as="image" fetchpriority="high" />

// INP: Memoize and useTransition
const [isPending, startTransition] = useTransition();
startTransition(() => setExpensiveState(newValue));

// CLS: Always specify dimensions in img tags
```

### Vue/Nuxt
```vue
<!-- LCP: Use nuxt/image with preload -->
<NuxtImg src="/hero.jpg" preload loading="eager" />

<!-- INP: Use async components -->
<component :is="() => import('./Heavy.vue')" />

<!-- CLS: Use aspect-ratio CSS -->
<img :style="{ aspectRatio: '16/9' }" />
```

## References

- [web.dev LCP](https://web.dev/articles/lcp)
- [web.dev INP](https://web.dev/articles/inp)
- [web.dev CLS](https://web.dev/articles/cls)
- [Performance skill](../performance/SKILL.md)
