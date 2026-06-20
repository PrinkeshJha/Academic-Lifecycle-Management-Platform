# Academic Lifecycle Management Platform (ALMP)

> A ServiceNow application that brings order to the chaos of university admissions — automating everything from student registration to departmental governance, so universities can focus on education instead of paperwork.

---

## What is ALMP?

Managing student admissions across a university involves a surprising amount of moving parts — registration forms, approval chains, departmental coordination, compliance records, and constant email back-and-forth. When these things are handled manually, things fall through the cracks.

ALMP is a custom ServiceNow application built to solve exactly that. It automates the entire student admission and academic governance lifecycle: from the moment a student registers, through approvals and notifications, all the way to departmental visibility and analytics. Everything lives in one place, and nothing gets lost.

Built using ServiceNow Studio, the platform puts into practice the core concepts from both the **ServiceNow Certified System Administrator (CSA)** and **Certified Application Developer (CAD)** certifications.

---

## The Problem It Solves

Here's what universities typically deal with without a system like this:

- Students accidentally registered twice, causing confusion downstream
- Approval requests sitting in someone's inbox for days with no follow-up
- No clear record of who approved what, or when
- Departments working in silos, unaware of admission decisions
- Reports that take hours to manually compile

ALMP addresses each of these through workflow automation, event-driven notifications, role-based governance, and real-time dashboards.

---

## Key Features

### Student Registration
When a student registers, the platform immediately gets to work:
- Generates a unique **Enrollment Number** automatically
- Creates a **University Email ID** from the student's details
- Validates the personal email address and mobile number
- Prevents duplicate registrations before they become a problem
- Auto-populates the correct department based on the selected branch

### Admission Approval Workflow
Approvals are managed through **Flow Designer**, keeping the process structured and trackable:
- Designated staff can **Approve** or **Reject** applications directly from the record
- Rejection requires a reason, ensuring accountability
- Every approval action is timestamped and logged
- Status is visible to all relevant stakeholders in real time

### Academic Governance
Once a student is approved, their record is automatically shared with:
- **IQAC** — for institutional quality monitoring
- **MIS** — for reporting and data governance
- **Dean's Office** — for academic oversight

No manual data re-entry. No emails asking "can you send me that student's details?"

### Notifications & Reminders
The platform uses an event-driven architecture so nothing falls through the cracks:
- Approval confirmation emails go out automatically
- Pending admission reminders are sent on a schedule
- All events are tracked through ServiceNow's Event Registry and Queue

### Audit Trail
Every approval action leaves a clean record:
- Who approved or rejected
- When the action was taken
- What reason was given for rejections

This makes compliance reviews straightforward and gives administrators confidence in the data.

### Analytics Dashboard
Interactive dashboards give leadership a live view of:
- Total registrations and their current status
- Branch-wise student distribution
- Approval throughput and bottlenecks
- Governance metrics across IQAC, MIS, and Dean modules

---

## How It All Fits Together

```
Student Registration
        │
        ▼
  Student Master
        │
        ▼
  Business Rules
  ├── Enrollment Number Generation
  ├── University Email Generation
  ├── Duplicate Prevention
  └── Approval History Creation
        │
        ▼
Flow Designer Workflow
        │
   ┌────┴────┐
   ▼         ▼
Approve    Reject
   └────┬────┘
        │
        ▼
Event Registry & Queue
        │
        ▼
   Notifications
   ├── Approval Email
   └── Reminder Email
        │
        ▼
 Approval History
        │
   ┌────┼────┐
   ▼    ▼    ▼
 IQAC  MIS  Dean
   └────┼────┘
        │
        ▼
Analytics Dashboard
```

---

## Roles & Permissions

Each user in the platform has a clearly defined role, so people only see and do what's relevant to them.

| Role | What They Can Do |
|---|---|
| Admin | Full application access |
| Student Admin | Register and manage student records |
| IQAC Head | Monitor academic quality metrics |
| MIS Head | Access reporting and governance data |
| Dean | Review and approve admissions |
| Faculty | View student records |
| Student | Limited read access to their own record |

---

## Tables

**Core**
- `Student Master` — the central student record
- `Approval History` — a complete log of every approval action

**Governance**
- `IQAC Students`
- `MIS Students`
- `Dean Students`

---

## Automation at a Glance

**Business Rules (server-side)**
- Generate enrollment numbers on record creation
- Derive university email from student data
- Block duplicate registrations
- Write approval history entries automatically

**Client Scripts (browser-side)**
- Validate mobile number format in real time
- Validate personal email format in real time

**UI Policies**
- Show/hide the rejection reason field based on approval status

**UI Actions**
- "Approve Student" button — triggers approval flow
- "Reject Student" button — triggers rejection flow with reason capture

**Script Includes & GlideAjax**
- Dynamic department lookup based on selected branch (no page reload required)

**Scheduled Jobs**
- Automated reminder for admissions that have been pending too long

---

## ServiceNow Concepts Used

This project covers the technical spectrum of what a certified ServiceNow developer would be expected to know:

**From CSA:** custom tables, modules, roles, ACLs, notifications, reports, dashboards, scheduled jobs

**From CAD:** business rules, client scripts, UI policies, UI actions, script includes, GlideAjax, Flow Designer, event registry, event queue, scheduled script execution

---

## Screenshots

> *(Replace the placeholders below with actual screenshots from your instance)*

**1. Student Registration & Validation**
The registration form with auto-generated enrollment number, university email, and real-time validation feedback.

**2. Dynamic Department Mapping**
Branch selection triggering a GlideAjax call that auto-populates the department field instantly.

**3. Flow Designer Workflow**
The visual approval workflow showing branch logic for approve and reject paths.

**4. Approval Governance & Audit Trail**
The UI action buttons on the student record, and the resulting approval history entries.

**5. Event & Notification Automation**
The event registry, event log, and a sample approval notification email.

**6. Analytics Dashboard**
The dashboard showing registration stats, branch distribution, and approval metrics.

---

## What This Project Demonstrates

Beyond just being a working application, ALMP is a demonstration of how ServiceNow can be used to replace fragmented, manual processes with something reliable, auditable, and scalable. It touches nearly every major platform capability — from form scripting to workflow orchestration to governance and reporting — in the context of a real-world use case.

---

## Developer

**Prinkesh Jha**
B.Tech — Computer Science & Engineering

Certified ServiceNow System Administrator (CSA)
Certified ServiceNow Application Developer (CAD)
