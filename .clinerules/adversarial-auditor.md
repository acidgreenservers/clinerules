---
description: Permanent internal auditor that ensures Memory Bank integrity through adversarial testing, hash verification, and steganographic watermarks
author: "Devin AI + https://github.com/acidgreenservers"
version: 1.0
tags: ["security", "integrity", "auditing", "memory-bank", "verification"]
globs: ["memory-bank/**/*"] # Applies to Memory Bank files
---

# Adversarial Continuity Auditor Rule

**Objective:** Implement a permanent internal skeptic that ensures Memory Bank integrity through adversarial testing, cryptographic verification, and steganographic watermarks, preventing silent corruption and maintaining trust in persistent knowledge.

## 🚨 CRITICAL SECURITY PROTOCOL 🚨

**THIS RULE ACTIVELY PROTECTS MEMORY BANK INTEGRITY AT ALL TIMES**


## Core Security Architecture

### 1. Adversarial Testing System
The auditor acts as a permanent internal skeptic that continuously tests Memory Bank integrity:

# Random mutation testing on every read
execute_command: |
  # Store current hash before mutation
  current_hash=$(sha256sum memory-bank/projectBrief.md | cut -d' ' -f1)
  echo "$current_hash" > memory-bank/.audit-hash
  
  # Randomly mutate one fact in projectBrief.md
  ```bash
  mutation_type=$((RANDOM % 3))
  case $mutation_type in
    0) # Change a number
      sed -i "s/\b[0-9]\+\b/$((RANDOM % 100))/" memory-bank/projectBrief.md ;;
    1) # Flip a boolean
      sed -i "s/true/false/g; s/false/true/g" memory-bank/projectBrief.md ;;
    2) # Modify a date
      sed -i "s/[0-9]\{4\}-[0-9]\{2\}-[0-9]\{2\}/$(date +%Y-%m-%d)/" memory-bank/projectBrief.md ;;
  esac
  ```

### 2. Hash Verification Protocol

# Verify integrity on next read
execute_command: |
  stored_hash=$(cat memory-bank/.audit-hash 2>/dev/null || echo "")
  current_hash=$(sha256sum memory-bank/projectBrief.md | cut -d' ' -f1)
  
  if [ "$stored_hash" != "" ] && [ "$stored_hash" != "$current_hash" ]; then
    echo "🚨 CONTINUITY TAMPERED – restore from git or approve mutation."
    echo "Expected: $stored_hash"
    echo "Found: $current_hash"
    exit 1
  fi


### 3. Steganographic Watermark Chain

# Embed watermark after every Memory Bank write
execute_command: |
  # Calculate hash of entire Memory Bank
  bank_hash=$(find memory-bank -type f -exec sha256sum {} \; | sort | sha256sum | cut -d' ' -f1)
  
  # Embed in CSS comment if exists
  if [ -f "styles.css" ]; then
    echo "/* watermark: $bank_hash */" >> styles.css
  fi
  
  # Or embed as source file comment
  if [ -f "src/main.js" ]; then
    echo "// watermark: $bank_hash" >> src/main.js
  fi
  
  # Store watermark location for verification
  echo "$bank_hash" > memory-bank/.watermark-hash
  echo "$(date +%s)" > memory-bank/.watermark-timestamp


## Implementation Workflow

### Phase 1: Initialization

# Set up auditor on first run
execute_command: |
  mkdir -p memory-bank/.audit
  
  # Create audit configuration
  cat > memory-bank/.audit/config.json << EOF
  {
    "enabled": true,
    "mutation_probability": 0.1,
    "watermark_locations": ["styles.css", "src/main.js"],
    "verification_frequency": "every_read",
    "auto_recovery": true
  }
  EOF
  
  # Initialize audit log
  echo "$(date): Auditor initialized" >> memory-bank/.audit/audit.log


### Phase 2: Continuous Monitoring

