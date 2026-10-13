---
name: frontend
description: Comprehensive frontend development skill for building modern, performant web applications using ReactJS, NextJS, TypeScript, Tailwind CSS. Includes component scaffolding, performance optimization, bundle analysis, and UI best practices. Use when developing frontend features, optimizing performance, implementing UI/UX designs, managing state, or reviewing frontend code. Frontend development guidelines for React/TypeScript applications. Modern patterns including Suspense, lazy loading, useSuspenseQuery, file organization with features directory, MUI v7 styling, TanStack Router, performance optimization, and TypeScript best practices. Use when creating components, pages, features, fetching data, styling, routing, or working with frontend code. Comprehensive React and Next.js performance optimization guide with 40+ rules for eliminating waterfalls, optimizing bundles, and improving rendering. Use when optimizing React apps, reviewing performance, or refactoring components. Modern React patterns and principles. Hooks, composition, performance, TypeScript best practices.
---


# Senior Frontend

Complete toolkit for senior frontend with modern tools and best practices.

## Quick Start

### Main Capabilities

This skill provides three core capabilities through automated scripts:

```bash
# Script 1: Component Generator
python scripts/component_generator.py [options]

# Script 2: Bundle Analyzer
python scripts/bundle_analyzer.py [options]

# Script 3: Frontend Scaffolder
python scripts/frontend_scaffolder.py [options]
```

## Core Capabilities

### 1. Component Generator

Automated tool for component generator tasks.

**Features:**
- Automated scaffolding
- Best practices built-in
- Configurable templates
- Quality checks

**Usage:**
```bash
python scripts/component_generator.py <project-path> [options]
```

### 2. Bundle Analyzer

Comprehensive analysis and optimization tool.

**Features:**
- Deep analysis
- Performance metrics
- Recommendations
- Automated fixes

**Usage:**
```bash
python scripts/bundle_analyzer.py <target-path> [--verbose]
```

### 3. Frontend Scaffolder

Advanced tooling for specialized tasks.

**Features:**
- Expert-level automation
- Custom configurations
- Integration ready
- Production-grade output

**Usage:**
```bash
python scripts/frontend_scaffolder.py [arguments] [options]
```

## Reference Documentation

### React Patterns

Comprehensive guide available in `references/react_patterns.md`:

- Detailed patterns and practices
- Code examples
- Best practices
- Anti-patterns to avoid
- Real-world scenarios

### Nextjs Optimization Guide

Complete workflow documentation in `references/nextjs_optimization_guide.md`:

- Step-by-step processes
- Optimization strategies
- Tool integrations
- Performance tuning
- Troubleshooting guide

### Frontend Best Practices

Technical reference guide in `references/frontend_best_practices.md`:

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
python scripts/bundle_analyzer.py .

# Review recommendations
# Apply fixes
```

### 3. Implement Best Practices

Follow the patterns and practices documented in:
- `references/react_patterns.md`
- `references/nextjs_optimization_guide.md`
- `references/frontend_best_practices.md`

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
python scripts/bundle_analyzer.py .
python scripts/frontend_scaffolder.py --analyze

# Deployment
docker build -t app:latest .
docker-compose up -d
kubectl apply -f k8s/
```

## Troubleshooting

### Common Issues

Check the comprehensive troubleshooting section in `references/frontend_best_practices.md`.

### Getting Help

- Review reference documentation
- Check script output messages
- Consult tech stack documentation
- Review error logs

## Resources

- Pattern Reference: `references/react_patterns.md`
- Workflow Guide: `references/nextjs_optimization_guide.md`
- Technical Guide: `references/frontend_best_practices.md`
- Tool Scripts: `scripts/` directory


---

<!-- merged-in: development/frontend-dev-guidelines, web-development/react-best-practices, development/react-patterns -->


# Merged section: frontend-dev-guidelines (from development/frontend-dev-guidelines)
Supporting files from this skill live in `references/frontend-dev-guidelines/`, `scripts/frontend-dev-guidelines/`, `data/frontend-dev-guidelines/` (whichever exist).

# Frontend Development Guidelines

## Purpose

Comprehensive guide for modern React development, emphasizing Suspense-based data fetching, lazy loading, proper file organization, and performance optimization.

## When to Use This Skill

