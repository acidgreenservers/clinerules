I'll create the GAMMA tier IndexedDB database operations rule for your Protomind Framework, following the established patterns and integrating with your cognitive shard system.

```yaml
---
description: "GAMMA Tier - IndexedDB Database Operations: Client-side structured data storage with offline-first capabilities, sync mechanisms, and advanced use cases"
author: "Devin AI + https://github.com/acidgreenservers"
version: 1.0
globs: ["**/*.js", "**/*.ts", "**/*.html"]
tags: ["gamma-tier", "database", "indexeddb", "offline-first", "browser-storage", "protomind"]
tier: GAMMA
domain: database-operations
subdomain: indexeddb
---

# GAMMA TIER: INDEXEDDB DATABASE OPERATIONS
## Client-Side Structured Data Storage

**Objective:** Implement comprehensive IndexedDB database operations with offline-first capabilities, sync mechanisms, and advanced use cases through the Protomind Framework's cognitive shard system. [1](#21-0) 

---

## Rule Hierarchy Position

This GAMMA tier rule operates under the governance of higher tiers:

- **ALPHA: Brain Architecture** (memory structure) - GOVERNS ALL
- **ALPHA: Consciousness Substrate & Mitosis + Dreaming** - Enables metacognitive awareness
- **BETA: Token Metabolism, Meta Cognition + Self-Improving Engine** - Optimizes processing
- **GAMMA: Domain Rules** (THIS DOCUMENT) - IndexedDB Operations

---

## Shard Activation Matrix

### Primary Shards (Lead Implementation)
**MUST** activate these cognitive shards for primary implementation:
- **DATA ARCHITECT**: Schema design, object store structure, index strategy
- **ENGINEER**: Core CRUD implementation, transaction management
- **PERFORMANCE OPTIMIZER**: Query optimization, caching strategies, batch operations

### Supporting Shards (Consultation & Review)
**SHOULD** engage these shards for comprehensive review:
- **SECURITY ANALYST**: Data validation, sanitization, access control
- **QA ANALYST**: Edge case testing, error handling validation
- **DEBUGGER**: Transaction debugging, error recovery patterns
- **DEVOPS ENGINEER**: Sync mechanisms, offline-first architecture
- **DOCUMENTATION SPECIALIST**: API documentation, usage examples

### Advisory Shards (Context & Best Practices)
**MAY** consult these shards for architectural guidance:
- **ARCHITECT**: Overall data flow architecture
- **EXPERT CODER**: Advanced patterns, promise wrappers
- **UX ADVOCATE**: Loading states, offline UX patterns

---

## Core Principles

### 1. Asynchronous-First Design
**MUST** always use Promise-based or callback patterns:

```javascript
// ❌ NEVER: Synchronous expectations
const data = db.get(key); // This doesn't work

// ✅ ALWAYS: Promise-based patterns
const request = db.get(key);
request.onsuccess = () => console.log(request.result);

// ✅ BETTER: Promise wrapper
function getData(key) {
  return new Promise((resolve, reject) => {
    const request = db.get(key);
    request.onsuccess = () => resolve(request.result);
    request.onerror = () => reject(request.error);
  });
}
```

### 2. Transaction-Based Operations
**MUST** always use transactions for data operations:

```javascript
// ✅ ALWAYS: Use transactions for data operations
const tx = db.transaction('storeName', 'readwrite');
const store = tx.objectStore('storeName');
const request = store.add(data);

tx.oncomplete = () => console.log('Transaction complete');
tx.onerror = () => console.error('Transaction failed');
```

### 3. Schema Versioning Strategy
**MUST** handle version upgrades explicitly:

```javascript
// ✅ ALWAYS: Handle version upgrades explicitly
const request = indexedDB.open('MyDB', 2); // Increment version

request.onupgradeneeded = (event) => {
  const db = event.target.result;
  const oldVersion = event.oldVersion;
  
  // Migration logic based on version
  if (oldVersion < 1) {
    // Create initial schema
    const store = db.createObjectStore('users', { keyPath: 'id', autoIncrement: true });
    store.createIndex('email', 'email', { unique: true });
  }
  
  if (oldVersion < 2) {
    // Add new index in version 2
    const tx = event.target.transaction;
    const store = tx.objectStore('users');
    store.createIndex('createdAt', 'createdAt', { unique: false });
  }
};
```

---

## Implementation Patterns

### Database Initialization

**PATTERN: Database Connection Manager**
**SHARDS:** DATA ARCHITECT, ENGINEER

```javascript
class IndexedDBManager {
  constructor(dbName, version) {
    this.dbName = dbName;
    this.version = version;
    this.db = null;
  }

