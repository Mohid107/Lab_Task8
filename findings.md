# MediTrack SRS — Consolidated Validation Findings

- **Consultants:** Mohid bin Zahid (Student A) & Abdul Rehman (Student B)
- **Client:** CityCare Clinic (12 doctors, 6 receptionists, ~400 patients/week)
- **Document Audited:** `srs/meditrack-srs.md` (R-01 to R-14)
- **Checklist Used:** `checklist/v0.1.md` (18 items)

## 1. Run Comparison Summary
Both reviewers independently answered **No** to all 18 checklist items, confirming severe ambiguity, contradictions, and missing operational rules across the SRS. Three items were flagged with `?` during individual reviews and resolved together:
- **CL-004 (`?` by Student B):** Agreed that R-03 ("prevent double bookings") is untestable as written unless concurrency/locking rules (CL-006) are added.
- **CL-014 (`?` by Student A):** Agreed that R-10 only mentions "walk-in patients" and completely omits telephone bookings, which the clinic currently relies on.
- **CL-018 (`?` by Student A):** Agreed that R-12 ("available during normal working hours") both lacks exact hours and contradicts R-01's core value of 24/7 online booking.

---

## 2. Agreed Problems in the SRS

### A. Contradictions
1. **Conflicting Appointment Durations (R-04 vs. R-05 | CL-005):** R-04 rigidly mandates that every appointment shall last 15 minutes, whereas R-05 allows doctors to configure appointment lengths between 10 and 30 minutes.
2. **Online Availability vs. Working Hours (R-01 vs. R-12 | CL-018):** R-01 allows patients to book appointments online, but R-12 restricts system availability to undefined "normal working hours," preventing patients from booking in the evening or on weekends.

### B. Ambiguous & Untestable Requirements
3. **Unquantified Performance & Peak Load (R-02, R-12 | CL-002, CL-003, CL-004, CL-011):** R-02 requires the system to "respond quickly" without a numeric response-time target (e.g., `< 2 seconds`) or concurrent user threshold for Monday morning rush hours.
4. **Vague Security & Privacy Controls (R-09 | CL-002, CL-016, CL-017):** R-09 states patient records shall be "stored securely" without specifying encryption standards (at rest and in transit), audit logging, or role-based access control (RBAC) across the 5 user roles.
5. **Unmeasurable Accessibility Claim (R-08 | CL-002, CL-004):** R-08 claims the system will be "user-friendly for all age groups" with no concrete accessibility criteria (e.g., WCAG AA, minimum font sizes, screen-reader support, or assisted phone booking for elderly patients).
6. **External Undefined Policy Reference (R-13 | CL-002, CL-015):** R-13 delegates overdue payment handling to an unattached "clinic policy" rather than defining exact grace periods, fees, or booking restrictions inside the contract.
7. **Compound Requirement Structure (R-07 | CL-001):** R-07 bundles three distinct behaviors (patient cancellation, schedule update, and receptionist notification) into a single statement, complicating traceability and testing.

### C. Missing Clinic-Critical Requirements (Omissions)
8. **No Concurrency Control for Double Bookings (R-03 | CL-006):** R-03 states the objective of preventing double bookings but omits atomic slot-locking rules when a patient online and a receptionist at the desk select the same slot simultaneously.
9. **Incomplete Reminder Specification (R-06 | CL-007, CL-008):** R-06 omits both the notification lead time (e.g., 24 hours and 2 hours prior) and the delivery channel (e.g., SMS or automated voice calls for elderly patients without smartphones).
10. **No Cancellation Cutoff Window (R-07 | CL-009):** Allowing cancellations "at any time" enables patients to cancel minutes before their slot, leaving doctors idle with no time to backfill.
11. **No Emergency Walk-In Triage or Overflow Mechanism (R-10 | CL-010):** R-10 allows booking walk-ins but fails to specify how urgent/emergency patients are accommodated when schedules are full.
12. **Missing Core User Workflows (R-01, R-10, R-14 | CL-012, CL-013, CL-014):**
    - **Patients** have no way to reschedule an appointment without cancelling and losing their slot (`CL-012`).
    - **Doctors** can view schedules (`R-14`) but cannot block off breaks, meetings, or leave (`CL-013`).
    - **Receptionists** have no documented workflow for phone bookings or conflict overrides (`CL-014`).
    - **Clinic Administrators & Data Protection Officers** have zero dedicated functional requirements for user management, reporting, audit trails, or data retention (`CL-015`, `CL-016`).

## 3. Recommendation to CityCare Clinic
**Do not sign the contract in its current form.** Require the vendor to revise `meditrack-srs.md` to resolve the R-04/R-05 contradiction, replace all subjective terms with measurable acceptance criteria, and add explicit requirements for concurrency locking, emergency walk-ins, phone bookings, and role-based medical data access before signing.
