<div align="center">

[![PLC Framework](logo.svg)](https://docs.plcframework.com)

# PLC Framework

A very **Platypus**-like framework for designing modern PLC programs!

[![Documentation](https://img.shields.io/badge/docs-plcframework.com-blue)](https://docs.plcframework.com)

</div>

---

## Overview

PLC Framework provides a structured collection of functions, structures, enumeratios, adata types and utilities ready to import into projects.

---

## Current `Core` Structure

| Module | Description |
| :----- | :---------- |
| **ADT** | Abstract data types: queue, stack, priority queue |
| **Alarm** | Alarm bit monitoring, safety alarms, add-on integration |
| **Communication** | TCP, data exchange, network adapter config, logging |
| **Control** | PID controllers, conveyor technology, motion control, manual control |
| **Converter** | Unit and type converters (real ↔ string, angles, bit fields) |
| **DAD** | Device-specific drivers (IFM, Sick sensors) |
| **Datetime** | Date/time arithmetic, timestamps, delta time, formatting |
| **Fieldbus** | PROFINET device activation, diagnostics (LLDX, PNIO) |
| **HMI** | Physical buttons, coded light signals, acoustic signals, screen selection |
| **Node** | Node link UDTs for structured inter-block communication |
| **Protection** | Power supply monitoring (Siemens SITOP PSE200U) |
| **Safety** | UF safety status blocks (enkey, FDI, feedback, RxDI, SendDP/RcvDP) |
| **Scaling** | Linear interpolation |
| **String** | String utilities: fill/remove spaces |
| **System** | Background OB utilities, ESC routines |
| **Util** | Edge detection, bit toggle |

---

## Getting Started

Full documentation, development instructions and usage examples are available at:

**[docs.plcframework.com](https://docs.plcframework.com)**
