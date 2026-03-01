===================================
Hyundai Kona Electric Gen 2 / Kia Niro EV Gen 2
===================================

**Hyundai Kona Electric Gen 2 / Kia Niro EV Gen 2**

- Vehicle Type: **KN2**
- Log tag: ``v-kianiroev2``
- Poll log tag: ``v-kianiroev2-poll``
- Namespace: ``xkn2``
- Maintainers: `Michael Geddes <frog@bunyip.wheelycreek.net>`_
- Credits: Based on Hyundai Ioniq 5 implementation by Michael Geddes, EVNotify

The Hyundai Kona Electric Gen 2 and Kia Niro EV Gen 2 share the E-GMP platform with the Ioniq 5, featuring the same CAN bus architecture and OBD-II polling capabilities.


----------------
Support Overview
----------------

=========================== ==============
Function                    Support Status
=========================== ==============
Hardware                    OVMS v3 (or later)
Vehicle Cable               OBD-II to DB9 Data Cable for OVMS (1441200 right, or 1139300 left)
GSM Antenna                 1000500 Open Vehicles OVMS GSM Antenna (or any compatible antenna)
GPS Antenna                 1020200 Universal GPS Antenna (SMA Connector) (or any compatible antenna)
SOC Display                 Yes
Range Display               Yes
GPS Location                Yes (from modem module GPS)
Speed Display               Yes
Temperature Display         Partial
BMS v+t Display             Yes
SOH Display                 Yes
TPMS Display                Yes
Charge Status Display       Yes
Charge Interruption Alerts  Yes
Charge Control              No
Cabin Pre-heat/cool Control No
Lock/Unlock Vehicle         No
Valet Mode Control          No
Others
=========================== ==============


--------------
Custom Metrics
--------------

======================================== ======================== ============================================
Metric name                              Example value            Description
======================================== ======================== ============================================
xkn2.m.version                           0.0.1 10/09/2022 10:23   Version of Module
xkn2.b.bms.soc                           78.5%                    Internal BMS SOC
xkn2.v.b.c.voltage.max                   10.0V                    Battery Cell Volt Max
xkn2.v.b.c.voltage.min                   10.0V                    Battery Cell Volt Min
xkn2.v.b.c.voltage.max.no                123450                   Battery Cell Volt Max No
xkn2.v.b.c.voltage.min.no                123450                   Battery Cell Volt Min No
xkn2.v.b.c.det.min                       12.1%                    Battery Cell Det Min
xkn2.v.b.c.det.max.no                    123450                   Battery Cell Det Max No
xkn2.v.b.c.det.min.no                    123450                   Battery Cell Det Min No
xkn2.c.power                             12345kW                  Power
xkn2.c.speed                             109Kph                   Speed
xkn2.b.min.temp                          36°C                     Battery Min Temperature
xkn2.b.max.temp                          36°C                     Battery Max Temperature
xkn2.b.inlet.temp                        36°C                     Battery Inlet Temperature
xkn2.b.heat1.temp                        36°C                     Battery Heat 1 Temperature
xkn2.b.bms.soc                           12.1%                    Battery Bms Soc
xkn2.b.aux.soc                           78%                      Battery Aux Soc
xkn2.b.bms.relay                         false                    Battery Bms Relay             
xkn2.b.bms.ignition                      false                    Battery Bms Ignition             
xkn2.b.bms.power.avail                   7680W                    BMS Available power for charging
xkn2.ldc.out.volt                        10.0V                    Low Voltage DC Conv Out Voltage
xkn2.ldc.in.volt                         10.0V                    Low Voltage DC Conv In Voltage
xkn2.ldc.out.amps                        8.2A                     Low Voltage DC Conv Out Current
xkn2.ldc.temp                            8.2°C                    Low Voltage DC Conv Temperature
xkn2.obc.pilot.duty                      12.1%                    OBC Pilot Duty
xkn2.obc.timer.enabled                   false                    OBC Timer Enabled             
xkn2.e.lowbeam                           false                    Env Lowbeam             
xkn2.e.highbeam                          false                    Env Highbeam             
xkn2.e.indicator.l                       false                    Left Indicator on
xkn2.e.indicator.r                       false                    Right Indicator on
xkn2.e.indicator.e                       false                    Emergency lights on
xkn2.e.preheat.timer1.enabled            false                    Preheat Timer1 Enabled             
xkn2.e.preheat.timer2.enabled            false                    Preheat Timer2 Enabled             
xkn2.e.preheating                        false                    Preheating             
xkn2.e.heated.steering                   false                    Heated Steering Wheel             
xkn2.e.rear.defogger                     false                    Rear Defogger             
xkn2.v.traction.control                  false                    Traction Control             
xkn2.e.trip                              12345Km                  Trip: Distance Travelled since Charged
xkn2.e.trip.energy.used                  12345kWh                 Trip: Energy Used since Charged
xkn2.e.trip.energy.recuperated         12345kWh                 Trip: Energy Recuperated since Charged
xkn2.v.trip.consumption                  9.5kW/100km              Power Consumption (kwH/100km) for current trip
xkn2.v.sb.driver                         false                    Seat Belt Driver             
xkn2.v.sb.passenger                      false                    Seat Belt Passenger             
xkn2.v.sb.back.right                     false                    Seat Belt Back Right             
xkn2.v.sb.back.middle                    false                    Seat Belt Back Middle             
xkn2.v.sb.back.left                      false                    Seat Belt Back Left             
xkn2.v.d.l.fl                            false                    Door Locked - Front Left             
xkn2.v.d.l.fr                            false                    Door Locked - Front Right             
xkn2.v.d.l.rl                            false                    Door Locked - Rear Left             
xkn2.v.d.l.rr                            false                    Door Locked - Rear Right
xkn2.v.c.current.req                     45A                      Requested charging current

======================================== ======================== ============================================

--------------
Custom Configs
--------------

======================================== ============== ========= ============================================
Config name                              Default value  …unit     Description
======================================== ============== ========= ============================================
xkn2 leftDrive                           true                     This car is left-hand-drive
xkn2 notify.charge.delay.ccs             15             Seconds   Wait time for DC charge power to ramp up before sending the notification
xkn2 notify.charge.delay.type2           10             Seconds   … same for AC charging
======================================== ============== ========= ============================================

----------
Debug Logs
----------

To see all PID poll results in your log, set log level ``verbose`` for component ``v-kianiroev2``.
