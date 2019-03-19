##Context Diagram

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

##Interfaces