- Creating new components or pages
- Building new features
- Fetching data with TanStack Query
- Setting up routing with TanStack Router
- Styling components with MUI v7
- Performance optimization
- Organizing frontend code
- TypeScript best practices

---

## Quick Start

### New Component Checklist

Creating a component? Follow this checklist:

- [ ] Use `React.FC<Props>` pattern with TypeScript
- [ ] Lazy load if heavy component: `React.lazy(() => import())`
- [ ] Wrap in `<SuspenseLoader>` for loading states
- [ ] Use `useSuspenseQuery` for data fetching
- [ ] Import aliases: `@/`, `~types`, `~components`, `~features`
- [ ] Styles: Inline if <100 lines, separate file if >100 lines
- [ ] Use `useCallback` for event handlers passed to children
- [ ] Default export at bottom
- [ ] No early returns with loading spinners
- [ ] Use `useMuiSnackbar` for user notifications

### New Feature Checklist

Creating a feature? Set up this structure:

- [ ] Create `features/{feature-name}/` directory
- [ ] Create subdirectories: `api/`, `components/`, `hooks/`, `helpers/`, `types/`
- [ ] Create API service file: `api/{feature}Api.ts`
- [ ] Set up TypeScript types in `types/`
- [ ] Create route in `routes/{feature-name}/index.tsx`
- [ ] Lazy load feature components
- [ ] Use Suspense boundaries
- [ ] Export public API from feature `index.ts`

---

## Import Aliases Quick Reference

| Alias | Resolves To | Example |
|-------|-------------|---------|
| `@/` | `src/` | `import { apiClient } from '@/lib/apiClient'` |
| `~types` | `src/types` | `import type { User } from '~types/user'` |
| `~components` | `src/components` | `import { SuspenseLoader } from '~components/SuspenseLoader'` |
| `~features` | `src/features` | `import { authApi } from '~features/auth'` |

Defined in: [vite.config.ts](../../vite.config.ts) lines 180-185

---

## Common Imports Cheatsheet

```typescript
// React & Lazy Loading
import React, { useState, useCallback, useMemo } from 'react';
const Heavy = React.lazy(() => import('./Heavy'));

// MUI Components
import { Box, Paper, Typography, Button, Grid } from '@mui/material';
import type { SxProps, Theme } from '@mui/material';

// TanStack Query (Suspense)
import { useSuspenseQuery, useQueryClient } from '@tanstack/react-query';

// TanStack Router
import { createFileRoute } from '@tanstack/react-router';

// Project Components
import { SuspenseLoader } from '~components/SuspenseLoader';

// Hooks
import { useAuth } from '@/hooks/useAuth';
import { useMuiSnackbar } from '@/hooks/useMuiSnackbar';

// Types
import type { Post } from '~types/post';
```

---

## Topic Guides

### 🎨 Component Patterns

**Modern React components use:**
- `React.FC<Props>` for type safety
- `React.lazy()` for code splitting
- `SuspenseLoader` for loading states
- Named const + default export pattern

**Key Concepts:**
- Lazy load heavy components (DataGrid, charts, editors)
- Always wrap lazy components in Suspense
- Use SuspenseLoader component (with fade animation)
- Component structure: Props → Hooks → Handlers → Render → Export

**[📖 Complete Guide: resources/component-patterns.md](resources/component-patterns.md)**

---

### 📊 Data Fetching

**PRIMARY PATTERN: useSuspenseQuery**
- Use with Suspense boundaries
- Cache-first strategy (check grid cache before API)
- Replaces `isLoading` checks
- Type-safe with generics

**API Service Layer:**
- Create `features/{feature}/api/{feature}Api.ts`
- Use `apiClient` axios instance
- Centralized methods per feature
- Route format: `/form/route` (NOT `/api/form/route`)

**[📖 Complete Guide: resources/data-fetching.md](resources/data-fetching.md)**

---

### 📁 File Organization

**features/ vs components/:**
- `features/`: Domain-specific (posts, comments, auth)
- `components/`: Truly reusable (SuspenseLoader, CustomAppBar)

**Feature Subdirectories:**
```
features/
  my-feature/
    api/          # API service layer
    components/   # Feature components
    hooks/        # Custom hooks
    helpers/      # Utility functions
    types/        # TypeScript types
```

**[📖 Complete Guide: resources/file-organization.md](resources/file-organization.md)**

---

### 🎨 Styling

