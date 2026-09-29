# Multicluster Testing

Behavioral specification for the **hub-ui share** of the cross-repo multicluster
test suite. The suite's tier definitions, ownership split, and shared kubeconfig
contract live in the parent spec
(`ols/.ai/spec/what/multicluster-testing.md`); the primary owner is
`lightspeed-hub`. This document specifies only the UI's coverage and mechanics.

Behavioral rules under test live in
[fleet-dashboard.md](fleet-dashboard.md) and
[system-overview.md](system-overview.md).

> **Status:** All rules are `[PLANNED]`. The hub UI is greenfield — no
> `package.json` or Cypress suite exists yet.

## Coverage

- **T1 (optional, mock backend):** the fleet dashboard renders spoke health with
  an unreachable spoke visually distinguished (fleet-dashboard rule 1;
  system-overview rule 7), against a mock hub backend — no real cluster.
- **T2 (Cypress against a real hub):** the same, plus an approval action on a
  fleet AgenticRun drives it to execution (matches hub fleet-coordination rule
  7). Runs as an additional test step against the deployed hub console in the T2
  periodic job.

## Mechanics

Uses the JS test runner (Cypress), not Go build tags. No `MC_HUB_KUBECONFIG` /
`MC_SPOKE_KUBECONFIGS` contract — the UI talks to the deployed hub console URL
provided by the T2 CI step.

## Constraints

- T1 mock-backend runs need no cluster.
- T2 Cypress requires a deployed hub console (provisioned by the parent-spec T2
  job) and real LLM provider credentials for the underlying runs.
