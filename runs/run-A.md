# Individual Checklist Run — Student A

- **Reviewer:** Mohid bin Zahid
- **Checklist Version:** v0.1
- **Start Time:** 10:05 AM
- **End Time:** 10:31 AM

| ID | Item | Answer | Evidence | Where question came from |
| :--- | :--- | :--- | :--- | :--- |
| **CL-001** | Does each requirement contain only one "shall" or "may" statement? | No | R-07 has three actions (cancel, update schedule, notify). | Rule: Clear |
| **CL-002** | Is every requirement free of undefined vague words (e.g. "quickly", "user-friendly", "securely", "normal", "policy")? | No | R-02 ("quickly"), R-08 ("user-friendly"), R-09 ("securely"), R-12 ("normal"), R-13 ("policy"). | Rule: Clear |
| **CL-003** | Does every speed or time requirement state a number and a unit? | No | R-02 has no response time number/unit; R-12 has no working hours stated. | Rule: Testable |
| **CL-004** | Could a pass/fail test be written for every requirement? | No | R-02, R-08, R-09, R-12, and R-13 lack measurable acceptance criteria. | Rule: Testable |
| **CL-005** | Are all appointment duration rules free of direct contradictions? | No | R-04 fixes every appointment at 15 minutes, contradicting R-05 (10 to 30 minutes). | Rule: Free of contradictions |
| **CL-006** | Does the document define the exact system behavior when two users select the same time slot simultaneously? | No | R-03 states "prevent double bookings" but specifies no locking or conflict mechanism. | Risk: Double booking concurrency |
| **CL-007** | Does the document specify the exact lead time (in hours or days) before an appointment when reminders are sent? | No | R-06 states "before appointments" without specifying hours or days. | Risk: Missed appointments / no-shows |
| **CL-008** | Does the document state the communication channel (e.g., SMS, phone call, email) used for appointment reminders? | No | R-06 mentions reminders but omits whether SMS, voice call, or email is used. | Risk: Elderly patients missing digital alerts |
| **CL-009** | Does the document specify a minimum cutoff window before an appointment after which online cancellation is restricted? | No | R-07 explicitly allows cancellation "at any time" with no cutoff restriction. | Risk: Last-minute cancellations leaving empty slots |
| **CL-010** | Does the document define how emergency walk-in patients are prioritized when all slots are already booked? | No | R-10 allows booking walk-ins but defines no priority or slot-override rule for emergencies. | Risk: Emergency walk-ins delayed |
| **CL-011** | Does the document specify the peak concurrent user load expected during busy periods such as Monday mornings? | No | R-02 and R-12 state no concurrent user capacity for peak Monday morning traffic. | Risk: Monday morning system slowdown/crash |
| **CL-012** | Does the document state whether patients can reschedule an existing appointment without cancelling first? | No | R-01 (book) and R-07 (cancel) exist, but no requirement covers rescheduling. | User: Patient |
| **CL-013** | Does the document allow doctors to block off unavailable time slots (e.g., breaks, leave, surgeries) in their schedule? | No | R-14 only allows doctors to view their schedule, not block off unavailable times. | User: Doctor |
| **CL-014** | Does the document specify how receptionists resolve or override scheduling conflicts for phone bookings? | No ? | R-10 covers walk-ins, but phone booking conflict handling is missing (unsure if R-10 implies phone bookings). | User: Receptionist |
| **CL-015** | Does the document define the exact numerical rules for handling overdue payments? | No | R-13 defers to "clinic policy" without defining fees, grace periods, or booking blocks. | User: Clinic administrator |
| **CL-016** | Does the document specify which user roles are permitted to view patient medical records? | No | R-09 mentions storing patient records but defines no role-based access control. | User: Data protection officer |
| **CL-017** | Does the document specify the encryption standard required for storing patient records? | No | R-09 says "stored securely" without naming an encryption standard (e.g., AES-256). | User: Data protection officer |
| **CL-018** | Does the document define the exact days and clock hours that constitute normal working hours? | No ? | R-12 says "normal working hours" without clock times (unsure if 24/7 online booking in R-01 conflicts with R-12). | Rule: Complete |
