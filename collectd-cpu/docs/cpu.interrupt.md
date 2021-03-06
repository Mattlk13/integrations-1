
---
title: cpu.interrupt
brief: CPU time spent while servicing hardware interrupts
metric_type: cumulative
custom: true
---
### cpu.interrupt

CPU time spent while servicing hardware interrupts. A hardware interrupt happens at the physical layer. When this occurs, the CPU will stop whatever else it is doing and service the interrupt. This metric measures how many jiffies were spent handling these interrupts. In order to get a percentage this value must be compared against the sum of all CPU states. A sustained high value for this metric may be caused by faulty hardware such as a broken peripheral.

