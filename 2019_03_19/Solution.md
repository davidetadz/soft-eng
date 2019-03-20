
```plantuml
@startuml
left to right direction
skinparam packagestyle rectangle

actor Internet as i
actor "Credit Card System" as c
actor User as u

rectangle system {
  (multiplex cinema) as mc
  i -- mc
  mc -- c
  u -- mc
}
@enduml
```

## Interfaces

```plantuml
---
```

## Use Cases Diagram

```plantuml
@startuml
left to right direction

actor Customer as c
actor Clerk as cl
actor "Credit Card System" as ccs

(Sell Ticket) as st
(Admint to room) as a
(Choose seat) as cs
(Handle Payment) as hp
(Print ticket) as pt
(Refund a ticket) as r
(Monitor) as m
(Define schedule) as d
(Print schedule) as p

c -- a
c -- st

st .> cs : include
st .> pt : include
st .> hp : include

cl -- m
cl -- st
cl -- r
cl -- d
cl -- p

@enduml

```

## Scenarios 

### Successful sale for a ticket for a movie

Precondition: at least one seat is available for the selected show

Post condition: selected seat now occupied

| Scenario ID: SC1 | Correspons to US: Sell Ticket |
| ---------------- | :----------------------------: |
| Step# | Description |
| 1 | Customer selects show |
| 2 | Customer selects seats |
| 3 | Customer pays |
| 4 | System sets the seat as occupied, decreases the total number of seats available |

### Successful admission to a room

Precondition: customer as a valid ticket for show and room

Post condition: the seat now occupied

| Scenario ID: SC2 | Correspons to US: Admit to Room |
| ---------------- | :----------------------------: |
| Step# | Description |
| 1 | Customer shows ticket to the barcode reader |
| 2 | System checks if the ticket is valid for show and room |
| 3 | Room gate opens, customer enters |
| 4 | System sets ticket as used, and the seat as occupied |