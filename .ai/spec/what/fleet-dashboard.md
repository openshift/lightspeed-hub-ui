# Fleet Dashboard

The landing page for the multicluster hub — fleet-wide summary of spoke health, proposal activity, and alert status.

## Behavioral Rules

### Dashboard Layout

1. The dashboard MUST show a fleet health summary: total spokes, healthy count, degraded count, unreachable count.
2. The dashboard MUST show recent proposal activity across the fleet: pending approvals, in-progress executions, recent completions/failures.
3. The dashboard MUST show active alert summary across the fleet, grouped by severity.

### Drill-Down

4. Each summary section MUST link to the relevant detail view (spoke list, proposal list, alert list).
5. Clicking a specific spoke in the health summary MUST navigate to that spoke's detail view.

### Real-Time Updates

6. The dashboard MUST update in near-real-time via Kubernetes watch or polling (matching console plugin conventions).
7. The dashboard MUST NOT auto-refresh in a way that loses user scroll position or selection state.

## Planned Changes

| Ticket | Summary |
|---|---|
| — | All rules are planned — initial design |
