# Individual Checklist Run — Student B

- **Reviewer:** Abdul Rehman
- **Checklist Version:** v0.1
- **Start Time:** 10:05 AM
- **End Time:** 10:33 AM

| ID | Item | Answer | Evidence | Where question came from |
| :--- | :--- | :--- | :--- | :--- |
| **CL-001** | Does each requirement contain only one "shall" or "may" statement? | No | R-07 combines "may cancel" and "shall update... and notify" into one requirement. | Rule: Clear |
| **CL-002** | Is every requirement free of undefined vague words (e.g. "quickly", "user-friendly", "securely", "normal", "policy")? | No | R-02, R-08, R-09, R-12, and R-13 all contain undefined subjective terms. | Rule: Clear |
| **CL-003** | Does every speed or time requirement state a number and a unit? | No | R-02 ("quickly") and R-06 ("before appointments") lack specific time units. | Rule: Testable |
| **CL-004** | Could a pass/fail test be written for every requirement? | No ? | R-02, R-08, R-09, R-12, R-13 cannot be tested (unsure if R-03 can be tested without concurrency rules). | Rule: Testable |
| **CL-005** | Are all appointment duration rules free of direct contradictions? | No | R-04 mandates 15-minute appointments while R-05 lets doctors set 10–30 minutes. | Rule: Free of contradictions |
| **CL-006** | Does the document define the exact system behavior when two users select the same time slot simultaneously? | No | R-03 states the goal ("prevent double bookings") but omits slot-locking rules. | Risk: Double booking concurrency |
| **CL-007** | Does the document specify the exact lead time (in hours or days) before an appointment when reminders are sent? | No | R-06 only says "before appointments" with no lead time specified. | Risk: Missed appointments / no-shows |
| **CL-008** | Does the document state the communication channel (e.g., SMS, phone call, email) used for appointment reminders? | No | R-06 does not state whether reminders are sent via SMS, phone call, or email. | Risk: Elderly patients missing digital alerts |
| **CL-009** | Does the document specify a minimum cutoff window before an appointment after which online cancellation is restricted? | No | R-07 permits cancellation "at any time," even 1 minute before the appointment. | Risk: Last-minute cancellations leaving empty slots |
| **CL-010** | Does the document define how emergency walk-in patients are prioritized when all slots are already booked? | No | R-10 mentions walk-in booking but omits emergency triage or priority slot rules. | Risk: Emergency walk-ins delayed |
| **CL-011** | Does the document specify the peak concurrent user load expected during busy periods such as Monday mornings? | No | No requirement in R-01–R-14 states concurrent users or throughput targets. | Risk: Monday morning system slowdown/crash |
| **CL-012** | Does the document state whether patients can reschedule an existing appointment without cancelling first? | No | R-01 through R-14 contain no rescheduling requirement for patients. | User: Patient |
| **CL-013** | Does the document allow doctors to block off unavailable time slots (e.g., breaks, leave, surgeries) in their schedule? | No | R-14 only covers viewing the daily schedule; schedule blocking is omitted. | User: Doctor |
| **CL-014** | Does the document specify how receptionists resolve or override scheduling conflicts for phone bookings? | No | R-10 only mentions walk-in patients and omits phone booking workflows entirely. | User: Receptionist |
| **CL-015** | Does the document define the exact numerical rules for handling overdue payments? | No | R-13 references an external "clinic policy" that is not included in the SRS. | User: Clinic administrator |
| **CL-016** | Does the document specify which user roles are permitted to view patient medical records? | No | R-09 omits access permissions for Doctors, Receptionists, Admins, and DPO. | User: Data protection officer |
| **CL-017** | Does the document specify the encryption standard required for storing patient records? | No | R-09 gives no encryption algorithm or key-management requirement. | User: Data protection officer |
| **CL-018** | Does the document define the exact days and clock hours that constitute normal working hours? | No | R-12 leaves "normal working hours" undefined (and implies patients cannot book at night). | Rule: Complete |
