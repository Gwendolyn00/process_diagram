# Project: ServiceNow Loan App

## Overview
**Problem:** 

**Solution:** 

## Process Analysis & Design
I mapped the core business process to define the system's logic:

```mermaid
flowchart TD
    Start([Scheduled Check]) --> Task1[Ping Device]
    Task1 --> Decision{Device Online?}
    Decision -- Yes --> Event1[Log Status: Online]
    Event1 --> CheckPrevious{Previous Status?}
    CheckPrevious -- Was Offline --> Task2[Mark Downtime Event Resolved]
    Task2 --> Task3[Send Recovery Alert]
    Task3 --> End1([Process End])
    CheckPrevious -- Was Online --> End1
    Decision -- No --> Event2[Log Status: Offline]
    Event2 --> CheckPrevious2{Previous Status?}
    CheckPrevious2 -- Was Online --> Task4[Create New Downtime Event]
    Task4 --> Task5[Send Outage Alert]
    Task5 --> End2([Process End])
    CheckPrevious2 -- Was Offline --> End2
