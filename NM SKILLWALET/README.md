# Implement Client Script & UI Policy (Incident)

## Naan Mudhalvan – ServiceNow Micro Project

This project demonstrates how **ServiceNow UI Policies and Client Scripts** can be used on the **Incident** table to improve data integrity, automate field behavior, and prevent invalid updates.

### Project Objective

The implementation uses:
- UI Policy
- UI Policy Action
- onChange Client Script
- onSubmit Client Script
- onCellEdit Client Script

The configuration controls the behavior of Incident fields based on the **Impact** and **State** values.

## Features

### 1. High Impact Control – UI Policy
When **Impact = 1 – High**:
- Assignment group is mandatory.
- Urgency becomes read-only.
- The policy is configured with **Reverse if false**.

### 2. Auto Set Urgency – onChange
When Impact changes to High:
- Urgency is automatically set to High.
- An informational message is displayed.

### 3. Prevent Save – onSubmit
When Impact is High and Assigned To is empty:
- The Incident cannot be saved.
- An error is displayed on the Assigned To field.

### 4. Prevent State List Editing – onCellEdit
When a user tries to edit State directly from an Incident list:
- The change is blocked.
- The user is instructed to open the Incident form.

## ServiceNow Configuration

### UI Policy
- Name: `High Impact Control`
- Table: `Incident`
- Active: `true`
- Condition: `Impact is 1 – High`
- UI Policy Action: `Assignment group` → Mandatory
- Reverse if false: `true`

### UI Policy Action
- Field: `Urgency`
- Read-only: `true`
- Visible: unchanged

### Client Script 1
- Name: `Auto set urgency for high impact`
- Table: `Incident`
- Type: `onChange`
- Field: `Impact`
- Active: `true`

### Client Script 2
- Name: `Prevent save if Assigned To missing`
- Table: `Incident`
- Type: `onSubmit`
- Active: `true`

### Client Script 3
- Name: `Prevent state change via list edit`
- Table: `Incident`
- Type: `onCellEdit`
- Field: `State`
- Active: `true`

## Project Structure

```text
naan-mudhalvan-servicenow-incident/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── scripts/
│   ├── onChange_auto_set_urgency.js
│   ├── onSubmit_validate_assigned_to.js
│   └── onCellEdit_block_state_change.js
│
├── docs/
│   ├── configuration.md
│   ├── testing.md
│   ├── project-report.md
│   └── github-upload-guide.md
│
└── evidence/
    └── README.md
```

## Testing Summary

The project should verify:
1. High Impact makes Assignment group mandatory.
2. High Impact makes Urgency read-only.
3. High Impact automatically sets Urgency to High.
4. High Impact + empty Assigned To prevents saving.
5. State cannot be changed through list editing.
6. State can be changed from the Incident form.
7. Changing Impact from High to Medium reverses the applicable UI Policy behavior.

## Important

This repository contains the client-side JavaScript and documentation required to recreate the configuration in a ServiceNow instance. ServiceNow configuration records themselves are created inside the ServiceNow platform.
