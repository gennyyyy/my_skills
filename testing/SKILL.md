---
name: testing
description: Plan and build comprehensive Playwright E2E test suites with Page Object Model, authentication state persistence, custom fixtures, visual regression, and CI integration. Uses interview-driven planning to clarify critical user flows, auth strategy, test data approach, and parallelization before writing any tests. Toolkit for interacting with and testing local web applications using Playwright. Supports verifying frontend functionality, debugging UI behavior, capturing browser screenshots, and viewing browser logs. Generate comprehensive test plans, manual test cases, regression test suites, and bug reports for QA engineers. Includes Figma MCP integration for design validation.
tags: [playwright, e2e, testing, automation, typescript, ci, visual-regression]
---


# Playwright E2E Test Suite Builder

## When to use

Use this skill when you need to:

- Set up Playwright from scratch in an existing project
- Build E2E tests for critical user flows (signup, checkout, dashboards)
- Implement Page Object Model for maintainable test architecture
- Configure authentication state persistence across tests
- Set up visual regression testing with screenshots
- Integrate Playwright into CI/CD with sharding and retries

## Phase 1: Explore (Plan Mode)

Enter plan mode. Before writing any tests, explore the existing project:

### Project structure
- Find the tech stack: is this React, Next.js, Vue, SvelteKit, or another framework?
- Check if Playwright is already installed (`playwright.config.ts`, `@playwright/test` in package.json)
- Look for existing test directories (`e2e/`, `tests/`, `__tests__/`)
- Check for existing E2E tests in Cypress, Selenium, or other frameworks (migration context)
- Find the dev server command and port (`npm run dev`, `next dev`, etc.)

### Application structure
- Identify the main routes/pages (look at router config, pages directory, or route files)
- Find authentication flow (login page URL, auth API endpoints, token storage)
- Check for test IDs in components (`data-testid`, `data-test`, `data-cy` attributes)
- Look for API routes that tests might need to seed data through
- Check `.env` files for test-specific environment variables

### CI/CD
- Check for existing CI config (`.github/workflows/`, `.gitlab-ci.yml`, `Jenkinsfile`)
- Look for Docker or docker-compose setup (useful for consistent test environments)
- Check if there's a staging/preview environment URL pattern

## Phase 2: Interview (AskUserQuestion)

Use AskUserQuestion to clarify requirements. Ask in rounds.

### Round 1: Scope and critical flows

```
Question: "What are the critical user flows to test?"
Header: "Flows"
multiSelect: true
Options:
  - "Authentication (signup, login, logout, password reset)" — Core auth flows
  - "Core CRUD (create, read, update, delete main resources)" — Primary data operations
  - "Checkout/payments (cart, billing, confirmation)" — E-commerce or payment flows
  - "Dashboard/admin (data views, filters, exports)" — Admin panel interactions
```

```
Question: "How many pages/routes does the application have approximately?"
Header: "App size"
Options:
  - "Small (< 10 routes)" — Landing page, auth, a few feature pages
  - "Medium (10-30 routes)" — Multiple feature areas, settings, profiles
  - "Large (30+ routes)" — Complex app with many sections and user roles
```

### Round 2: Authentication strategy for tests

```
Question: "How does your app handle authentication?"
Header: "Auth type"
Options:
  - "Cookie/session based (Recommended)" — Server sets httpOnly cookies after login
  - "JWT in localStorage" — Token stored in browser localStorage
  - "OAuth/SSO (Google, GitHub, etc.)" — Third-party auth provider redirect flow
  - "No auth (public app)" — No login required

Question: "How should tests authenticate?"
Header: "Test auth"
Options:
  - "Login via UI once, reuse state (Recommended)" — storageState pattern: login in setup, share cookies across tests
  - "API login in beforeEach" — Call auth API directly before each test, skip UI login
  - "Seed auth token in fixtures" — Inject pre-generated tokens, no login flow needed
  - "Test login UI every time" — Actually test the login form in each test suite
```

### Round 3: Test data and environment

```
Question: "How should test data be managed?"
Header: "Test data"
Options:
  - "API seeding in fixtures (Recommended)" — Call API endpoints to create/clean test data before each test
  - "Database seeding (direct SQL)" — Run SQL scripts or ORM commands to populate test database
  - "Shared test environment (pre-populated)" — Tests run against a persistent staging environment with existing data
  - "Mock API responses" — Intercept network requests and return mock data

Question: "What environment do E2E tests run against?"
Header: "Environment"
Options:
  - "Local dev server (Recommended)" — Start dev server before tests, run against localhost
  - "Preview/staging URL" — Run against a deployed preview or staging environment
  - "Docker Compose stack" — Full stack in containers, tests run outside or inside
```

### Round 4: CI and parallelization

```
Question: "How should tests run in CI?"
Header: "CI"
Options:
  - "GitHub Actions (Recommended)" — Native Playwright support with sharding
  - "GitLab CI" — Docker-based runners with Playwright image
  - "Local only (no CI yet)" — Just local test runs for now
  - "Other CI (Jenkins, CircleCI)" — Custom CI configuration

Question: "Do you need visual regression testing?"
Header: "Visual"
Options:
  - "No — functional tests only (Recommended)" — Assert behavior, not pixels
  - "Yes — screenshot comparisons" — Capture and compare page screenshots
  - "Yes — component screenshots" — Capture specific components, not full pages
```

