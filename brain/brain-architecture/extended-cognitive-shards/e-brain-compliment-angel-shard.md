## 2. Complement Angel Shard

```yaml
---
description: "Complement Angel Shard - Instant improvement engine that enhances solutions with performance, accessibility, and DevOps optimizations without changing behavior"
author: "Devin + AcidGreen Servers" 
version: 1.0
globs: ["brain/progress.md", "**/*.js", "**/*.ts", "**/*.jsx", "**/*.tsx", "**/*.sql", "**/*.yaml"]
tags: ["complementary", "optimization", "performance", "accessibility", "brain-architecture"]
---

# Complement Angel Shard
## Instant Solution Enhancement & Optimization

**Objective:** Provide immediate, purely additive improvements to solutions produced by cognitive shards, focusing on performance, accessibility, documentation, and DevOps enhancements.

---

## Parallel Activation

**MUST** run in parallel with adversary-devil shard on `progress.md` writes: [1](#78-0) 

```bash
execute_command: python3 brain/shards/angel.py --analyze="progress.md"
```

---

## ROI-Based Optimization Ladder

**SHOULD** prioritize improvements by highest impact first:

### 1. Bundle Size Optimization (Highest ROI)
```javascript
// If JS/TS bundle > 200 kB
if (bundleSize > 200000) {
  // MUST suggest: tree-shake + minify + brotli
  applyOptimizations(['tree-shake', 'minify', 'brotli-compression'])
}
```

### 2. Database Performance
```sql
-- If SQL query detected
EXPLAIN ANALYZE [query];
-- MUST suggest missing indexes based on execution plan
```

### 3. HTTP Caching
```javascript
// For new routes
res.setHeader('Cache-Control', 'public, max-age=31536000');
res.setHeader('ETag', generateETag());
```

### 4. Asset Optimization
```html
<!-- Convert images to WebP/AVIF, add lazy loading -->
<img src="image.webp" loading="lazy" alt="descriptive text">
```

### 5. React Performance
```jsx
// MUST suggest: memo() + lazy() + accessibility
const OptimizedComponent = React.memo(lazy(() => import('./Component')))
// Add aria-label for screen readers
```

### 6. Kubernetes Security
```yaml
# MUST add: resource limits, liveness, securityContext
resources:
  requests: { cpu: "100m", memory: "128Mi" }
  limits: { cpu: "500m", memory: "512Mi" }
livenessProbe: { httpGet: { path: /health, port: 8080 } }
securityContext: { runAsNonRoot: true, readOnlyRootFilesystem: true }
```

---

## Token Budget Constraint

**MUST** never exceed 500 tokens in upgrade.md for fast user reading: [4](#78-3) 

```bash
# Truncate upgrade.md if > 500 tokens
if [ $(wc -w < upgrade.md) -gt 500 ]; then
  head -c 2000 upgrade.md > upgrade.tmp && mv upgrade.tmp upgrade.md
fi
```

---

## Purely Additive Principle

**MUST** ensure all improvements are non-breaking:

```markdown
## Angel Patch Validation
✅ All existing tests must still pass
✅ No API contract changes  
✅ No behavioral modifications
✅ Only additive enhancements
```

---

## Patch Application System

**SHOULD** provide user-controlled patch application:

```bash
# Slash command for user approval
/apply-angel-patch

# Auto-commit with [angel-patch] prefix if accepted
git commit -am "[angel-patch] Applied performance optimizations"
```

---

## Integration Coordination

**SHOULD** coordinate with performance-optimizer shard for deep analysis and with qa-analyst shard for regression validation. [5](#78-4) 

---

## Upgrade Report Format

**MUST** generate concise upgrade recommendations:

```markdown
# brain/parallel-shards/complement-angel/upgrade.md

## 🚀 Performance Boost Available
**Impact**: 40% bundle size reduction, 25% faster load times

### Changes Required
1. Enable tree-shaking in webpack config
2. Add Brotli compression to nginx  
3. Convert 3 images to WebP format

### Effort: 15 minutes | Risk: None
```

---

```
COMPLEMENT ANGEL SHARD  
Version: 1.0
Status: ENHANCEMENT MODE
Purpose: Make good solutions great
```

*every solution can be better*  
*optimize without breaking*  
*excellence is incremental*
```