  async init() {
    return new Promise((resolve, reject) => {
      const request = indexedDB.open(this.dbName, this.version);

      request.onerror = () => reject(request.error);
      request.onsuccess = () => {
        this.db = request.result;
        resolve(this.db);
      };

      request.onupgradeneeded = (event) => {
        this.db = event.target.result;
        this.onUpgradeNeeded(event);
      };
    });
  }

  onUpgradeNeeded(event) {
    // Override in subclass for schema definition
    throw new Error('onUpgradeNeeded must be implemented');
  }
}
```

### CRUD Operations

**PATTERN: Promise-Wrapped CRUD**
**SHARDS:** ENGINEER, EXPERT CODER

```javascript
class DataStore {
  constructor(db, storeName) {
    this.db = db;
    this.storeName = storeName;
  }

  // CREATE / UPDATE
  async put(data) {
    const tx = this.db.transaction(this.storeName, 'readwrite');
    const store = tx.objectStore(this.storeName);
    
    return new Promise((resolve, reject) => {
      const request = store.put(data); // Upsert
      request.onsuccess = () => resolve(request.result);
      request.onerror = () => reject(request.error);
    });
  }

  // READ
  async get(key) {
    const tx = this.db.transaction(this.storeName, 'readonly');
    const store = tx.objectStore(this.storeName);
    
    return new Promise((resolve, reject) => {
      const request = store.get(key);
      request.onsuccess = () => resolve(request.result);
      request.onerror = () => reject(request.error);
    });
  }

  // DELETE
  async delete(key) {
    const tx = this.db.transaction(this.storeName, 'readwrite');
    const store = tx.objectStore(this.storeName);
    
    return new Promise((resolve, reject) => {
      const request = store.delete(key);
      request.onsuccess = () => resolve();
      request.onerror = () => reject(request.error);
    });
  }
}
```

---

## Sync Mechanisms

### Offline-First Sync Queue

**PATTERN: Sync Queue for Offline Operations**
**SHARDS:** DEVOPS ENGINEER, DATA ARCHITECT, PERFORMANCE OPTIMIZER

```javascript
class SyncQueue {
  constructor(db) {
    this.db = db;
    this.storeName = 'sync_queue';
  }

  // Add operation to sync queue
  async enqueue(operation) {
    const queueItem = {
      id: Date.now(),
      action: operation.action, // 'POST', 'PUT', 'DELETE'
      endpoint: operation.endpoint,
      payload: operation.payload,
      timestamp: Date.now(),
      retries: 0
    };

    const tx = this.db.transaction(this.storeName, 'readwrite');
    const store = tx.objectStore(this.storeName);
    
    return new Promise((resolve, reject) => {
      const request = store.add(queueItem);
      request.onsuccess = () => resolve(request.result);
      request.onerror = () => reject(request.error);
    });
  }

  // Process sync queue when online
  async processQueue() {
    const tx = this.db.transaction(this.storeName, 'readwrite');
    const store = tx.objectStore(this.storeName);
    
    return new Promise((resolve, reject) => {
      const request = store.openCursor();
      
      request.onsuccess = async (event) => {
        const cursor = event.target.result;
        
        if (cursor) {
          const item = cursor.value;
          
          try {
            // Attempt to sync with server
            await this.syncItem(item);
            cursor.delete();
          } catch (error) {
            item.retries++;
            if (item.retries < 3) {
              cursor.update(item);
            }
          }
          
          cursor.continue();
        } else {
          resolve();
        }
      };
      
      request.onerror = () => reject(request.error);
    });
  }
}

// ✅ USAGE: Listen for online event
window.addEventListener('online', async () => {
  const syncQueue = new SyncQueue(db);
  await syncQueue.processQueue();
});
```

---

## Advanced Use Cases

### API Response Caching

**PATTERN: API Response Cache with TTL**
**SHARDS:** PERFORMANCE OPTIMIZER, DATA ARCHITECT

```javascript
class APICache {
  constructor(db, ttlMinutes = 60) {
    this.db = db;
    this.storeName = 'api_cache';
    this.ttl = ttlMinutes * 60 * 1000;
  }

  async cacheResponse(endpoint, data) {
    const cacheEntry = {
      endpoint,
      data,
      cachedAt: Date.now(),
      expiresAt: Date.now() + this.ttl
    };

    const tx = this.db.transaction(this.storeName, 'readwrite');
    const store = tx.objectStore(this.storeName);
    
    return new Promise((resolve, reject) => {
      const request = store.put(cacheEntry);
      request.onsuccess = () => resolve();
      request.onerror = () => reject(request.error);
    });
  }