## Phase 3: Plan (ExitPlanMode)

Write a concrete implementation plan covering:

1. **Directory structure** — test files, page objects, fixtures, config
2. **Playwright config** — projects (browsers), base URL, retries, workers
3. **Auth setup** — global setup for storageState or API-based auth
4. **Page objects** — classes for each page with locators and actions
5. **Test fixtures** — custom fixtures for data seeding, auth, API client
6. **Test suites** — test files for each critical flow from the interview
7. **CI config** — workflow file with sharding, artifact upload, reporting

Present via ExitPlanMode for user approval.

## Phase 4: Execute

After approval, implement following this order:

### Step 1: Playwright config

```typescript
import { defineConfig, devices } from '@playwright/test';

export default defineConfig({
  testDir: './e2e',
  fullyParallel: true,
  forbidOnly: !!process.env.CI,
  retries: process.env.CI ? 2 : 0,
  workers: process.env.CI ? 1 : undefined,
  reporter: process.env.CI
    ? [['html', { open: 'never' }], ['github']]
    : [['html', { open: 'on-failure' }]],

  use: {
    baseURL: process.env.BASE_URL || 'http://localhost:3000',
    trace: 'on-first-retry',
    screenshot: 'only-on-failure',
    video: 'on-first-retry',
  },

  projects: [
    // Auth setup — runs before all tests
    {
      name: 'setup',
      testMatch: /.*\.setup\.ts/,
    },
    {
      name: 'chromium',
      use: {
        ...devices['Desktop Chrome'],
        storageState: 'e2e/.auth/user.json',
      },
      dependencies: ['setup'],
    },
    {
      name: 'firefox',
      use: {
        ...devices['Desktop Firefox'],
        storageState: 'e2e/.auth/user.json',
      },
      dependencies: ['setup'],
    },
    {
      name: 'mobile',
      use: {
        ...devices['iPhone 14'],
        storageState: 'e2e/.auth/user.json',
      },
      dependencies: ['setup'],
    },
  ],

  webServer: {
    command: 'npm run dev',
    url: 'http://localhost:3000',
    reuseExistingServer: !process.env.CI,
    timeout: 120_000,
  },
});
```

### Step 2: Auth setup (global)

```typescript
// e2e/auth.setup.ts
import { test as setup, expect } from '@playwright/test';

const authFile = 'e2e/.auth/user.json';

setup('authenticate', async ({ page }) => {
  // Navigate to login page
  await page.goto('/login');

  // Fill login form
  await page.getByLabel('Email').fill(process.env.TEST_USER_EMAIL || 'test@example.com');
  await page.getByLabel('Password').fill(process.env.TEST_USER_PASSWORD || 'testpassword');
  await page.getByRole('button', { name: 'Sign in' }).click();

  // Wait for auth to complete — adjust selector to your app
  await page.waitForURL('/dashboard');
  await expect(page.getByRole('navigation')).toBeVisible();

  // Save signed-in state
  await page.context().storageState({ path: authFile });
});
```

### Step 3: Custom fixtures

```typescript
// e2e/fixtures.ts
import { test as base, expect } from '@playwright/test';
import { LoginPage } from './pages/login-page';
import { DashboardPage } from './pages/dashboard-page';

// API client for test data seeding
class ApiClient {
  constructor(private baseURL: string, private token?: string) {}

  async createResource(data: Record<string, unknown>) {
    const response = await fetch(`${this.baseURL}/api/resources`, {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
        ...(this.token ? { Authorization: `Bearer ${this.token}` } : {}),
      },
      body: JSON.stringify(data),
    });
    if (!response.ok) throw new Error(`Seed failed: ${response.status}`);
    return response.json();
  }

  async deleteResource(id: string) {
    await fetch(`${this.baseURL}/api/resources/${id}`, {
      method: 'DELETE',
      headers: this.token ? { Authorization: `Bearer ${this.token}` } : {},
    });
  }
}

type Fixtures = {
  loginPage: LoginPage;
  dashboardPage: DashboardPage;
  api: ApiClient;
};

export const test = base.extend<Fixtures>({
  loginPage: async ({ page }, use) => {
    await use(new LoginPage(page));
  },

  dashboardPage: async ({ page }, use) => {
    await use(new DashboardPage(page));
  },

  api: async ({ baseURL }, use) => {
    const client = new ApiClient(baseURL!);
    await use(client);
  },
});

export { expect };
```

### Step 4: Page Object Model

