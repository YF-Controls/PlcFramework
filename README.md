# PLC Coding Style

[TOC]

## 1. Data

### 1.1. Constants

> **Rules**
>
> 1. Snake case
> 2. Always in upper case
> 3. Words must be separated by underscores
> 4. Name must always begin with a letter
> 5. Safety constants must always begin with 'F_'
>

* CONSTANT_NAME
* F_CONSTANT_NAME

### 1.2. Variables

> **Rules**
>
> 1. Camel case
> 2. Name must always begin with a lower case letter
> 3. Safety variables must always begin with 'F_'
>

* variableName
* F_variableName

### 1.3 Data Types

> **Rules**
>
> 1. Camel case
> 2. Name must always begin with a lower case letter
> 3. Safety data type must always begin with 'F_'
>

* dataTypeName
* F_dataTypeName

### 1.4. Data Containers

> **Rules**
>
> 1. Snake case
> 2. Always in upper case
> 3. Words must be separated by underscores
> 4. Name must always begin with a letter
> 5. Safety data container must always begin with 'F_'
>

* CONTAINER_NAME
* F_CONTAINER_NAME
_Applicable in Siemens Datablock: DB or DI_

## 2. Enumerations

* __Operating mode__

| usint | Operating mode |
|:-----:|:---------------|
| 0 | Control off |
| 1 | Warm restart |
| 2 | Stop mode |
| 3 | Maintenance mode |
| 4 | Semiautomatic mode |
| 5 | Automatic mode |
| 6 | Emergency stop unacknowledged |
| 7 | Emergency stop triggered |

* __Operating cycle__

| usint | Operating cycle |
|:-----:|:----------------|
| 0 | No cycle |
| 3 | Maintenance movement |
| 4 | Manual movement |
| 5 | Semiautomatic step |
| 6 | Automatic cycle |

* __Command cycles__

| int | Operating cycle |
|:---:|:----------------|
| -1 | No cycle |
| 0..N | Cycle number |

* __Alarm levels__

| usint | Alarm levels |
|:---:|:----------------|
| 0 | No alarm |
| 1 | Information alarm |
| 2 | Warning alarm |
| 3 | Error alarm |
| 4 | Emergency alarm |

* __State machine__

| int | State machine |
|:---:|:--------------|
| 0 | Wait |
| 0x0001..0x6FFF | Normal step |
| 0x7000..0x7FFF | Warning step |
| 0x8000..0x8FFF | Error step |

* __Synchronous function status__

| int | Status |
|:---:|:-------|
| 0 | Done |
| 0x8000..0x8FFF | Error |

* __Asynchronous function status__

| int | Status |
|:---:|:-------|
| 0 | Wait |
| 1 | Request |
| 2 | Busy |
| 3 | Done |
| 0x8000..0x8FFF | Error |

* __HMI Commands__

| uint | HMI Command |
|:----:|:------------|
| 0 | Null |
| 1..N | Command number |

* __Drive action__

| usint | HMI Command |
|:----:|:------------|
| 0 | Stopped |
| 1 | Running forward |
| 3 | Running backward |

## 3. Code

### 3.1. Interruptions / Main Subroutines

> **Rules**
>
> 1. Snake case
> 2. Always in upper case
> 3. Words must be separated by underscores
> 4. Name must always begin with a letter
> 5. Safety interruption type must always begin with 'F_'
> 

* INTERRUPTION_NAME
* MAIN_PROGRAM_NAME
* OB000_NAME _'Applicable in Siemens OB'_

### 3.2. Subroutines

> **Rules**
>
> 1. Camel case
> 2. Name must always begin with an upper case letter
> 3. Safety variables must always begin with 'F_'
>

* SubroutineName
* F_SubroutineName

### 3.3. Functions

> **Rules**
>
> 1. Camel case
> 2. Name must always begin with an underscore
> 3. Safety variables must always begin with '_F_'
>

* _functionName
* _F_functionName

### 3.4. Modules

> **Rules**
>
> 1. Camel case
> 2. Name must always begin with '_M_'
> 3. Module name begins with upper case letter
> 4. Safety module must always begin with '_F'
>

* _M_ModuleName
* _FM_ModuleName

## 4. Program Folder Hierarchy

| ID | Folder |
|:---|:-------|
| 00_OB  | Organization Blocks |
| 00_Settings | Setting Blocks |
| 01_FSP | Fail-Safe Program |
| 02_SCP | System Control Program |
| 03_HW | Hardware Handling |
| 04_HMI | Human-Machine Interface |
| 05_SEQ | Sequence Program |
| 06_MCP | Motion Control Program |
| 07_PCP | Process Control Program |
| 08_DAD | Data Acquisition Devices |
| - | - |
| 10_ITX  | Information Technology Exchange |
| 11_LLDX | Low-Level Data Exchange |
| - | - |
| 90_Library | Standar Library |
| 91_Vendor | Vendor Libraries |
| 92_Custom | Custom Library |