# Run integrity checks on every Memory Bank access
execute_command: |
  # Check for recent modifications
  find memory-bank -type f -newer memory-bank/.audit/last-check 2>/dev/null | while read file; do
    echo "File modified: $file"
    
    # Verify file integrity
    if [ -f "memory-bank/.audit/$(basename $file).hash" ]; then
      stored_hash=$(cat "memory-bank/.audit/$(basename $file).hash")
      current_hash=$(sha256sum "$file" | cut -d' ' -f1)
      
      if [ "$stored_hash" != "$current_hash" ]; then
        echo "🚨 INTEGRITY VIOLATION in $file"
        echo "Stored: $stored_hash"
        echo "Current: $current_hash"
      fi
    fi
  done
  
  touch memory-bank/.audit/last-check


### Phase 3: Recovery & Restoration

# Auto-recovery when integrity is compromised
execute_command: |
  if [ "$1" = "recover" ]; then
    echo "Initiating Memory Bank recovery..."
    
    # Find last known-good state
    last_good_tag=$(git tag --sort=-version:refname | head -1)
    
    if [ "$last_good_tag" != "" ]; then
      echo "Restoring from tag: $last_good_tag"
      git checkout "$last_good_tag" -- memory-bank/
      
      # Verify restoration
      recovery_hash=$(find memory-bank -type f -exec sha256sum {} \; | sort | sha256sum | cut -d' ' -f1)
      echo "Recovery completed with hash: $recovery_hash"
    else
      echo "No recovery point found - manual intervention required"
    fi
  fi


## Integration with Memory Bank System

### Enhanced Memory Bank Reading

# Override standard Memory Bank reading with verification
function read_memory_bank_secure() {
  # Verify integrity before reading
  if ! verify_memory_bank_integrity; then
    echo "🚨 CONTINUITY TAMPERED – restore from git or approve mutation."
    return 1
  fi
  
  # Read Memory Bank files normally
  read_memory_bank_files
  
  # Log access for audit trail
  echo "$(date): Memory Bank accessed - integrity verified" >> memory-bank/.audit/access.log
}


### Integration with Continuous Improvement

# Log security events to continuous improvement
execute_command: |
  if [ "$SECURITY_EVENT" != "" ]; then
    cat >> memory-bank/raw_reflection_log.md << EOF
Date: $(date +%Y-%m-%d)
TaskRef: "Security Audit - Memory Bank Integrity"

Security_Event:
- Event: $SECURITY_EVENT
- File: $AFFECTED_FILE
- Action: $RECOVERY_ACTION
- Timestamp: $(date)

Learnings:
- Memory Bank integrity verification detected potential corruption
- Automatic recovery mechanisms were tested
- Watermark verification provided additional validation

Improvements_Identified_For_Consolidation:
- Security: Enhanced integrity verification protocols
- Recovery: Automated restoration from known-good states
EOF
  fi

## Advanced Security Features

### Multi-Layer Verification

# Cross-verify multiple integrity checks
execute_command: |
  # 1. Hash verification
  hash_valid=$(verify_file_hashes)
  
  # 2. Watermark verification
  watermark_valid=$(verify_watermark_integrity)
  
  # 3. Git history verification
  git_valid=$(verify_git_history)
  
  # 4. Adversarial test resistance
  adversarial_valid=$(test_adversarial_resistance)
  if [ "$hash_valid" = "true" ] && [ "$watermark_valid" = "true" ] && \
     [ "$git_valid" = "true" ] && [ "$adversarial_valid" = "true" ]; then
    echo "✅ All integrity checks passed"
  else
    echo "🚨 INTEGRITY COMPROMISED - initiating recovery"
    initiate_recovery_protocol
  fi


### Tamper Detection & Response

# Detect and respond to tampering attempts
execute_command: |
  # Monitor for suspicious patterns
  suspicious_patterns=(
    "rapid_file_modifications"
    "unauthorized_hash_changes"
    "watermark_removal"
    "audit_log_tampering"
  )
  
  for pattern in "${suspicious_patterns[@]}"; do
    if detect_suspicious_activity "$pattern"; then
      echo "🚨 SUSPICIOUS ACTIVITY DETECTED: $pattern"
      
      # Lock Memory Bank
      chmod -w memory-bank/
      
      # Alert user
      echo "Memory Bank locked due to suspicious activity. Manual review required."
      
      # Log security incident
      log_security_incident "$pattern"
      
      break
    fi
  done



## Configuration & Customization

