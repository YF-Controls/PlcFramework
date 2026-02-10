# Esc Output `v2.2`

## Table of Contents

- [Description](#description)
- [Parameters](#parameters)
  - [Data Type](#data-type)
  - [Om Structure](#om-structure)
  - [Oc Structure](#oc-structure)

## Description

This `data type` is used as a result of the `_esc` function.

## Parameters

### Data Type

| Parameter | Type | Init. value | Description |
| :-------- | :--: | :---------: | :---------- |
| om | `struct`| - | Operating modes. [See here.](#om-structure) |
| oc | `struct`| - | Operating cycles. [See here.](#oc-structure) |
| stopping | `Bool` | 0 | 1=Stopping sequence before to Control OFF |
| errorAckn | `Bool` | 0 | 1=Error acknowledgement |
| emrgAckn | `Bool` | 0 | 1=Emergency acknowledgement |
| lampTest | `Bool` | 0 | 1=Lamp test |

### Om Structure

| Parameter | Type | Init. value | Description |
| :-------- | :--: | :---------: | :---------- |
| SEL | `USint` | 0 | 0= `OM_0_CONTROL_OFF` - Control off<br>1= `OM_1_WARM_RESTART` - Warmrestart<br>2= `OM_2_STOP` - Stop<br>3= `OM_3_MAINT` - Maintenance<br>4= `OM_4_MANUAL` - Manual<br>5= `OM_5_SEMIAUTO` - Semiautomatic<br>6= `OM_6_AUTO` - Automatic<br>7= `OM_7_EMRG_STOP_UNACKN` - Emergency Stop unack.<br>8= `OM_8_EMRG_STOP_TRIGGERED` - Emergency Stop triggered |
| controlOn | `Bool` | 0 | 1=Control on |
| warmRestart | `Bool` | 0 | 1=Warmrestart (from any mode to automatic) |
| stopMode | `Bool` | 0 | 1=Stop mode |
| maintMode | `Bool` | 0 | 1=Maintenance mode |
| manualMode | `Bool` | 0 | 1=Manual mode |
| semiMode | `Bool` | 0 | 1=Semiautomatic mode |
| autoMode | `Bool` | 0 | 1=Automatic mode |
| emrgStopUnackn | `Bool` | 0 | 1=Emergency stop unacknowledged. (released but not ackn.) |
| emrgStopTriggered | `Bool` | 0 | 1=Emergency stop triggered |
| emrgStopOk | `Bool` | 0 | 1=Emergency stop ok |

### Oc Structure

| Parameter | Type | Init. value | Description |
| :-------- | :--: | :---------: | :---------- |
| SEL | `USint` | 0 | 0= `OC_0_NIL` - No cycle<br>3= `OC_3_MAINT_MOV` - Maintenance movement<br>4= `OC_4_MANUAL_MOV` - Manual movement<br>5= `OC_5_SEMIAUTO_STEP` - Semiautomatic step<br>6= `OC_6_AUTO_CYCLE` - Automatic cycle |
| maintMov | `Bool` | 0 | 1=Maintenance movement ready |
| manualMov | `Bool` | 0 | 1=Manual movement ready |
| semiStep | `Bool` | 0 | 1=Semiautomatic step ready |
| autoCycle | `Bool` | 0 | 1=Automatic cycle ready |

## See also

🚧 Working 🚧

- [Operating Modes.](/)
- [Operating Cycles.](/)
- [_esc](/S7-1200-1500/Core/System/readme-_esc-v5.4.md)
