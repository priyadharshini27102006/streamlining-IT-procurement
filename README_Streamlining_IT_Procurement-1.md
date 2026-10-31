# Streamlining IT Procurement: Automating Standard Laptop Orders with Flow Designer

## Overview
This project proposes a ServiceNow workflow for standard employee laptop requests. The flow validates request details, routes approvals when required, creates or assigns fulfillment work, and sends status notifications.

> **Project status:** Documentation and implementation guide. Add screenshots and test evidence from your own ServiceNow instance before presenting this as a completed implementation.

## Problem Statement
Manual laptop procurement requests can be delayed by incomplete information, approval follow-ups, and unclear task ownership. A standardized workflow can improve consistency and visibility.

## Objectives
- Standardize laptop request submission.
- Validate required request information.
- Route approvals according to organizational policy.
- Assign fulfillment work to the appropriate IT/procurement team.
- Notify requesters about important status changes.
- Improve traceability from submission to completion.

## Platform and Components
- **Platform:** ServiceNow
- **Primary tool:** Flow Designer
- **Potential components:** Service Catalog, approval actions, task/fulfillment records, notifications

Exact triggers, tables, actions, and permissions depend on the ServiceNow instance and installed applications.

## Proposed Workflow
1. Employee submits a **Standard Laptop Request** catalog item.
2. Flow validates the required fields and selected laptop option.
3. If approval is required, the flow requests approval from the configured approver.
4. If rejected, the request is updated and the requester is notified.
5. If approved—or if approval is not required—the flow creates or assigns the fulfillment task.
6. The IT/procurement team processes the request and updates its status.
7. The requester is notified when the request is completed.

## Suggested Request Fields
| Field | Purpose | Requirement |
|---|---|---|
| Requested for | Employee receiving the laptop | Required |
| Department | Employee department | Required |
| Laptop model/type | Approved standard laptop option | Required |
| Business justification | Reason for the request | Required |
| Required-by date | Requested fulfillment date | Policy-dependent |
| Additional notes | Extra context | Optional |

## Implementation Outline
1. Create a catalog item named `Standard Laptop Request`.
2. Open Flow Designer and create `Standard Laptop Order Automation`.
3. Configure the appropriate Service Catalog trigger supported by the instance.
4. Add validation conditions for required fields and approved laptop choices.
5. Add approval logic if required by policy.
6. Configure the approved path to create or assign a fulfillment task.
7. Configure rejected and invalid-request paths.
8. Add notifications for submission, approval/rejection, and fulfillment completion.
9. Save, activate, and test the flow.
10. Review flow execution details and resulting records.

## Test Plan
| Scenario | Expected result |
|---|---|
| Valid request and approval granted | Fulfillment task is created/assigned and the requester is updated |
| Request rejected | Request is updated with the rejection outcome and the requester is notified |
| Required information missing | Request is routed for correction or prevented from normal fulfillment |
| Unsupported laptop option | Request is rejected or routed for correction |
| Notification check | Correct recipients receive the appropriate message |
| Repeated submission | Behavior follows the chosen duplicate-request policy |

Record actual pass/fail results and add screenshots from your ServiceNow instance.

## Expected Benefits
- Less manual follow-up for routine requests
- More consistent validation and approvals
- Better visibility into request status and task ownership
- Clearer communication between employees and IT/procurement
- Measurable improvements in request-processing and approval turnaround times

## Limitations
Flow Designer coordinates workflow actions; it does not by itself guarantee that a laptop is purchased, available in inventory, or delivered. Those capabilities require the appropriate ServiceNow applications, configuration, permissions, or external integrations.

## Repository Structure
```text
streamlining-it-procurement/
├── README.md
├── docs/
│   └── project-documentation.docx
├── screenshots/
│   ├── catalog-item.png
│   ├── flow-designer.png
│   └── test-results.png
└── LICENSE
```

Add screenshots and a license only when appropriate. Replace placeholder filenames with the files you actually include.

## Documentation
See [`docs/project-documentation.docx`](docs/project-documentation.docx) for the full project report, workflow diagram, implementation procedure, testing plan, and governance considerations.

## Author
Add your name here.