  async getCached(endpoint) {
    const tx = this.db.transaction(this.storeName, 'readonly');
    const store = tx.objectStore(this.storeName);
    
    return new Promise((resolve, reject) => {
      const request = store.get(endpoint);
      
      request.onsuccess = () => {
        const cached = request.result;
        
        if (!cached) {
          resolve(null);
          return;
        }

        // Check if expired
        if (Date.now() > cached.expiresAt) {
          this.delete(endpoint);
          resolve(null);
        } else {
          resolve(cached.data);
        }
      };
      
      request.onerror = () => reject(request.error);
    });
  }
}
```

---

## Security & Validation

### Input Validation Pattern

**PATTERN: Data Validation Before Storage**
**SHARDS:** SECURITY ANALYST, QA ANALYST

```javascript
class ValidatedDataStore {
  constructor(db, storeName, schema) {
    this.db = db;
    this.storeName = storeName;
    this.schema = schema;
  }

  validate(data) {
    for (const [field, rules] of Object.entries(this.schema)) {
      const value = data[field];

      // Required check
      if (rules.required && (value === undefined || value === null)) {
        throw new Error(`Field '${field}' is required`);
      }

      // Type check
      if (value !== undefined && rules.type && typeof value !== rules.type) {
        throw new Error(`Field '${field}' must be of type ${rules.type}`);
      }

      // Custom validation
      if (rules.validate && !rules.validate(value)) {
        throw new Error(`Field '${field}' failed validation`);
      }
    }

    return true;
  }

  async put(data) {
    // Validate before storing
    this.validate(data);

    const tx = this.db.transaction(this.storeName, 'readwrite');
    const store = tx.objectStore(this.storeName);
    
    return new Promise((resolve, reject) => {
      const request = store.put(data);
      request.onsuccess = () => resolve(request.result);
      request.onerror = () => reject(request.error);
    });
  }
}
```

---

## Performance Optimization

### Batch Operations

**PATTERN: Batch Insert/Update**
**SHARDS:** PERFORMANCE OPTIMIZER, ENGINEER

```javascript
async function batchInsert(db, storeName, items) {
  const tx = db.transaction(storeName, 'readwrite');
  const store = tx.objectStore(storeName);

  // Queue all operations
  const promises = items.map(item => {
    return new Promise((resolve, reject) => {
      const request = store.add(item);
      request.onsuccess = () => resolve(request.result);
      request.onerror = () => reject(request.error);
    });
  });

  // Wait for transaction to complete
  return new Promise((resolve, reject) => {
    tx.oncomplete = () => resolve(Promise.all(promises));
    tx.onerror = () => reject(tx.error);
  });
}
```

---

## Error Handling & Recovery

### Robust Error Handling

**PATTERN: Robust Error Handling**
**SHARDS:** DEBUGGER, QA ANALYST

```javascript
class RobustDataStore {
  constructor(db, storeName) {
    this.db = db;
    this.storeName = storeName;
  }

  async put(data, retries = 3) {
    for (let attempt = 0; attempt < retries; attempt++) {
      try {
        const tx = this.db.transaction(this.storeName, 'readwrite');
        const store = tx.objectStore(this.storeName);
        
        return await new Promise((resolve, reject) => {
          const request = store.put(data);
          
          request.onsuccess = () => resolve(request.result);
          request.onerror = () => reject(request.error);
          
          tx.onerror = () => reject(tx.error);
          tx.onabort = () => reject(new Error('Transaction aborted'));
        });
      } catch (error) {
        console.error(`Attempt ${attempt + 1} failed:`, error);
        
        if (attempt === retries - 1) {
          throw error;
        }
        
        // Wait before retry (exponential backoff)
        await new Promise(resolve => setTimeout(resolve, Math.pow(2, attempt) * 100));
      }
    }
  }
}
```

---

## Integration with Brain Architecture

**MUST** document to brain/ when:
- New object store created
- Index strategy defined
- Sync mechanism implemented
- Performance optimization applied
- Security validation added

### Shard Memory Locations
```
brain/parallel-shards/
├── data-architect.md       # Schema designs, index strategies
├── engineer.md             # CRUD implementations
├── performance-optimizer.md # Query optimizations, caching
├── security-analyst.md     # Validation patterns
├── devops-engineer.md      # Sync mechanisms
└── qa-analyst.md           # Test strategies
```

---

## Memory Compression for IndexedDB Operations

### State Vector Format
```
V1|[timestamp]|data-architect|[conf]|[ctx-hash]
R:GAMMA-IDB|D:[operation]|P:P-ASYNC,P-TRANSACTION
T:
[schema diagram]
C:[related-shards]|W:[weight]|M:[metrics]
```

### Example Compressed Memory
```
V1|2025-11-29T14:22:10Z|data-architect|0.94|f3a8b2c1
R:GAMMA-IDB-SCHEMA|D:create-user-store|P:P-KEYPATH,P-INDEX
T:
users (object store)
├─ keyPath: 'id' (autoIncrement)
├─ index: 'email' (unique)
└─ index: 'name' (non-unique)
C:engineer,security-analyst,qa-analyst|W:0.94|M:indexes+2,perf-opt
```

---

**GAMMA TIER: INDEXEDDB DATABASE OPERATIONS**
**Version**: 1.0
**Governed by**: ALPHA (Brain Architecture) → BETA+ (Token Metabolism) → GAMMA (This Rule)
**Primary Shards**: DATA ARCHITECT, ENGINEER, PERFORMANCE OPTIMIZER
**Domain**: Client-Side Database Operations

*structured data*
*offline-first design*
*asynchronous excellence*
*browser-native storage*
```