**Inline vs Separate:**
- <100 lines: Inline `const styles: Record<string, SxProps<Theme>>`
- >100 lines: Separate `.styles.ts` file

**Primary Method:**
- Use `sx` prop for MUI components
- Type-safe with `SxProps<Theme>`
- Theme access: `(theme) => theme.palette.primary.main`

**MUI v7 Grid:**
```typescript
<Grid size={{ xs: 12, md: 6 }}>  // ✅ v7 syntax
<Grid xs={12} md={6}>             // ❌ Old syntax
```

**[📖 Complete Guide: resources/styling-guide.md](resources/styling-guide.md)**

---

### 🛣️ Routing

**TanStack Router - Folder-Based:**
- Directory: `routes/my-route/index.tsx`
- Lazy load components
- Use `createFileRoute`
- Breadcrumb data in loader

**Example:**
```typescript
import { createFileRoute } from '@tanstack/react-router';
import { lazy } from 'react';

const MyPage = lazy(() => import('@/features/my-feature/components/MyPage'));

export const Route = createFileRoute('/my-route/')({
    component: MyPage,
    loader: () => ({ crumb: 'My Route' }),
});
```

**[📖 Complete Guide: resources/routing-guide.md](resources/routing-guide.md)**

---

### ⏳ Loading & Error States

**CRITICAL RULE: No Early Returns**

```typescript
// ❌ NEVER - Causes layout shift
if (isLoading) {
    return <LoadingSpinner />;
}

// ✅ ALWAYS - Consistent layout
<SuspenseLoader>
    <Content />
</SuspenseLoader>
```

**Why:** Prevents Cumulative Layout Shift (CLS), better UX

**Error Handling:**
- Use `useMuiSnackbar` for user feedback
- NEVER `react-toastify`
- TanStack Query `onError` callbacks

**[📖 Complete Guide: resources/loading-and-error-states.md](resources/loading-and-error-states.md)**

---

### ⚡ Performance

**Optimization Patterns:**
- `useMemo`: Expensive computations (filter, sort, map)
- `useCallback`: Event handlers passed to children
- `React.memo`: Expensive components
- Debounced search (300-500ms)
- Memory leak prevention (cleanup in useEffect)

**[📖 Complete Guide: resources/performance.md](resources/performance.md)**

---

### 📘 TypeScript

**Standards:**
- Strict mode, no `any` type
- Explicit return types on functions
- Type imports: `import type { User } from '~types/user'`
- Component prop interfaces with JSDoc

**[📖 Complete Guide: resources/typescript-standards.md](resources/typescript-standards.md)**

---

### 🔧 Common Patterns

**Covered Topics:**
- React Hook Form with Zod validation
- DataGrid wrapper contracts
- Dialog component standards
- `useAuth` hook for current user
- Mutation patterns with cache invalidation

**[📖 Complete Guide: resources/common-patterns.md](resources/common-patterns.md)**

---

### 📚 Complete Examples

**Full working examples:**
- Modern component with all patterns
- Complete feature structure
- API service layer
- Route with lazy loading
- Suspense + useSuspenseQuery
- Form with validation

**[📖 Complete Guide: resources/complete-examples.md](resources/complete-examples.md)**

---

## Navigation Guide

| Need to... | Read this resource |
|------------|-------------------|
| Create a component | [component-patterns.md](resources/component-patterns.md) |
| Fetch data | [data-fetching.md](resources/data-fetching.md) |
| Organize files/folders | [file-organization.md](resources/file-organization.md) |
| Style components | [styling-guide.md](resources/styling-guide.md) |
| Set up routing | [routing-guide.md](resources/routing-guide.md) |
| Handle loading/errors | [loading-and-error-states.md](resources/loading-and-error-states.md) |
| Optimize performance | [performance.md](resources/performance.md) |
| TypeScript types | [typescript-standards.md](resources/typescript-standards.md) |
| Forms/Auth/DataGrid | [common-patterns.md](resources/common-patterns.md) |
| See full examples | [complete-examples.md](resources/complete-examples.md) |

---

## Core Principles

