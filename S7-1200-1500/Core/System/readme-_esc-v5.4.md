# ESC: Emergency Stop Circuit - `v5.4`

## Table of Contents

- [Description](#description)
- [Dependencies](#dependencies)
- [Parameters](#parameters)
  - [Function](#function)
  - [Settings Structure](#settings-structure)
  - [HMI Commands](#hmi-commands)
- [Example](#example)

## Description

You can use `_esc` `function` to control the `Operating Modes` of an `Emergency Stop Circuit` in your system.

## Dependencies

| Type | Name | Version |
| :--- | :--- | :------ |
| `data type` | `escOutput` | [v2.2](/S7-1200-1500/Core/System/readme-escOutput-v2.2.md) |
| `function` | `TON_TIME` | Siemens FB |
| `function` | `TP_TIME` | Siemens FB |

## Parameters

### Function

| Parameter | Declaration | Type | Init. value | Description |
| :-------- | :---------: | :--: | :---------: | :---------- |
| F_emrgCircuitOk | Input | `Bool` | 1 | `IR`: 1= Emergency Circuit Ok |
| F_emrgStopOk | Input | `Bool` | 1 | `IR`: 1=Emergency Stop Ok |
| extControlOn | Input | `Bool` | 1 |`IR`: External control:<br>0= Control off<br>1= Control on |
| extOperatingMode | Input | `USint` | 4 | `IR`: External operating mode:<br>2= `OM_2_STOP` - Stop mode<br>3= `OM_3_MAINT` - Maintenance mode<br>4= `OM_4_MANUAL` - Manual mode<br>5= `OM_5_SEMIAUTO` - Semiautomatic mode<br>6= `OM_6_AUTO` - Automatic mode |
| extOperatingCycle | Input | `USint` | 0 | `IR`: External operating cycle:<br>3= `OC_3_MAINT_MOV` - Enable Maintenance movement<br>4= `OC_4_MANUAL_MOV` - Enable Manual movement<br>5= `OC_5_SEMIAUTO_STEP` - Enable Semiautomatic step<br>6= `OC_6_AUTO_CYCLE` - Enable Automatic cycle |
| extErrorAckn | Input | `Bool` | 0 | `IR`: 1= External error acknowledgement |
| extEmrgAckn | Input | `Bool` | 0 | `IR`: 1= External emergency acknowledgement |
| extLampTest | Input | `Bool` | 0 | `IR`: 1= External lamp test |
| hmiOk | Input | `Bool` | 0 | `IR`: 1= HMI panels are ok (this signal is used to enable/disable `hmiCommand` ) |
| settings | Input | `structure` | - | `IR`: Function configuration. [See here.](#settings-structure) |
| o | Output | `escOutput` | - |  `OR`: ESC output. [See here.](/S7-1200-1500/Core/System/readme-escOutput-v2.2.md) |
| selectedMode | Output | `USint` | 0 | `OR`: Show selected mode (Not the current mode |
| selectedCycle | Output | `USint` | 0 | `OR`: Show selected cycle (Not the current cycle) |
| hmiDisabled | Output | `Bool` | 0 | `OR`: 1=Hmi disabled, then disable `hmiCommand` variable and clear `o.oc.maintMov/manualMov` |
| hmiCommand | Static | `UInt` | 0 | `SW`: HMI Command. [See here.](#hmi-commands) |

<br>

🚨 What about `IR`, `SW`, etc.? [See Remote access to variables.](/S7-1200-1500/readme-remote-access-to-variables.md) 🚨

### Settings Structure

| settings | Type | Init. value | Description |
| :------- | :--: | :---------: | :---------- |
| WARM_RESTART | `Time` | `T#5S` | 0=Disabled<br>>0=Warm restart time |
| DELAY_ON | `Time` | `T#0s` | <=0=Disabled<br>>0=Delay actions as ackns, control on |
| DELAY_OFF | `Time` | `T#0s` | <=0=Disabled<br>>0=Delay actions as control off |
| useExtControlOn | `Bool` | 1 | 0=Use `hmiCommand` with:<br>- `HMI_CMD_00001_ON_OFF` <br>1=Use `controlOn` input |
| useExtOperatingMode | `Bool` | 1 | 0=Use `hmiCommand` with:<br>- `HMI_CMD_00002_OM_STOP`<br>- `HMI_CMD_00003_OM_MAINT`<br>- `HMI_CMD_00004_OM_MANUAL`<br>- `HMI_CMD_00005_OM_SEMI`<br>- `HMI_CMD_00006_OM_AUTO`<br>1=Use `extOperatingMode` input |
| useExtOperatingCycle | `Bool` | 1 | 0=Use `hmiCommand` with:<br>- `HMI_CMD_00007_MAINT_MOV`<br>- `HMI_CMD_00008_MANUAL_MOV`<br>- `HMI_CMD_00009_SEMI_STEP`<br>- `HMI_CMD_00010_AUTO_CYCLE`<br>1=Use `extOperatingCycle` input |
| useWarmrestartAsMode | `Bool` | 1 | 0=Warmrestart before to semi/automatic mode<br>1=Warmrestart before to semi/automatic cycle |
| useAutoStartCycle | `Bool` | 1 | 0=When mode changes to maint, manual, semi, auto, ESC waits for cycle<br>1=When mode changes to maint, manual, semi, auto, ESC autostarts cycle (Becareful this option can cause unexpected movements) |

### HMI Commands

The following list shows the useful `hmi commands` for this `function`.

| HMI Command | Value | Description |
| :---------- | :---: | :---------- |
| HMI_CMD_00000_NIL | 0 | HMI Command: 0000 - No action |
| HMI_CMD_00001_ON_OFF | 1 | HMI Command: 0001 - On/Off |
| HMI_CMD_00002_OM_STOP | 2 | HMI Command: 0002 - Stop mode |
| HMI_CMD_00003_OM_MAINT | 3 | HMI Command: 0003 - Maintenance mode |
| HMI_CMD_00004_OM_MANUAL | 4 | HMI Command: 0004 - Manual mode |
| HMI_CMD_00005_OM_SEMI | 5 | HMI Command: 0005 - Semiautomatic mode |
| HMI_CMD_00006_OM_AUTO | 6 | HMI Command: 0006 - Automatic mode |
| HMI_CMD_00007_MAINT_MOV | 7 | HMI Command: 0007 - Maintenance movement |
| HMI_CMD_00008_MANUAL_MOV | 8 | HMI Command: 0008 - Manual movement |
| HMI_CMD_00009_SEMI_STEP | 9 | HMI Command: 0009 - Semiautomatic step |
| HMI_CMD_00010_AUTO_CYCLE | 10 | HMI Command: 0010 - Automatic cycle |
| HMI_CMD_00011_ERROR_ACKN | 11 | HMI Command: 0011 - Error acknowledgement |
| HMI_CMD_00012_EMRG_ACKN | 12 | HMI Command: 0012 - Emergency acknowledgement |
| HMI_CMD_00013_LAMP_TEST | 13 | HMI Command: 0013 - Lamp test |

<br>

ℹ️ See full table [here](/S7-1200-1500/Core/HMI/__HMI_COMMAND__-v1.0.xlsx).

## Example

🚧 Working 🚧

## See also

🚧 Working 🚧

- [Remote access to variables.](/S7-1200-1500/readme-remote-access-to-variables.md)
- [HMI Commands.](/S7-1200-1500/Core/HMI/__HMI_COMMAND__-v1.0.xlsx)
- [Operating Modes.](/)
- [Operating Cycles.](/)
- [escOutput](/S7-1200-1500/Core/System/readme-escOutput-v2.2.md)