```typescript
// e2e/pages/login-page.ts
import { type Page, type Locator, expect } from '@playwright/test';

export class LoginPage {
  readonly emailInput: Locator;
  readonly passwordInput: Locator;
  readonly submitButton: Locator;
  readonly errorMessage: Locator;

  constructor(private page: Page) {
    this.emailInput = page.getByLabel('Email');
    this.passwordInput = page.getByLabel('Password');
    this.submitButton = page.getByRole('button', { name: 'Sign in' });
    this.errorMessage = page.getByRole('alert');
  }

  async goto() {
    await this.page.goto('/login');
  }

  async login(email: string, password: string) {
    await this.emailInput.fill(email);
    await this.passwordInput.fill(password);
    await this.submitButton.click();
  }

  async expectError(message: string) {
    await expect(this.errorMessage).toContainText(message);
  }
}

// e2e/pages/dashboard-page.ts
import { type Page, type Locator, expect } from '@playwright/test';

export class DashboardPage {
  readonly heading: Locator;
  readonly createButton: Locator;
  readonly searchInput: Locator;
  readonly resourceList: Locator;

  constructor(private page: Page) {
    this.heading = page.getByRole('heading', { level: 1 });
    this.createButton = page.getByRole('button', { name: 'Create' });
    this.searchInput = page.getByPlaceholder('Search');
    this.resourceList = page.getByTestId('resource-list');
  }

  async goto() {
    await this.page.goto('/dashboard');
  }

  async createResource(name: string) {
    await this.createButton.click();
    await this.page.getByLabel('Name').fill(name);
    await this.page.getByRole('button', { name: 'Save' }).click();
  }

  async search(query: string) {
    await this.searchInput.fill(query);
    // Wait for debounced search to trigger
    await this.page.waitForResponse(resp =>
      resp.url().includes('/api/resources') && resp.status() === 200
    );
  }

  async expectResourceVisible(name: string) {
    await expect(this.resourceList.getByText(name)).toBeVisible();
  }

  async expectResourceCount(count: number) {
    await expect(this.resourceList.getByRole('listitem')).toHaveCount(count);
  }
}
```

### Step 5: Test suites

```typescript
// e2e/auth.spec.ts
import { test, expect } from './fixtures';

test.describe('Authentication', () => {
  // These tests run WITHOUT storageState (unauthenticated)
  test.use({ storageState: { cookies: [], origins: [] } });

  test('successful login redirects to dashboard', async ({ loginPage, page }) => {
    await loginPage.goto();
    await loginPage.login('test@example.com', 'testpassword');
    await expect(page).toHaveURL('/dashboard');
  });

  test('invalid credentials shows error', async ({ loginPage }) => {
    await loginPage.goto();
    await loginPage.login('test@example.com', 'wrongpassword');
    await loginPage.expectError('Invalid credentials');
  });

  test('logout clears session', async ({ page }) => {
    // Login first
    await page.goto('/login');
    // ... login steps ...

    // Logout
    await page.getByRole('button', { name: 'Logout' }).click();
    await expect(page).toHaveURL('/login');

    // Verify can't access protected route
    await page.goto('/dashboard');
    await expect(page).toHaveURL('/login');
  });
});

// e2e/dashboard.spec.ts
import { test, expect } from './fixtures';

test.describe('Dashboard', () => {
  test('displays resource list', async ({ dashboardPage }) => {
    await dashboardPage.goto();
    await expect(dashboardPage.heading).toHaveText('Dashboard');
    await expect(dashboardPage.resourceList).toBeVisible();
  });

  test('create new resource', async ({ dashboardPage, page }) => {
    await dashboardPage.goto();
    await dashboardPage.createResource('New E2E Resource');

    // Verify resource appears in list
    await dashboardPage.expectResourceVisible('New E2E Resource');
  });

  test('search filters results', async ({ dashboardPage, api }) => {
    // Seed test data via API
    await api.createResource({ name: 'Alpha Item' });
    await api.createResource({ name: 'Beta Item' });

    await dashboardPage.goto();
    await dashboardPage.search('Alpha');
    await dashboardPage.expectResourceVisible('Alpha Item');
  });

  test('empty state shown when no resources', async ({ dashboardPage, page }) => {
    await dashboardPage.goto();
    await dashboardPage.search('nonexistent-query-xyz');
    await expect(page.getByText('No results found')).toBeVisible();
  });
});

// e2e/crud.spec.ts
import { test, expect } from './fixtures';

test.describe('Resource CRUD', () => {
  let resourceId: string;

  test.beforeEach(async ({ api }) => {
    // Seed a resource for tests that need one
    const resource = await api.createResource({ name: 'Test Resource' });
    resourceId = resource.id;
  });

  test.afterEach(async ({ api }) => {
    // Clean up seeded data
    if (resourceId) {
      await api.deleteResource(resourceId).catch(() => {});
    }
  });

  test('edit resource name', async ({ page }) => {
    await page.goto(`/resources/${resourceId}`);
    await page.getByRole('button', { name: 'Edit' }).click();
    await page.getByLabel('Name').clear();
    await page.getByLabel('Name').fill('Updated Resource');
    await page.getByRole('button', { name: 'Save' }).click();

    await expect(page.getByRole('heading')).toHaveText('Updated Resource');
  });

  test('delete resource with confirmation', async ({ page }) => {
    await page.goto(`/resources/${resourceId}`);
    await page.getByRole('button', { name: 'Delete' }).click();

    // Confirm deletion dialog
    await expect(page.getByRole('dialog')).toBeVisible();
    await page.getByRole('button', { name: 'Confirm' }).click();

    // Should redirect to list
    await expect(page).toHaveURL('/dashboard');
  });
});
```

### Step 6: Visual regression (if selected)

```typescript
// e2e/visual.spec.ts
import { test, expect } from './fixtures';

test.describe('Visual regression', () => {
  test('dashboard matches snapshot', async ({ dashboardPage, page }) => {
    await dashboardPage.goto();
    // Wait for dynamic content to stabilize
    await page.waitForLoadState('networkidle');
    await expect(page).toHaveScreenshot('dashboard.png', {
      maxDiffPixelRatio: 0.01,
    });
  });

  test('login page matches snapshot', async ({ loginPage, page }) => {
    test.use({ storageState: { cookies: [], origins: [] } });
    await loginPage.goto();
    await expect(page).toHaveScreenshot('login.png', {
      maxDiffPixelRatio: 0.01,
    });
  });

  // Component-level screenshots
  test('navigation component matches snapshot', async ({ page }) => {
    await page.goto('/dashboard');
    const nav = page.getByRole('navigation');
    await expect(nav).toHaveScreenshot('navigation.png');
  });
});
```

