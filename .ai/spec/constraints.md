# Constraints

Project-wide invariants. If an agent violates any of these, the system is wrong.

1. The UI MUST be an OpenShift console dynamic plugin — it runs inside the OpenShift console, not as a standalone app.
2. The UI MUST NOT make direct API calls to spoke clusters. All spoke data is accessed through the hub operator's APIs/CRs on the hub cluster.
3. The UI MUST degrade gracefully when spokes are unreachable — show last-known state with a clear staleness indicator rather than failing entirely.
4. The UI MUST NOT cache or store spoke credentials. Authentication flows through the hub operator.
5. Commit messages and PR titles MUST start with `OLS-XXXX` (Jira ticket reference).
6. Fork-based git workflow: push to your fork, PR against `origin/main`.
