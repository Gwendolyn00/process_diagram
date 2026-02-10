# Crestron Monitoring System - Process Flow

**Role:** Co-architect & Developer | **Tools:** Python, Flask, SQLite

**Problem:** IT support was reactive, discovering device failures only when users reported them.

**Solution:** I co-designed and developed a full-stack system to automate monitoring.

### Process Analysis & Design
Below is the business process flow I designed and implemented for the proactive monitoring solution.


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
```