### Step 7: GitHub Actions CI

```yaml
# .github/workflows/e2e.yml
name: E2E Tests

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  e2e:
    timeout-minutes: 30
    runs-on: ubuntu-latest
    strategy:
      fail-fast: false
      matrix:
        shard: [1/4, 2/4, 3/4, 4/4]

    steps:
      - uses: actions/checkout@v4

      - uses: actions/setup-node@v4
        with:
          node-version: 20
          cache: 'npm'

      - run: npm ci

      - name: Install Playwright browsers
        run: npx playwright install --with-deps chromium

      - name: Run E2E tests
        run: npx playwright test --shard=${{ matrix.shard }}
        env:
          BASE_URL: http://localhost:3000
          TEST_USER_EMAIL: ${{ secrets.TEST_USER_EMAIL }}
          TEST_USER_PASSWORD: ${{ secrets.TEST_USER_PASSWORD }}

      - name: Upload test report
        uses: actions/upload-artifact@v4
        if: ${{ !cancelled() }}
        with:
          name: playwright-report-${{ strategy.job-index }}
          path: playwright-report/
          retention-days: 14

      - name: Upload test results
        uses: actions/upload-artifact@v4
        if: ${{ !cancelled() }}
        with:
          name: test-results-${{ strategy.job-index }}
          path: test-results/
          retention-days: 7
```

## Directory structure reference

```
e2e/
├── .auth/
│   └── user.json            # Saved auth state (gitignored)
├── fixtures.ts              # Custom test fixtures and API client
├── pages/
│   ├── login-page.ts        # Login page object
│   ├── dashboard-page.ts    # Dashboard page object
│   └── resource-page.ts     # Resource detail page object
├── auth.setup.ts            # Global auth setup (runs once)
├── auth.spec.ts             # Authentication tests
├── dashboard.spec.ts        # Dashboard tests
├── crud.spec.ts             # CRUD operation tests
└── visual.spec.ts           # Visual regression tests (optional)
playwright.config.ts         # Playwright configuration
```

## Best practices

### Use role-based locators first
Prefer `getByRole()`, `getByLabel()`, `getByText()` over CSS selectors or test IDs. These locators mirror how users interact with the page and catch accessibility issues:

```typescript
// Preferred — accessible and resilient
await page.getByRole('button', { name: 'Submit' }).click();
await page.getByLabel('Email').fill('user@test.com');

// Fallback — when role-based doesn't work
await page.getByTestId('custom-widget').click();

// Avoid — fragile, breaks on refactors
await page.locator('.btn-primary').click();
await page.locator('#email-input').fill('user@test.com');
```

### Wait for network, not timers
Never use `page.waitForTimeout()`. Wait for specific conditions:

```typescript
// Wait for API response
await page.waitForResponse(resp => resp.url().includes('/api/data'));

// Wait for element state
await expect(page.getByText('Saved')).toBeVisible();

// Wait for navigation
await expect(page).toHaveURL('/dashboard');

// Wait for loading to finish
await expect(page.getByTestId('spinner')).toBeHidden();
```

### Isolate test data
Each test should create its own data and clean up after:

```typescript
test('edit resource', async ({ api, page }) => {
  // Arrange — seed via API
  const resource = await api.createResource({ name: 'Test' });

  // Act
  await page.goto(`/resources/${resource.id}`);
  // ... test logic ...

  // Cleanup (also runs on failure via afterEach)
});
```

### Tag tests for selective runs

```typescript
test('checkout flow @slow @checkout', async ({ page }) => {
  // Long test tagged for selective execution
});

// Run only: npx playwright test --grep @checkout
// Skip slow: npx playwright test --grep-invert @slow
```

### .gitignore additions

```
# Playwright
e2e/.auth/
test-results/
playwright-report/
blob-report/
```

## Checklist before finishing

- [ ] `playwright.config.ts` has webServer configured to start the dev server
- [ ] Auth setup saves storageState and all test projects depend on it
- [ ] Page objects use role-based locators (`getByRole`, `getByLabel`, `getByText`)
- [ ] No `waitForTimeout()` calls — only wait for elements, URLs, or responses
- [ ] Tests create and clean up their own data (no shared mutable state)
- [ ] CI config has sharding for parallel execution
- [ ] Trace, screenshot, and video are captured on failure for debugging
- [ ] `.auth/` directory is in `.gitignore`
- [ ] `npx playwright test` passes locally before pushing


---

<!-- merged-in: development/webapp-testing, ai-research/qa-test-planner -->


# Merged section: webapp-testing (from development/webapp-testing)
Supporting files from this skill live in `references/webapp-testing/`, `scripts/webapp-testing/`, `data/webapp-testing/` (whichever exist).

# Web Application Testing

To test local web applications, write native Python Playwright scripts.

**Helper Scripts Available**:
- `scripts/with_server.py` - Manages server lifecycle (supports multiple servers)

