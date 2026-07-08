# Spoke Management

UI for registering, monitoring, and decommissioning spoke clusters.

## Behavioral Rules

### Spoke List View

1. The spoke list MUST show all registered `SpokeCluster` CRs with their current status (Ready, Provisioning, Degraded, Unreachable).
2. Each spoke entry MUST display: cluster name, API endpoint, status, last sync time, and active proposal count.
3. The list MUST support filtering by status and sorting by name, status, or last sync time.

### Spoke Registration

4. The UI MUST provide a guided flow for registering a new spoke cluster.
5. The registration flow collects the spoke's API endpoint and credentials, then creates a `SpokeCluster` CR.
6. After creation, the UI MUST show provisioning progress with status updates.

### Spoke Detail View

7. Drilling into a spoke MUST show: health conditions, deployed components (adapter status, operator status), recent proposals, and recent alerts.
8. The detail view MUST provide actions to decommission (delete) the spoke, with a confirmation dialog.

### Spoke Health

9. Spoke health status MUST use standard status iconography consistent with OpenShift console conventions (green/yellow/red indicators).
10. Unhealthy spokes MUST surface prominently — not buried in a list of healthy spokes.

## Planned Changes

| Ticket | Summary |
|---|---|
| — | All rules are planned — initial design |