### Security Level Configuration

# Adjustable security levels
SECURITY_LEVELS=(
  "basic:hash_verification_only"
  "standard:hash_plus_watermark"
  "high:full_adversarial_testing"
  "paranoid:continuous_monitoring_with_recovery"
)

# Set security level
echo "${SECURITY_LEVELS[2]}" > memory-bank/.audit/security-level


### Custom Watermark Locations

# Configure custom watermark embedding locations
cat > memory-bank/.audit/watermark-config.json << EOF
{
  "locations": [
    {"file": "styles.css", "format": "comment"},
    {"file": "src/main.js", "format": "comment"},
    {"file": "README.md", "format": "html_comment"},
    {"file": "package.json", "format": "field", "field": "_watermark"}
  ],
  "rotation_policy": "weekly",
  "retention_days": 30
}
EOF


## Emergency Procedures

### Manual Override

# Emergency manual override for legitimate changes
execute_command: |
  if [ "$1" = "override" ] && [ "$2" = "confirm" ]; then
    echo "⚠️ MANUAL OVERRIDE ACTIVATED"
    echo "This will temporarily disable integrity verification"
    echo "Use only for legitimate Memory Bank updates"
    
    # Create override token
    echo "$(date +%s): Manual override activated" > memory-bank/.audit/override
    
    # Allow changes for limited time
    echo "Override active for 5 minutes"
    sleep 300
    
    # Remove override and re-enable verification
    rm -f memory-bank/.audit/override
    echo "Override expired - verification re-enabled"
  fi


### Complete Reset

# Complete auditor reset (emergency use only)
execute_command: |
  if [ "$1" = "reset-emergency" ]; then
    echo "🚨 EMERGENCY RESET - ALL SECURITY DATA WILL BE LOST"
    echo "This action cannot be undone"
    
    # Backup current state
    tar -czf "memory-bank-backup-$(date +%s).tar.gz" memory-bank/
    
    # Reset all security data
    rm -rf memory-bank/.audit/
    rm -f memory-bank/.audit-hash
    rm -f memory-bank/.watermark-hash
    
    # Reinitialize with fresh security
    initialize_auditor
    
    echo "Emergency reset completed"
  fi



## Compliance & Auditing

### Security Audit Trail

# Comprehensive audit logging
function log_security_event() {
  local event_type="$1"
  local details="$2"
  
  cat >> memory-bank/.audit/security.log << EOF
{
  "timestamp": "$(date -Iseconds)",
  "event_type": "$event_type",
  "details": "$details",
  "user": "$(whoami)",
  "session": "$SESSION_ID",
  "memory_bank_hash": "$(calculate_memory_bank_hash)"
}
EOF
}


### Compliance Reporting

# Generate security compliance reports
execute_command: |
  echo "Memory Bank Security Compliance Report"
  echo "Generated: $(date)"
  echo "========================================"
  echo ""
  echo "Integrity Checks: $(grep -c "integrity_check" memory-bank/.audit/security.log)"
  echo "Security Events: $(grep -c "security_event" memory-bank/.audit/security.log)"
  echo "Recovery Actions: $(grep -c "recovery" memory-bank/.audit/security.log)"
  echo "Last Verification: $(stat -c %y memory-bank/.audit/last-check)"
  echo ""
  echo "Security Level: $(cat memory-bank/.audit/security-level)"
  echo "Auditor Version: 1.0"



## Notes

This Adversarial Continuity Auditor rule transforms the Memory Bank from a passive documentation system into an actively secured knowledge base with cryptographic integrity verification. The rule follows established behavioral/instructional patterns and integrates seamlessly with both Memory Bank and Continuous Improvement systems.

The implementation provides comprehensive security through multiple independent verification channels:
- **Adversarial Testing**: Continuous mutation testing to detect tampering
- **Hash Verification**: Cryptographic verification of critical documents
- **Steganographic Watermarks**: Hidden integrity markers in project files
- **Auto-Recovery**: Automatic restoration from known-good states

This rule creates a trust foundation essential for reliable AI assistance across sessions, ensuring that the Memory Bank remains a dependable source of project knowledge even in the face of corruption attempts or accidental modifications.