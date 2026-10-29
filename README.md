## Flight software and embedded systems

 SWE B.S. @ Loyola Chicago, December 2027 graduation. **U.S. citizen, clearance-eligible.**
Looking for a **Summer 2027 internship** in flight software, firmware, or GNC.

Attitude estimation, flight controllers, and vehicle dynamics — multirotors,
eVTOL, and anything that has to know which way is up without being told.


antoniogarcia41624@gmail.com · [LinkedIn]()

---

### Open source

**[ArduPilot](https://github.com/ArduPilot/ardupilot)** — the autopilot behind a
large share of commercial and research UAVs.

- [#34890](https://github.com/ArduPilot/ardupilot/issues/34890) — reported a link
  failure that blocks SITL builds on current Xcode, traced to a `PACKED` struct
  placing a pointer at a 4-byte-aligned offset after Apple removed the classic
  linker.
- [#34924](https://github.com/ArduPilot/ardupilot/pull/34924) — reviewed the fix
  on the toolchain that reproduces the bug, including flying it in SITL.
- [#34928](https://github.com/ArduPilot/ardupilot/pull/34928) — follow-up PR
  replacing an unbounded compiler-version check with a configure-time linker
  probe, so a dead flag stops being passed to linkers that no longer accept it.
  *(open)*

### Projects

**[attitude-estimator](https://github.com/AdemiseG/attitude-estimator)** —
complementary filter estimating roll and pitch from gyro and accelerometer,
scored against ArduCopter SITL ground truth. **3.75° roll / 6.32° pitch RMS**
over a 176 s flight, against 52°/156° for raw gyro integration. Includes the
script that generates the flight data, and a writeup of the two mistakes that
nearly invalidated the results.

[![pitch estimate vs. ground truth](https://raw.githubusercontent.com/AdemiseG/attitude-estimator/main/thumb.png)](https://github.com/AdemiseG/attitude-estimator)

### Currently

- Bringing the attitude estimator up on a Teensy 4.1 with a real IMU. The
  filter is already ported to allocation-free C and reproduces the Python
  results exactly; what remains is the I2C driver and the sampling loop
- Working through ArduPilot issues to get deeper into the codebase

### Tools

Python · C · ArduPilot · SITL · MAVLink / pymavlink · waf · Git

<!-- Keep this list to things you can be interviewed on. Add C++, STM32,
     SPI/I2C, RTOS, PX4 as each becomes true - an inflated list is worse
     than a short one, because the interview finds out either way. -->
