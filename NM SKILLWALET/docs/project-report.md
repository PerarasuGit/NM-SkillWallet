# Naan Mudhalvan Project Report

## Project Title

**Implement Client Script & UI Policy (Incident)**

## Domain

ServiceNow – Incident Management

## Problem Statement

Incident records require consistent and accurate data entry for effective triage, routing, and resolution. Manual checks can result in incomplete, inconsistent, or incorrect information. This project addresses the problem by enforcing conditional field behavior and validation at the user-interface level.

## Objective

The objective is to demonstrate how ServiceNow client-side controls can enforce data integrity on Incident records using UI Policies and Client Scripts.

The implementation dynamically:
- Makes fields mandatory.
- Auto-populates values.
- Controls field behavior.
- Prevents invalid record submission.
- Restricts direct list editing of State.

## Technologies / Skills

- ServiceNow
- Incident Management
- UI Policy
- UI Policy Actions
- Client Scripts
- JavaScript
- Form Validation

## Implementation

### UI Policy

A UI Policy named **High Impact Control** is created on the Incident table. It is triggered when Impact is set to High.

The policy makes Assignment group mandatory and uses Reverse if false.

### UI Policy Action

The Urgency field is configured as read-only when the High Impact condition is active.

### onChange Client Script

The script monitors the Impact field. When Impact becomes High, Urgency is automatically set to High and an informational message is displayed.

### onSubmit Client Script

The script checks whether Assigned To is empty when Impact is High. If it is empty, saving is prevented and an error message is displayed.

### onCellEdit Client Script

The script blocks direct State changes through list editing and asks the user to open the Incident form.

## Testing

The configuration is tested for:
- Mandatory field enforcement.
- Read-only field behavior.
- Automatic urgency assignment.
- Save-time validation.
- List-edit blocking.
- Form-based State update.
- Reverse condition behavior.

## Expected Outcome

The Incident form should enforce the configured business rules and prevent incomplete or unauthorized updates.

## Conclusion

This micro project demonstrates how ServiceNow UI Policies and Client Scripts can work together to enforce dynamic field behavior, automate updates, and prevent incorrect data submission. The solution improves consistency and data integrity while remaining lightweight and suitable for a short-duration ServiceNow project.

## Student Evidence

Attach screenshots from the ServiceNow instance in the `evidence/` folder and update the testing status with the actual results.