**Always run scripts with `--help` first** to see usage. DO NOT read the source until you try running the script first and find that a customized solution is abslutely necessary. These scripts can be very large and thus pollute your context window. They exist to be called directly as black-box scripts rather than ingested into your context window.

## Decision Tree: Choosing Your Approach

```
User task → Is it static HTML?
    ├─ Yes → Read HTML file directly to identify selectors
    │         ├─ Success → Write Playwright script using selectors
    │         └─ Fails/Incomplete → Treat as dynamic (below)
    │
    └─ No (dynamic webapp) → Is the server already running?
        ├─ No → Run: python scripts/with_server.py --help
        │        Then use the helper + write simplified Playwright script
        │
        └─ Yes → Reconnaissance-then-action:
            1. Navigate and wait for networkidle
            2. Take screenshot or inspect DOM
            3. Identify selectors from rendered state
            4. Execute actions with discovered selectors
```

## Example: Using with_server.py

To start a server, run `--help` first, then use the helper:

**Single server:**
```bash
python scripts/with_server.py --server "npm run dev" --port 5173 -- python your_automation.py
```

**Multiple servers (e.g., backend + frontend):**
```bash
python scripts/with_server.py \
  --server "cd backend && python server.py" --port 3000 \
  --server "cd frontend && npm run dev" --port 5173 \
  -- python your_automation.py
```

To create an automation script, include only Playwright logic (servers are managed automatically):
```python
from playwright.sync_api import sync_playwright

with sync_playwright() as p:
    browser = p.chromium.launch(headless=True) # Always launch chromium in headless mode
    page = browser.new_page()
    page.goto('http://localhost:5173') # Server already running and ready
    page.wait_for_load_state('networkidle') # CRITICAL: Wait for JS to execute
    # ... your automation logic
    browser.close()
```

## Reconnaissance-Then-Action Pattern

1. **Inspect rendered DOM**:
   ```python
   page.screenshot(path='/tmp/inspect.png', full_page=True)
   content = page.content()
   page.locator('button').all()
   ```

2. **Identify selectors** from inspection results

3. **Execute actions** using discovered selectors

## Common Pitfall

❌ **Don't** inspect the DOM before waiting for `networkidle` on dynamic apps
✅ **Do** wait for `page.wait_for_load_state('networkidle')` before inspection

## Best Practices

- **Use bundled scripts as black boxes** - To accomplish a task, consider whether one of the scripts available in `scripts/` can help. These scripts handle common, complex workflows reliably without cluttering the context window. Use `--help` to see usage, then invoke directly. 
- Use `sync_playwright()` for synchronous scripts
- Always close the browser when done
- Use descriptive selectors: `text=`, `role=`, CSS selectors, or IDs
- Add appropriate waits: `page.wait_for_selector()` or `page.wait_for_timeout()`

## Reference Files