1. **Lazy Load Everything Heavy**: Routes, DataGrid, charts, editors
2. **Suspense for Loading**: Use SuspenseLoader, not early returns
3. **useSuspenseQuery**: Primary data fetching pattern for new code
4. **Features are Organized**: api/, components/, hooks/, helpers/ subdirs
5. **Styles Based on Size**: <100 inline, >100 separate
6. **Import Aliases**: Use @/, ~types, ~components, ~features
7. **No Early Returns**: Prevents layout shift
8. **useMuiSnackbar**: For all user notifications

---

## Quick Reference: File Structure

```
src/
  features/
    my-feature/
      api/
        myFeatureApi.ts       # API service
      components/
        MyFeature.tsx         # Main component
        SubComponent.tsx      # Related components
      hooks/
        useMyFeature.ts       # Custom hooks
        useSuspenseMyFeature.ts  # Suspense hooks
      helpers/
        myFeatureHelpers.ts   # Utilities
      types/
        index.ts              # TypeScript types
      index.ts                # Public exports

  components/
    SuspenseLoader/
      SuspenseLoader.tsx      # Reusable loader
    CustomAppBar/
      CustomAppBar.tsx        # Reusable app bar

  routes/
    my-route/
      index.tsx               # Route component
      create/
        index.tsx             # Nested route
```

---

## Modern Component Template (Quick Copy)

```typescript
import React, { useState, useCallback } from 'react';
import { Box, Paper } from '@mui/material';
import { useSuspenseQuery } from '@tanstack/react-query';
import { featureApi } from '../api/featureApi';
import type { FeatureData } from '~types/feature';

interface MyComponentProps {
    id: number;
    onAction?: () => void;
}

export const MyComponent: React.FC<MyComponentProps> = ({ id, onAction }) => {
    const [state, setState] = useState<string>('');

    const { data } = useSuspenseQuery({
        queryKey: ['feature', id],
        queryFn: () => featureApi.getFeature(id),
    });

    const handleAction = useCallback(() => {
        setState('updated');
        onAction?.();
    }, [onAction]);

    return (
        <Box sx={{ p: 2 }}>
            <Paper sx={{ p: 3 }}>
                {/* Content */}
            </Paper>
        </Box>
    );
};

export default MyComponent;
```

For complete examples, see [resources/complete-examples.md](resources/complete-examples.md)

---

## Related Skills

- **error-tracking**: Error tracking with Sentry (applies to frontend too)
- **backend-dev-guidelines**: Backend API patterns that frontend consumes

---

**Skill Status**: Modular structure with progressive loading for optimal context management


# Merged section: react-best-practices (from web-development/react-best-practices)
Supporting files from this skill live in `references/react-best-practices/`, `scripts/react-best-practices/`, `data/react-best-practices/` (whichever exist).

# React Best Practices - Performance Optimization

Comprehensive performance optimization guide for React and Next.js applications with 40+ rules organized by impact level. Designed to help developers eliminate performance bottlenecks and follow best practices.

## When to use this skill

**Use React Best Practices when:**
- Optimizing React or Next.js application performance
- Reviewing code for performance improvements
- Refactoring existing components for better performance
- Implementing new features with performance in mind
- Debugging slow rendering or loading issues
- Reducing bundle size
- Eliminating request waterfalls

**Key areas covered:**
- **Eliminating Waterfalls** (CRITICAL): Prevent sequential async operations
- **Bundle Size Optimization** (CRITICAL): Reduce initial JavaScript payload
- **Server-Side Performance** (HIGH): Optimize RSC and data fetching
- **Client-Side Data Fetching** (MEDIUM-HIGH): Implement efficient caching
- **Re-render Optimization** (MEDIUM): Minimize unnecessary re-renders
- **Rendering Performance** (MEDIUM): Optimize browser rendering
- **JavaScript Performance** (LOW-MEDIUM): Micro-optimizations for hot paths
- **Advanced Patterns** (LOW): Specialized techniques for edge cases

## Quick reference

### Critical priorities

1. **Defer await until needed** - Move awaits into branches where they're used
2. **Use Promise.all()** - Parallelize independent async operations
3. **Avoid barrel imports** - Import directly from source files
4. **Dynamic imports** - Lazy-load heavy components
5. **Strategic Suspense** - Stream content while showing layout

### Common patterns

**Parallel data fetching:**
```typescript
const [user, posts, comments] = await Promise.all([
  fetchUser(),
  fetchPosts(),
  fetchComments()
])
```

