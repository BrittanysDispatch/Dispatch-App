# Ambulance Dispatch & Scheduling System

## Purpose
Web-based EMS dispatch system to:
- Log incoming transport calls
- Track patient and insurance info
- Schedule units/trucks hour-by-hour
- Assign calls with drag-and-drop interface
- Provide warnings for overlapping assignments
- Escalate pending calls as pickup time approaches
- Keep schedule clean with compact call cards, expandable to full details

---

## Folder Structure (Planned)
This shows where files and assets will live once on a computer:


---

## Core Features

### Pending Calls Bar (Top)
- Horizontal strip showing all pending calls
- Displays:
  - Pickup location
  - Dropoff location
  - Pickup time
- Draggable to schedule grid
- Color-coded by priority (Routine = Green, Urgent = Yellow, STAT = Red)
- Escalation: Color intensity increases as pickup time approaches
- Compact view shows only key info; clicking expands to full call details

### Daily Schedule Grid
- Rows: Units / Trucks
- Columns: 15-minute time slots (hour-by-hour breakdown)
- Calls appear as draggable blocks spanning their duration
- Current time vertical red line shows live time
- Overlap allowed but triggers **hard warning**; override is logged

### Call Detail Modal
- Opens when a call card is clicked
- Shows:
  - Caller info
  - Pickup & dropoff rooms
  - Patient demographics
  - Insurance info
  - Condition & priority
  - Notes

---

## Database Blueprint

### Calls
- id
- caller_name
- callback_number
- pickup_location
- pickup_department
- pickup_room
- pickup_time
- appointment_duration
- dropoff_location
- dropoff_department
- dropoff_room
- notes
- assigned_unit_id
- status (Pending / Assigned / Completed)

### Patients
- id
- first_name
- last_name
- date_of_birth
- address
- condition
- call_id (links to Calls table)

### Insurance
- id
- patient_id (links to Patients)
- insurance_type (Primary / Secondary / Tertiary)
- company_name
- policy_number
- authorization_number

### Units / Trucks
- id
- unit_number
- truck_number
- status (Available / Busy / Out of Service)

---

## Wireframe / UI Notes

### Pending Calls Bar
- Draggable call cards
- Compact view for schedule overview
- Color-coded by priority
- Escalation as pickup time approaches

### Schedule Grid
- Rows: Units / Trucks
- Columns: 15-minute increments
- Drag-and-drop calls from pending bar
- Current time line indicator
- Overlap triggers warning

### Call Detail Modal
- Full information view
- Opens on click
- Editable if necessary
- Compact view stays on grid until clicked

---

## Future Enhancements
- Mileage / route tracking
- Crew assignments
- STAT / Urgent / Routine indicators
- Reporting / analytics
- Billing export
- Notifications for pending call escalation
- Mobile-friendly interface adjustments

---

## Design Assets
- Mockup of dispatch screen: `dispatch_screen.png` (planned for /design folder)