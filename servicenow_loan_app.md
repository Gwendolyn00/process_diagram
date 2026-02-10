# Project: ServiceNow Loan App

## Overview
**Problem:** Manual email-based loaner vehicle request process that would get lost in tracking vehicles.

**Solution:** Developed a custom ServiceNow application to automate the vehicle requests, approvals, and inventory tracking.

## Process Analysis & Design
I mapped two core business process to define the system's logic:

**Loaner Request Flow**

```mermaid
flowchart TD
    Start([User submits Loaner Request Form]) --> Task1[Tracker Record is created]
    Task1 --> Decision{Approved?}
    Decision -- Yes --> Event1a[Delivery Task Created]
    Event1a --> Event2a[Item Record Updated to Closed]
    Event2a --> Event3a[Vehicle Tracker Record Updated to Out on Field]
    Event3a --> End1([Process End])
    Decision -- No --> Event1b[Item Record Updated to Closed Imcomplete]
    Event1b --> Event2b[Vehicle Tracker Record UPdated to Returned to Warehouse]
    Event2b --> End2([Process End])