**Direct imports:**
```tsx
// ❌ Loads entire library
import { Check } from 'lucide-react'

// ✅ Loads only what you need
import Check from 'lucide-react/dist/esm/icons/check'
```

**Dynamic components:**
```tsx
import dynamic from 'next/dynamic'

const MonacoEditor = dynamic(
  () => import('./monaco-editor'),
  { ssr: false }
)
```

## Using the guidelines

The complete performance guidelines are available in the references folder:

- **react-performance-guidelines.md**: Complete guide with all 40+ rules, code examples, and impact analysis

Each rule includes:
- Incorrect/correct code comparisons
- Specific impact metrics
- When to apply the optimization
- Real-world examples

## Categories overview

### 1. Eliminating Waterfalls (CRITICAL)
Waterfalls are the #1 performance killer. Each sequential await adds full network latency.
- Defer await until needed
- Dependency-based parallelization
- Prevent waterfall chains in API routes
- Promise.all() for independent operations
- Strategic Suspense boundaries

### 2. Bundle Size Optimization (CRITICAL)
Reducing initial bundle size improves Time to Interactive and Largest Contentful Paint.
- Avoid barrel file imports
- Conditional module loading
- Defer non-critical third-party libraries
- Dynamic imports for heavy components
- Preload based on user intent

### 3. Server-Side Performance (HIGH)
Optimize server-side rendering and data fetching.
- Cross-request LRU caching
- Minimize serialization at RSC boundaries
- Parallel data fetching with component composition
- Per-request deduplication with React.cache()

### 4. Client-Side Data Fetching (MEDIUM-HIGH)
Automatic deduplication and efficient data fetching patterns.
- Deduplicate global event listeners
- Use SWR for automatic deduplication

### 5. Re-render Optimization (MEDIUM)
Reduce unnecessary re-renders to minimize wasted computation.
- Defer state reads to usage point
- Extract to memoized components
- Narrow effect dependencies
- Subscribe to derived state
- Use lazy state initialization
- Use transitions for non-urgent updates

### 6. Rendering Performance (MEDIUM)
Optimize the browser rendering process.
- Animate SVG wrapper instead of SVG element
- CSS content-visibility for long lists
- Hoist static JSX elements
- Optimize SVG precision
- Prevent hydration mismatch without flickering
- Use Activity component for show/hide
- Use explicit conditional rendering

### 7. JavaScript Performance (LOW-MEDIUM)
Micro-optimizations for hot paths.
- Batch DOM CSS changes
- Build index maps for repeated lookups
- Cache property access in loops
- Cache repeated function calls
- Cache storage API calls
- Combine multiple array iterations
- Early length check for array comparisons
- Early return from functions
- Hoist RegExp creation
- Use loop for min/max instead of sort
- Use Set/Map for O(1) lookups
- Use toSorted() instead of sort()

### 8. Advanced Patterns (LOW)
Specialized techniques for edge cases.
- Store event handlers in refs
- useLatest for stable callback refs

## Implementation approach

When optimizing a React application:

1. **Profile first**: Use React DevTools Profiler and browser performance tools to identify bottlenecks
2. **Focus on critical paths**: Start with eliminating waterfalls and reducing bundle size
3. **Measure impact**: Verify improvements with metrics (LCP, TTI, FID)
4. **Apply incrementally**: Don't over-optimize prematurely
5. **Test thoroughly**: Ensure optimizations don't break functionality

## Key metrics to track

- **Time to Interactive (TTI)**: When page becomes fully interactive
- **Largest Contentful Paint (LCP)**: When main content is visible
- **First Input Delay (FID)**: Responsiveness to user interactions
- **Cumulative Layout Shift (CLS)**: Visual stability
- **Bundle size**: Initial JavaScript payload
- **Server response time**: TTFB for server-rendered content

## Common pitfalls to avoid

❌ **Don't:**
- Use barrel imports from large libraries
- Block parallel operations with sequential awaits
- Re-render entire trees when only part needs updating
- Load analytics/tracking in the critical path
- Mutate arrays with .sort() instead of .toSorted()
- Create RegExp or heavy objects inside render

✅ **Do:**
- Import directly from source files
- Use Promise.all() for independent operations
- Memoize expensive components
- Lazy-load non-critical code
- Use immutable array methods
- Hoist static objects outside components

## Resources

