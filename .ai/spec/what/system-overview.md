# System Overview

The Lightspeed Hub UI is an OpenShift console dynamic plugin that provides the user interface for the multicluster hub. It renders fleet-wide dashboards, spoke management views, aggregated proposal lists, and hub-level policy configuration. It communicates exclusively with the hub cluster's Kubernetes API (reading SpokeCluster CRs, hub-aggregated proposals, etc.) — never directly with spoke clusters.

## Behavioral Rules

### System Role

1. The hub UI is a console plugin registered with the OpenShift console on the hub cluster.
2. All data is fetched from the hub cluster's Kubernetes API. The hub operator is responsible for aggregating spoke data into hub-side CRs.
3. The UI MUST present fleet-wide views as the primary navigation, with drill-down into individual spokes.

### Navigation

4. The plugin MUST add a top-level navigation section for multicluster Lightspeed management.
5. Primary views: Fleet Dashboard, Spoke Management, Proposals (fleet-wide), Alerts (fleet-wide), Configuration.

### Data Freshness

6. The UI MUST show the age of aggregated data (e.g., "last synced 2m ago") so operators can assess data freshness.
7. When a spoke is unreachable, its data MUST be visually distinguished from data from healthy spokes.

## Configuration Surface

| Field/Flag | Type | Default | Description |
|---|---|---|---|
| Configured via the console plugin manifest and hub operator CRs — to be specified as the plugin is designed. ||||

## Planned Changes

| Ticket | Summary |
|---|---|
| — | Initial implementation — all rules above are planned |