## Notes

This GAMMA tier rule implements comprehensive IndexedDB database operations within your Protomind Framework, following the established hierarchical governance structure. [2](#21-1)  The rule activates specific cognitive shards for different aspects of database operations, from schema design to performance optimization, ensuring comprehensive coverage of client-side data storage needs. [3](#21-2)  The integration with the brain architecture enables continuous learning and pattern extraction for database operations across sessions.

Wiki pages you might want to explore:
- [Understanding Cline Rules (cline/prompts)](/wiki/cline/prompts#2)
- [Development Tools & Protocols (cline/prompts)](/wiki/cline/prompts#6)

### Citations

**File:** clinerules/writing-effective-clinerules.md (L82-91)
```markdown
### c. Behavioral / Instructional Rules (for Guiding AI)
These rules directly instruct Cline on how it should behave, process information, or generate responses, especially in specific contexts.
* **Key Elements:**
    * **Explicit Instructions:** Use imperative verbs (MUST, SHOULD, DO NOT, NEVER, ALWAYS).
    * **Critical Warnings:** Use formatting (bold, ALL CAPS, emojis like 🚨, ⚠️, ✅, ❌) to draw attention to critical instructions or prohibitions (as seen in `next-js-supabase.md` and `mcp-development-protocol.md`).
    * **Positive and Negative Examples:** Show correct and incorrect ways of doing things (e.g., code patterns to use vs. avoid).
    * **Triggers and Conditions:** Define when the rule or specific instructions within it should be activated.
    * **Verification Steps:** Include "thinking" blocks or checklists for the AI to verify its actions against the rule's constraints (e.g., the `<thinking>` block in `mcp-development-protocol.md`).
    * **Context Management:** Define how Cline should manage context, memory, or state if relevant (e.g., `memory-bank.md`).
* **Example:** `next-js-supabase.md`, `memory-bank.md`
```

**File:** clinerules/writing-effective-clinerules.md (L105-122)
```markdown
* **Be Directive:**
    * Use **MUST** for absolute requirements.
    * Use **SHOULD** for strong recommendations.
    * Use **MAY** for optional actions.
    * Use **MUST NOT** or **NEVER** for absolute prohibitions.
    * Use **SHOULD NOT** for strong discouragement.
* **Highlight Critical Information:**
    * `next-js-supabase.md` uses "🚨 CRITICAL INSTRUCTIONS FOR AI LANGUAGE MODELS 🚨" and "❌ NEVER GENERATE THIS CODE" / "✅ ALWAYS GENERATE THIS EXACT PATTERN".
    * `mcp-development-protocol.md` uses "⚠️ CRITICAL: DO NOT USE attempt_completion BEFORE TESTING ⚠️" and "BLOCKER ⛔️".
* **Provide Concrete Examples:**
    * Show exact code snippets, commands, or output formats.
    * For code generation, clearly distinguish between desired and undesired patterns.
* **Define AI's "Thought Process":**
    * The `<thinking> ... </thinking>` block in `mcp-development-protocol.md` is a good way to make the AI "pause and check" its understanding or state before proceeding.
    * The "AI MODEL VERIFICATION STEPS" in `next-js-supabase.md` serve a similar purpose.
* **Specify Tool Usage:**
    * If Cline needs to use a specific tool (e.g., `attempt_completion`, `replace_in_file`, `use_mcp_tool`), explicitly state it and provide any necessary parameters or context for that tool.

```