- [React Documentation](https://react.dev)
- [Next.js Documentation](https://nextjs.org)
- [SWR Documentation](https://swr.vercel.app)
- [Vercel Bundle Optimization](https://vercel.com/blog/how-we-optimized-package-imports-in-next-js)
- [Vercel Dashboard Performance](https://vercel.com/blog/how-we-made-the-vercel-dashboard-twice-as-fast)
- [better-all Library](https://github.com/shuding/better-all)
- [node-lru-cache](https://github.com/isaacs/node-lru-cache)

## Version history

**v0.1.0** (January 2026)
- Initial release from Vercel Engineering
- 40+ performance rules across 8 categories
- Comprehensive code examples and impact analysis


# Merged section: react-patterns (from development/react-patterns)
Supporting files from this skill live in `references/react-patterns/`, `scripts/react-patterns/`, `data/react-patterns/` (whichever exist).

# React Patterns

> Principles for building production-ready React applications.

---

## 1. Component Design Principles

### Component Types

| Type | Use | State |
|------|-----|-------|
| **Server** | Data fetching, static | None |
| **Client** | Interactivity | useState, effects |
| **Presentational** | UI display | Props only |
| **Container** | Logic/state | Heavy state |

### Design Rules

- One responsibility per component
- Props down, events up
- Composition over inheritance
- Prefer small, focused components

---

## 2. Hook Patterns

### When to Extract Hooks

| Pattern | Extract When |
|---------|-------------|
| **useLocalStorage** | Same storage logic needed |
| **useDebounce** | Multiple debounced values |
| **useFetch** | Repeated fetch patterns |
| **useForm** | Complex form state |

### Hook Rules

- Hooks at top level only
- Same order every render
- Custom hooks start with "use"
- Clean up effects on unmount

---

## 3. State Management Selection

| Complexity | Solution |
|------------|----------|
| Simple | useState, useReducer |
| Shared local | Context |
| Server state | React Query, SWR |
| Complex global | Zustand, Redux Toolkit |

### State Placement

| Scope | Where |
|-------|-------|
| Single component | useState |
| Parent-child | Lift state up |
| Subtree | Context |
| App-wide | Global store |

---

## 4. React 19 Patterns

### New Hooks

| Hook | Purpose |
|------|---------|
| **useActionState** | Form submission state |
| **useOptimistic** | Optimistic UI updates |
| **use** | Read resources in render |

### Compiler Benefits

- Automatic memoization
- Less manual useMemo/useCallback
- Focus on pure components

---

## 5. Composition Patterns

### Compound Components

- Parent provides context
- Children consume context
- Flexible slot-based composition
- Example: Tabs, Accordion, Dropdown

### Render Props vs Hooks

| Use Case | Prefer |
|----------|--------|
| Reusable logic | Custom hook |
| Render flexibility | Render props |
| Cross-cutting | Higher-order component |

---

## 6. Performance Principles

### When to Optimize

| Signal | Action |
|--------|--------|
| Slow renders | Profile first |
| Large lists | Virtualize |
| Expensive calc | useMemo |
| Stable callbacks | useCallback |

### Optimization Order

1. Check if actually slow
2. Profile with DevTools
3. Identify bottleneck
4. Apply targeted fix

---

## 7. Error Handling

### Error Boundary Usage

| Scope | Placement |
|-------|-----------|
| App-wide | Root level |
| Feature | Route/feature level |
| Component | Around risky component |

### Error Recovery

- Show fallback UI
- Log error
- Offer retry option
- Preserve user data

---

## 8. TypeScript Patterns

### Props Typing

| Pattern | Use |
|---------|-----|
| Interface | Component props |
| Type | Unions, complex |
| Generic | Reusable components |

### Common Types

| Need | Type |
|------|------|
| Children | ReactNode |
| Event handler | MouseEventHandler |
| Ref | RefObject<Element> |

---

## 9. Testing Principles

| Level | Focus |
|-------|-------|
| Unit | Pure functions, hooks |
| Integration | Component behavior |
| E2E | User flows |

### Test Priorities

- User-visible behavior
- Edge cases
- Error states
- Accessibility

---

## 10. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Prop drilling deep | Use context |
| Giant components | Split smaller |
| useEffect for everything | Server components |
| Premature optimization | Profile first |
| Index as key | Stable unique ID |

---

> **Remember:** React is about composition. Build small, combine thoughtfully.