- **examples/** - Examples showing common patterns:
  - `element_discovery.py` - Discovering buttons, links, and inputs on a page
  - `static_html_automation.py` - Using file:// URLs for local HTML
  - `console_logging.py` - Capturing console logs during automation


# Merged section: qa-test-planner (from ai-research/qa-test-planner)
Supporting files from this skill live in `references/qa-test-planner/`, `scripts/qa-test-planner/`, `data/qa-test-planner/` (whichever exist).

# QA Test Planner

A comprehensive skill for QA engineers to create test plans, generate manual test cases, build regression test suites, validate designs against Figma, and document bugs effectively.

> **Activation:** This skill is triggered only when explicitly called by name (e.g., `/qa-test-planner`, `qa-test-planner`, or `use the skill qa-test-planner`).

---

## Quick Start

**Create a test plan:**
```
"Create a test plan for the user authentication feature"
```

**Generate test cases:**
```
"Generate manual test cases for the checkout flow"
```

**Build regression suite:**
```
"Build a regression test suite for the payment module"
```

**Validate against Figma:**
```
"Compare the login page against the Figma design at [URL]"
```

**Create bug report:**
```
"Create a bug report for the form validation issue"
```

---

## Quick Reference

| Task | What You Get | Time |
|------|--------------|------|
| Test Plan | Strategy, scope, schedule, risks | 10-15 min |
| Test Cases | Step-by-step instructions, expected results | 5-10 min each |
| Regression Suite | Smoke tests, critical paths, execution order | 15-20 min |
| Figma Validation | Design-implementation comparison, discrepancy list | 10-15 min |
| Bug Report | Reproducible steps, environment, evidence | 5 min |

---

## How It Works

```
Your Request
    │
    ▼
┌─────────────────────────────────────────────────────┐
│ 1. ANALYZE                                          │
│    • Parse feature/requirement                      │
│    • Identify test types needed                     │
│    • Determine scope and priorities                 │
├─────────────────────────────────────────────────────┤
│ 2. GENERATE                                         │
│    • Create structured deliverables                 │
│    • Apply templates and best practices             │
│    • Include edge cases and variations              │
├─────────────────────────────────────────────────────┤
│ 3. VALIDATE                                         │
│    • Check completeness                             │
│    • Verify traceability                            │
│    • Ensure actionable steps                        │
└─────────────────────────────────────────────────────┘
    │
    ▼
QA Deliverable Ready
```

---

## Commands

### Interactive Scripts

| Script | Purpose | Usage |
|--------|---------|-------|
| `./scripts/generate_test_cases.sh` | Create test cases interactively | Step-by-step prompts |
| `./scripts/create_bug_report.sh` | Generate bug reports | Guided input collection |

### Natural Language

| Request | Output |
|---------|--------|
| "Create test plan for {feature}" | Complete test plan document |
| "Generate {N} test cases for {feature}" | Numbered test cases with steps |
| "Build smoke test suite" | Critical path tests |
| "Compare with Figma at {URL}" | Visual validation checklist |
| "Document bug: {description}" | Structured bug report |

---

## Core Deliverables

### 1. Test Plans
- Test scope and objectives
- Testing approach and strategy
- Environment requirements
- Entry/exit criteria
- Risk assessment
- Timeline and milestones

### 2. Manual Test Cases
- Step-by-step instructions
- Expected vs actual results
- Preconditions and setup
- Test data requirements
- Priority and severity

### 3. Regression Suites
- Smoke tests (15-30 min)
- Full regression (2-4 hours)
- Targeted regression (30-60 min)
- Execution order and dependencies

### 4. Figma Validation
- Component-by-component comparison
- Spacing and typography checks
- Color and visual consistency
- Interactive state validation

### 5. Bug Reports
- Clear reproduction steps
- Environment details
- Evidence (screenshots, logs)
- Severity and priority

---

## Anti-Patterns

| Avoid | Why | Instead |
|-------|-----|---------|
| Vague test steps | Can't reproduce | Specific actions + expected results |
| Missing preconditions | Tests fail unexpectedly | Document all setup requirements |
| No test data | Tester blocked | Provide sample data or generation |
| Generic bug titles | Hard to track | Specific: "[Feature] issue when [action]" |
| Skip edge cases | Miss critical bugs | Include boundary values, nulls |

---

## Verification Checklist

**Test Plan:**
- [ ] Scope clearly defined (in/out)
- [ ] Entry/exit criteria specified
- [ ] Risks identified with mitigations
- [ ] Timeline realistic

**Test Cases:**
- [ ] Each step has expected result
- [ ] Preconditions documented
- [ ] Test data available
- [ ] Priority assigned

**Bug Reports:**
- [ ] Reproducible steps
- [ ] Environment documented
- [ ] Screenshots/evidence attached
- [ ] Severity/priority set

---

## References

- [Test Case Templates](references/test_case_templates.md) - Standard formats for all test types
- [Bug Report Templates](references/bug_report_templates.md) - Documentation templates
- [Regression Testing Guide](references/regression_testing.md) - Suite building and execution
- [Figma Validation Guide](references/figma_validation.md) - Design-implementation validation

---

<details>
<summary><strong>Deep Dive: Test Case Structure</strong></summary>

### Standard Test Case Format

```markdown
## TC-001: [Test Case Title]

**Priority:** High | Medium | Low
**Type:** Functional | UI | Integration | Regression
**Status:** Not Run | Pass | Fail | Blocked

### Objective
[What are we testing and why]

### Preconditions
- [Setup requirement 1]
- [Setup requirement 2]
- [Test data needed]

### Test Steps
1. [Action to perform]
   **Expected:** [What should happen]

2. [Action to perform]
   **Expected:** [What should happen]

3. [Action to perform]
   **Expected:** [What should happen]

### Test Data
- Input: [Test data values]
- User: [Test account details]
- Configuration: [Environment settings]

### Post-conditions
- [System state after test]
- [Cleanup required]

### Notes
- [Edge cases to consider]
- [Related test cases]
- [Known issues]
```

### Test Types

| Type | Focus | Example |
|------|-------|---------|
| Functional | Business logic | Login with valid credentials |
| UI/Visual | Appearance, layout | Button matches Figma design |
| Integration | Component interaction | API returns data to frontend |
| Regression | Existing functionality | Previous features still work |
| Performance | Speed, load handling | Page loads under 3 seconds |
| Security | Vulnerabilities | SQL injection prevented |

</details>

<details>
<summary><strong>Deep Dive: Test Plan Template</strong></summary>

### Test Plan Structure

```markdown
# Test Plan: [Feature/Release Name]

## Executive Summary
- Feature/product being tested
- Testing objectives
- Key risks
- Timeline overview

## Test Scope

**In Scope:**
- Features to be tested
- Test types (functional, UI, performance)
- Platforms and environments
- User flows and scenarios

**Out of Scope:**
- Features not being tested
- Known limitations
- Third-party integrations (if applicable)

## Test Strategy

**Test Types:**
- Manual testing
- Exploratory testing
- Regression testing
- Integration testing
- User acceptance testing

**Test Approach:**
- Black box testing
- Positive and negative testing
- Boundary value analysis
- Equivalence partitioning

## Test Environment
- Operating systems
- Browsers and versions
- Devices (mobile, tablet, desktop)
- Test data requirements
- Backend/API environments

## Entry Criteria
- [ ] Requirements documented
- [ ] Designs finalized
- [ ] Test environment ready
- [ ] Test data prepared
- [ ] Build deployed

## Exit Criteria
- [ ] All high-priority test cases executed
- [ ] 90%+ test case pass rate
- [ ] All critical bugs fixed
- [ ] No open high-severity bugs
- [ ] Regression suite passed

## Risk Assessment

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| [Risk 1] | H/M/L | H/M/L | [Mitigation] |

## Test Deliverables
- Test plan document
- Test cases
- Test execution reports
- Bug reports
- Test summary report
```

</details>

<details>
<summary><strong>Deep Dive: Bug Reporting</strong></summary>

### Bug Report Template

```markdown
# BUG-[ID]: [Clear, specific title]

**Severity:** Critical | High | Medium | Low
**Priority:** P0 | P1 | P2 | P3
**Type:** Functional | UI | Performance | Security
**Status:** Open | In Progress | Fixed | Closed

## Environment
- **OS:** [Windows 11, macOS 14, etc.]
- **Browser:** [Chrome 120, Firefox 121, etc.]
- **Device:** [Desktop, iPhone 15, etc.]
- **Build:** [Version/commit]
- **URL:** [Page where bug occurs]

## Description
[Clear, concise description of the issue]

## Steps to Reproduce
1. [Specific step]
2. [Specific step]
3. [Specific step]

## Expected Behavior
[What should happen]

## Actual Behavior
[What actually happens]

## Visual Evidence
- Screenshot: [attached]
- Video: [link if applicable]
- Console errors: [paste errors]

## Impact
- **User Impact:** [How many users affected]
- **Frequency:** [Always, Sometimes, Rarely]
- **Workaround:** [If one exists]

## Additional Context
- Related to: [Feature/ticket]
- Regression: [Yes/No]
- Figma design: [Link if UI bug]
```

### Severity Definitions

| Level | Criteria | Examples |
|-------|----------|----------|
| **Critical (P0)** | System crash, data loss, security | Payment fails, login broken |
| **High (P1)** | Major feature broken, no workaround | Search not working |
| **Medium (P2)** | Feature partial, workaround exists | Filter missing one option |
| **Low (P3)** | Cosmetic, rare edge cases | Typo, minor alignment |

</details>

<details>
<summary><strong>Deep Dive: Figma MCP Integration</strong></summary>

### Design Validation Workflow

**Prerequisites:**
- Figma MCP server configured
- Access to Figma design files
- Figma URLs for components/pages

**Process:**

1. **Get Design Specs from Figma**
```
"Get the button specifications from Figma file [URL]"

Response includes:
- Dimensions (width, height)
- Colors (background, text, border)
- Typography (font, size, weight)
- Spacing (padding, margin)
- Border radius
- States (default, hover, active, disabled)
```

2. **Compare Implementation**
```
TC: Primary Button Visual Validation
1. Inspect primary button in browser dev tools
2. Compare against Figma specs:
   - Dimensions: 120x40px
   - Border-radius: 8px
   - Background color: #0066FF
   - Font: 16px Medium #FFFFFF
3. Document discrepancies
```

3. **Create Bug if Mismatch**
```
BUG: Primary button color doesn't match design
Severity: Medium
Expected (Figma): #0066FF
Actual (Implementation): #0052CC
Screenshot: [attached]
Figma link: [specific component]
```

### What to Validate

| Element | What to Check | Tool |
|---------|---------------|------|
| Colors | Hex values exact | Browser color picker |
| Spacing | Padding/margin px | DevTools computed styles |
| Typography | Font, size, weight | DevTools font panel |
| Layout | Width, height, position | DevTools box model |
| States | Hover, active, focus | Manual interaction |
| Responsive | Breakpoint behavior | DevTools device mode |

### Example Queries
```
"Get button specifications from Figma design [URL]"
"Compare navigation menu implementation against Figma design"
"Extract spacing values for dashboard layout from Figma"
"List all color tokens used in Figma design system"
```

</details>

<details>
<summary><strong>Deep Dive: Regression Testing</strong></summary>

### Suite Structure

| Suite Type | Duration | Frequency | Coverage |
|------------|----------|-----------|----------|
| Smoke | 15-30 min | Daily | Critical paths only |
| Targeted | 30-60 min | Per change | Affected areas |
| Full | 2-4 hours | Weekly/Release | Comprehensive |
| Sanity | 10-15 min | After hotfix | Quick validation |

### Building a Regression Suite

**Step 1: Identify Critical Paths**
- What can users NOT live without?
- What generates revenue?
- What handles sensitive data?
- What's used most frequently?

**Step 2: Prioritize Test Cases**

| Priority | Description | Must Run |
|----------|-------------|----------|
| P0 | Business-critical, security | Always |
| P1 | Major features, common flows | Weekly+ |
| P2 | Minor features, edge cases | Releases |

**Step 3: Execution Order**
1. Smoke first - if fails, stop and fix build
2. P0 tests next - must pass before proceeding
3. P1 then P2 - track all failures
4. Exploratory - find unexpected issues

### Pass/Fail Criteria

**PASS:**
- All P0 tests pass
- 90%+ P1 tests pass
- No critical bugs open

**FAIL (Block Release):**
- Any P0 test fails
- Critical bug discovered
- Security vulnerability
- Data loss scenario

**CONDITIONAL:**
- P1 failures with workarounds
- Known issues documented
- Fix plan in place

</details>

<details>
<summary><strong>Deep Dive: Test Execution Tracking</strong></summary>

### Test Run Report Template

```markdown
# Test Run: [Release Version]

**Date:** 2024-01-15
**Build:** v2.5.0-rc1
**Tester:** [Name]
**Environment:** Staging

## Summary
- Total Test Cases: 150
- Executed: 145
- Passed: 130
- Failed: 10
- Blocked: 5
- Not Run: 5
- Pass Rate: 90%

## Test Cases by Priority

| Priority | Total | Pass | Fail | Blocked |
|----------|-------|------|------|---------|
| P0 (Critical) | 25 | 23 | 2 | 0 |
| P1 (High) | 50 | 45 | 3 | 2 |
| P2 (Medium) | 50 | 45 | 3 | 2 |
| P3 (Low) | 25 | 17 | 2 | 1 |

## Critical Failures
- TC-045: Payment processing fails
  - Bug: BUG-234
  - Status: Open

## Blocked Tests
- TC-112: Dashboard widget (API endpoint down)

## Risks
- 2 critical bugs blocking release
- Payment integration needs attention

## Next Steps
- Retest after BUG-234 fix
- Complete remaining 5 test cases
- Run full regression before sign-off
```

### Coverage Tracking

```markdown
## Coverage Matrix

| Feature | Requirements | Test Cases | Status | Gaps |
|---------|--------------|------------|--------|------|
| Login | 8 | 12 | Complete | None |
| Checkout | 15 | 10 | Partial | Payment errors |
| Dashboard | 12 | 15 | Complete | None |
```

</details>

<details>
<summary><strong>QA Process Workflow</strong></summary>

### Phase 1: Planning
- [ ] Review requirements and designs
- [ ] Create test plan
- [ ] Identify test scenarios
- [ ] Estimate effort and timeline
- [ ] Set up test environment

### Phase 2: Test Design
- [ ] Write test cases
- [ ] Review test cases with team
- [ ] Prepare test data
- [ ] Build regression suite
- [ ] Get Figma design access

### Phase 3: Execution
- [ ] Execute test cases
- [ ] Log bugs with clear steps
- [ ] Validate against Figma (UI tests)
- [ ] Track test progress
- [ ] Communicate blockers

### Phase 4: Reporting
- [ ] Compile test results
- [ ] Analyze coverage
- [ ] Document risks
- [ ] Provide go/no-go recommendation
- [ ] Archive test artifacts

</details>

<details>
<summary><strong>Best Practices</strong></summary>

### Test Case Writing

**DO:**
- Be specific and unambiguous
- Include expected results for each step
- Test one thing per test case
- Use consistent naming conventions
- Keep test cases maintainable

**DON'T:**
- Assume knowledge
- Make test cases too long
- Skip preconditions
- Forget edge cases
- Leave expected results vague

### Bug Reporting

**DO:**
- Provide clear reproduction steps
- Include screenshots/videos
- Specify exact environment details
- Describe impact on users
- Link to Figma for UI bugs

**DON'T:**
- Report without reproduction steps
- Use vague descriptions
- Skip environment details
- Forget to assign priority
- Duplicate existing bugs

### Regression Testing

**DO:**
- Automate repetitive tests when possible
- Maintain regression suite regularly
- Prioritize critical paths
- Run smoke tests frequently
- Update suite after each release

**DON'T:**
- Skip regression before releases
- Let suite become outdated
- Test everything every time
- Ignore failed regression tests

</details>

---

## Examples

<details>
<summary><strong>Example: Login Flow Test Case</strong></summary>

```markdown
## TC-LOGIN-001: Valid User Login

**Priority:** P0 (Critical)
**Type:** Functional
**Estimated Time:** 2 minutes

### Objective
Verify users can successfully login with valid credentials

### Preconditions
- User account exists (test@example.com / Test123!)
- User is not already logged in
- Browser cookies cleared

### Test Steps
1. Navigate to https://app.example.com/login
   **Expected:** Login page displays with email and password fields

2. Enter email: test@example.com
   **Expected:** Email field accepts input

3. Enter password: Test123!
   **Expected:** Password field shows masked characters

4. Click "Login" button
   **Expected:**
   - Loading indicator appears
   - User redirected to /dashboard
   - Welcome message shown: "Welcome back, Test User"
   - Avatar/profile image displayed in header

### Post-conditions
- User session created
- Auth token stored
- Analytics event logged

### Edge Cases to Consider
- TC-LOGIN-002: Invalid password
- TC-LOGIN-003: Non-existent email
- TC-LOGIN-004: SQL injection attempt
- TC-LOGIN-005: Very long password
```

</details>

<details>
<summary><strong>Example: Responsive Design Test Case</strong></summary>

```markdown
## TC-UI-045: Mobile Navigation Menu

**Priority:** P1 (High)
**Type:** UI/Responsive
**Devices:** Mobile (iPhone, Android)

### Objective
Verify navigation menu works correctly on mobile devices

### Preconditions
- Access from mobile device or responsive mode
- Viewport width: 375px (iPhone SE) to 428px (iPhone Pro Max)

### Test Steps
1. Open homepage on mobile device
   **Expected:** Hamburger menu icon visible (top-right)

2. Tap hamburger icon
   **Expected:**
   - Menu slides in from right
   - Overlay appears over content
   - Close (X) button visible

3. Tap menu item
   **Expected:** Navigate to section, menu closes

4. Compare against Figma mobile design [link]
   **Expected:**
   - Menu width: 280px
   - Slide animation: 300ms ease-out
   - Overlay opacity: 0.5, color #000000
   - Font size: 16px, line-height 24px

### Breakpoints to Test
- 375px (iPhone SE)
- 390px (iPhone 14)
- 428px (iPhone 14 Pro Max)
- 360px (Galaxy S21)
```

</details>

---

**"Testing shows the presence, not the absence of bugs." - Edsger Dijkstra**

**"Quality is not an act, it is a habit." - Aristotle**
