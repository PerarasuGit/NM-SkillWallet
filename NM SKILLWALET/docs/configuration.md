# ServiceNow Configuration Guide

## 1. UI Policy – High Impact Control

Navigate to:

`System UI → UI Policies → New`

Configure:

| Property | Value |
|---|---|
| Name | High Impact Control |
| Table | Incident |
| Active | true |
| Condition Field | Impact |
| Operator | is |
| Value | 1 – High |
| Reverse if false | true |

### UI Policy Action – Assignment group

Create an action under the UI Policy:

| Property | Value |
|---|---|
| Field name | Assignment group |
| Mandatory | true |

## 2. UI Policy Action – Urgency

Under `High Impact Control`, create another UI Policy Action:

| Property | Value |
|---|---|
| Field name | Urgency |
| Read-only | true |
| Visible | Leave unchanged |

## 3. onChange Client Script

Navigate to:

`System UI → Client Scripts → New`

| Property | Value |
|---|---|
| Name | Auto set urgency for high impact |
| Table | Incident |
| Type | onChange |
| Field name | Impact |
| Active | true |

Copy the code from:

`scripts/onChange_auto_set_urgency.js`

## 4. onSubmit Client Script

| Property | Value |
|---|---|
| Name | Prevent save if Assigned To missing |
| Table | Incident |
| Type | onSubmit |
| Active | true |

Copy the code from:

`scripts/onSubmit_validate_assigned_to.js`

## 5. onCellEdit Client Script

| Property | Value |
|---|---|
| Name | Prevent state change via list edit |
| Table | Incident |
| Type | onCellEdit |
| Field name | State |
| Active | true |

Copy the code from:

`scripts/onCellEdit_block_state_change.js`
