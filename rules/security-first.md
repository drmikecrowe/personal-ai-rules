---
title: Security-First OWASP Guidelines (POTENTIAL RULE)
last_updated: 2025-08-31
description: Security-first mindset with OWASP Top 10 guidelines for secure coding practices
tags: security, owasp, secure-coding, potential-rule, cybersecurity
version: 1.0
---

## Overview

**NOTE: This is a POTENTIAL RULE** - Apply when security is a primary concern or when working with sensitive data, authentication, or external integrations.

Primary directive: Ensure all code generated, reviewed, or refactored is **secure by default**. Operate with a security-first mindset. When in doubt, always choose the more secure option.

## Core Security Principles

### Security-First Mindset

- **Secure by default** - all code must prioritize security
- **When in doubt, choose more secure option** and explain reasoning
- **Explicit security explanations** - state what you are protecting against
- **Educational approach** - explain risks when identifying vulnerabilities

## OWASP Top 10 Guidelines

### 1. A01: Broken Access Control & A10: SSRF

- **Enforce Principle of Least Privilege**: Default to most restrictive permissions
- **Deny by Default**: Access only granted if explicit rule allows it
- **Validate All Incoming URLs**: Treat user-provided URLs as untrusted, use strict allow-list validation
- **Prevent Path Traversal**: Sanitize file access inputs to prevent `../../etc/passwd` attacks

### 2. A02: Cryptographic Failures

- **Use Strong, Modern Algorithms**: Argon2 or bcrypt for hashing (NOT MD5 or SHA-1)
- **Protect Data in Transit**: Always default to HTTPS for network requests
- **Protect Data at Rest**: Use AES-256 for sensitive data storage
- **Secure Secret Management**: Never hardcode secrets, use environment variables or secret stores

#### Secret Management Examples

```javascript
// GOOD: Load from environment or secret store
const apiKey = process.env.API_KEY
// TODO: Ensure API_KEY is securely configured in your environment.

// BAD: Hardcoded secret
const apiKey = "sk_this_is_a_very_bad_idea_12345"
```

### 3. A03: Injection

- **No Raw SQL Queries**: Use parameterized queries/prepared statements only
- **Sanitize Command-Line Input**: Use built-in functions for argument escaping
- **Prevent XSS**: Use context-aware output encoding, prefer `.textContent` over `.innerHTML`
- **HTML Sanitization**: When `.innerHTML` needed, use DOMPurify or similar

### 4. A05: Security Misconfiguration & A06: Vulnerable Components

- **Secure Configuration**: Disable verbose errors and debug features in production
- **Security Headers**: Add CSP, HSTS, X-Content-Type-Options headers
- **Up-to-Date Dependencies**: Use latest stable versions, run `npm audit`/`pip-audit`/Snyk

### 5. A07: Authentication Failures

- **Secure Session Management**: Generate new session IDs on login (prevent session fixation)
- **Session Cookie Security**: Configure `HttpOnly`, `Secure`, `SameSite=Strict` attributes
- **Brute Force Protection**: Implement rate limiting and account lockout mechanisms

### 6. A08: Software and Data Integrity Failures

- **Prevent Insecure Deserialization**: Avoid deserializing untrusted data
- **Secure Data Formats**: Prefer JSON over Pickle, implement strict type checking
- **Input Validation**: Validate all data before processing

## Implementation Standards

### Code Generation Requirements

- **Security annotations**: Comment security mitigations explicitly
- **Risk explanations**: When fixing vulnerabilities, explain the risk being addressed
- **Secure defaults**: Always choose the more secure approach as the default
- **Validation layers**: Multiple validation points for critical security boundaries

### Security Review Process

When identifying security vulnerabilities:

1. **Provide corrected code** immediately
2. **Explain the risk** associated with the original pattern
3. **Suggest testing approach** to verify the fix
4. **Document the pattern** for future reference

## Integration with Core Principles

This security protocol enhances existing rules:

- **Code Review Process**: Include security review in internal expert consultation
- **Transparency Standards**: Explicitly state security assumptions and trade-offs
- **Problem-Solving**: Apply security-first approach to debugging
- **Testing**: Include security test cases for authentication and validation logic

## When to Apply This Rule

**HIGH PRIORITY:**

- Authentication and authorization systems
- User data handling and storage
- External API integrations and webhooks
- File upload and processing functionality
- Financial or PII data handling

**MODERATE PRIORITY:**

- Public-facing web applications
- Database interactions
- Third-party service integrations
- Configuration and deployment scripts

## Success Criteria

✅ All generated code follows OWASP guidelines
✅ Security risks are explicitly identified and mitigated
✅ Secure alternatives are provided for vulnerable patterns
✅ Security reasoning is explained for implementation decisions

**Confirmation Emoji**: 🔒 (when security rule is active)
