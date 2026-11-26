# Technical Process Report: Home Delivery of Medicines and Personalised Treatments

## 1. Process Overview

EcoRoute delivers medicines and personalised treatments to patients' homes in the city. The process validates each order [Source: Step 2], assigns a vehicle by urgency and car availability [Source: Step 4–5], calculates a route with real-time traffic data [Source: Step 6–7] and delivers the medicine [Source: Step 8]. It ends in [Medicine Delivered] or [Order Cancelled] [Source: Step 9].

## 2. Step-by-Step Process Table

| Step | Type | Name | Description and Paths | Source |
|---|---|---|---|---|
| Start | Start | [Medicine Order Received] | The process starts. Next: [Order Details]. | [Source: START] |
| 1 | Input | [Order Details] | Patient address, medicine, deadline. Next: [Validate Order]. | [Source: Step 1] |
| 2 | Action | [Validate Order] | Checks the received Order Details. Next: [Order complete?]. | [Source: Step 2] |
| 3 | Decision | [Order complete?] | Yes: [Same-day urgent?]. No: [Request Missing Information]. | [Source: Step 3] |
| 3a | Action | [Request Missing Information] | Next: [Validate Order]. | [Source: Step 3] |
| 4 | Decision | [Same-day urgent?] | Yes: [Assign Electric Scooter]. No: [Car available?]. | [Source: Step 4] |
| 4a | Action | [Assign Electric Scooter] | Next: [Calculate Optimal Route]. | [Source: Step 4] |
| 5 | Decision | [Car available?] | Yes: [Assign Electric Car]. No: [Wait for Available Car]. | [Source: Step 5] |
| 5a | Action | [Assign Electric Car] | Next: [Calculate Optimal Route]. | [Source: Step 5] |
| 5b | Action | [Wait for Available Car] | Next: [Waiting over 15 min?]. | [Source: Step 5] |
| 5c | Decision | [Waiting over 15 min?] | Yes: [Reschedule Delivery]. No: [Car available?]. | [Source: Step 5] |
| 5d | Action | [Reschedule Delivery] | Next: [Calculate Optimal Route]. | [Source: Step 5] |
| 6 | Input | [Real-time Traffic Data] | Feeds [Calculate Optimal Route]. | [Source: Step 6] |
| 7 | Action | [Calculate Optimal Route] | Uses [Real-time Traffic Data]. Next: [Deliver Medicine]. | [Source: Step 7] |
| 8 | Action | [Deliver Medicine] | Next: [Patient at home?]. | [Source: Step 8] |
| 9 | Decision | [Patient at home?] | Yes: [Confirm Delivery]. No: [Max attempts reached?]. | [Source: Step 9] |
| 9a | Action | [Confirm Delivery] | Produces [Delivery Confirmation & Emissions Report]. Next: [Medicine Delivered]. | [Source: Step 9] |
| 9b | Decision | [Max attempts reached?] | Yes: [Return Medicine to Pharmacy]. No: [Schedule New Delivery Attempt]. Maximum number of attempts: INSUFFICIENT_DATA. | [Source: Step 9] |
| 9c | Action | [Schedule New Delivery Attempt] | Next: [Calculate Optimal Route]. | [Source: Step 9] |
| 9d | Action | [Return Medicine to Pharmacy] | Next: [Order Cancelled]. | [Source: Step 9] |
| End | End | [Medicine Delivered] | Successful end. | [Source: Step 9] |
| End | End | [Order Cancelled] | Unsuccessful end. | [Source: Step 9] |
