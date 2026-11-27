## 3. Decision Rules

- R1: Same-day urgent orders get an electric scooter [Source: Step 4].
- R2: Other orders get an electric car when one is available [Source: Step 5].
- R3: A wait for a car longer than 15 minutes triggers [Reschedule Delivery] [Source: Step 5].

## 4. Exception and Error Handling

- Incomplete order: [Request Missing Information], then [Validate Order]. Retry limit: INSUFFICIENT_DATA [Source: Step 3].
- No car: [Wait for Available Car], up to 15 minutes [Source: Step 5].
- Patient absent: [Schedule New Delivery Attempt]; at the attempt limit, [Return Medicine to Pharmacy] → [Order Cancelled] [Source: Step 9].
