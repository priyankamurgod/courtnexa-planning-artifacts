# Court Booking & Session Management (v1)
**Product:** Courtnexa  
**Author:** [Your Name]  
**Date:** [Insert Date]  
**Status:** Draft v1  

---

## 1. Overview

This document defines the v1 implementation of the Court Booking & Session Management system for pickleball clubs.

The goal is to enable:
- Efficient court utilization
- Seamless booking experience for players
- Flexible configuration for club administrators

This is a **core revenue-driving feature** and critical for launch.

---

## 2. Problem Statement

Clubs today face challenges with:
- Manual or fragmented scheduling systems
- Double bookings and poor visibility into availability
- Lack of support for open play sessions
- Poor user experience for members

Existing tools are either:
- Too generic (e.g., calendars)
- Too rigid (legacy club software)

---

## 3. Goals & Success Metrics

### Goals
- Enable real-time court booking
- Support both private bookings and open play sessions
- Provide admin configurability without complexity

### Success Metrics
- Court utilization rate (%)
- Booking conversion rate
- Average players per session
- No-show rate

---

## 4. User Roles

### Club Admin
- Configures court availability
- Sets pricing and rules

### Member
- Books courts
- Joins open play sessions

### Guest (Optional - v1 limited support)
- Can book with restrictions (if enabled)

---

## 5. Core Features (v1 Scope)

### 5.1 Court Availability View
- Grid-based time slot view (per court)
- 30-minute intervals (configurable later)
- Real-time availability updates

### 5.2 Court Booking
- Member selects slot and confirms booking
- Option to add players
- Payment (if required)

### 5.3 Open Play Sessions
- Users can join existing sessions
- System enforces max player capacity

### 5.4 Admin Configuration
- Define court schedules
- Set pricing rules
- Enable/disable open play

---

## 6. User Flows

### Flow 1: Member Booking

1. User selects club
2. Views availability grid
3. Selects time slot
4. Chooses:
   - Private booking OR Open play
5. Adds players (optional)
6. Confirms booking
7. Completes payment (if required)

---

### Flow 2: Open Play Join

1. User views available sessions
2. Selects session
3. Joins (if slots available)
4. Confirmation shown

---

### Flow 3: Admin Setup

1. Admin defines court availability
2. Configures:
   - Time slots
   - Pricing
   - Player limits
3. Publishes schedule

---

## 7. Key Product Decisions

| Decision Area | Choice | Rationale |
|------|--------|----------|
| UI Pattern | Slot-based grid | Faster scanning vs calendar |
| Booking Ownership | Single user owns booking | Simplifies payments & cancellations |
| Open Play | Native support | Core for pickleball usage |
| No-show handling | Manual (v1) | Avoid premature complexity |

---

## 8. Edge Cases

- Double booking conflicts
- Payment failure after slot selection
- User drops out after booking
- Fully booked sessions
- Timezone inconsistencies (future global concern)

---

## 9. Dependencies

- Authentication system
- Court availability API
- Payment gateway integration
- Notification system (confirmation)

---

## 10. Technical Considerations

- Optimistic locking to prevent double booking
- Real-time updates (polling or websocket)
- Multi-tenant architecture (club isolation)
- Timezone normalization

---

## 11. Ticket Breakdown

### Epic: Court Booking System (v1)

---

### Ticket 1: Render Court Availability Grid

**Description:**  
Display all courts and time slots for selected date.

**Acceptance Criteria:**
- All courts visible
- Slots shown in 30-min intervals
- Booked slots marked unavailable
- Updates reflect near real-time changes

**Edge Cases:**
- No availability
- Partial court closures

---

### Ticket 2: Create Booking

**Description:**  
Allow member to book a court.

**Acceptance Criteria:**
- User selects slot and confirms
- Prevent double booking
- Booking stored successfully
- Confirmation displayed

**Dependencies:**
- Auth system
- Availability API

---

### Ticket 3: Join Open Play Session

**Description:**  
Allow users to join existing sessions.

**Acceptance Criteria:**
- Session list visible
- Capacity enforced
- Session auto-closes when full

---

### Ticket 4: Admin Court Configuration

**Description:**  
Admin configures availability and rules.

**Acceptance Criteria:**
- Define schedule
- Set pricing
- Toggle open play

---

### Ticket 5: Payment Integration

**Description:**  
Enable payments for bookings.

**Acceptance Criteria:**
- Payment required before confirmation
- Success/failure handled gracefully
- Booking only confirmed after success

---

## 12. Open Questions

- Should guests be allowed to book without account creation?
- Cancellation policy (v1 vs v2)?
- Dynamic pricing (peak vs off-peak)?
- Waitlist support for full sessions?

---

## 13. Future Enhancements (Out of Scope v1)

- Waitlist system
- Automated no-show penalties
- Player matching / skill-based grouping
- Subscription/membership pricing tiers
- Push notifications

---

## 14. Competitive Insights (Summary)

### Tools Reviewed
- Mindbody
- Playtomic
- CourtReserve

### Gaps Identified
- Slow booking flows
- Weak open play handling
- Poor mobile UX

### Opportunity
- 3-click booking experience
- Native open play workflows
- Mobile-first design

---

## 15. Summary

This feature establishes the foundation for:
- Revenue generation
- User retention
- Platform scalability
