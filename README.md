# PFEP 1 - Style Guide for PLC Framework

|        |                 |
|-------:|:----------------|
| Author | Christian Yáñez |
| Status | ___Editing___ |
| Type   | Doc |
| Created | 2025-06-01 |
| Last edition | 2025-11-07 |

<!--[TOC]-->

## __Introduction__

This document gives coding conventions for this `PLC Framework`. The purpose of this document is to provide a clear guide for developing an application for the world of `Industrial Automation`

## __Naming of the data elements__

A key component of application development is the correct use of element names, which is why we emphasize understanding and applying this guide.

### __Constants__

The constants must be clear, descriptive, and comply with the following rules:

> 1. Snake case.
> 2. Always in upper case.
> 3. Words must be separated by underscores.
> 4. Name must always begin with a letter.
> 5. Safety constants must always begin with 'F_'.

<br>

<div style="padding: 10px; border-left: 4px solid green;">

```c
// ✅ Correct:
CONSTANT_NAME : int := 16#0001;
F_CONSTANT_NAME : int := 1;
```
</div><br>

<div style="padding: 10px; border-left: 4px solid red;">

```c
// ❌ Wrong:
constantname : int := 16#0000;
safetyconstantname : int := 1;
```
</div><br>

### __Variables__

Naming variables is perhaps the most challenging task when writing a program. Variables must be clear, concise, descriptive, and consistent with the action or state they represent. These are the rules:

> 1. Camel case.
> 2. Name must always begin with a lower case letter.
> 3. Safety variables must always begin with 'F_'.

<br>

<div style="padding: 10px; border-left: 4px solid green;">

```c
// ✅ Correct:
variableName : int := 20;
F_variableName : bool := false;
```

</div><br>

<div style="padding: 10px; border-left: 4px solid red;">

```c
// ❌ Wrong:
variablename : int := 20;
f_variable_name : bool := false;
```

</div><br>


<div style="padding: 10px; border-left: 4px solid orange;">

⚠️ ___Important notice___

_When a variable cannot be wrapped within a structure, an underscore can be used in variables._

```c
// ✅ Correct:
motorName_isRunning := bool;
motorName_id := string[10];
motorName_command := int;
```

```c
// ❌ Wrong:
motorNameIsRunning : int := 20;
motorNameId : bool := false;
```

</div><br>

### __Data Types__

The rules used for naming variables are used to name data structures:

> 1. Camel case
> 2. Name must always begin with a lower case letter
> 3. Safety data type must always begin with 'F_'

<br>

<div style="padding: 10px; border-left: 4px solid green;">

```c
// ✅ Correct:
motor : struct {
  id : string[20];
  isRunning : bool;
  command : uint;
  status : int;
}

F_status : struct {
  type : int;
  status : int;
}
```

</div><br>

<div style="padding: 10px; border-left: 4px solid red;">

```c
// ❌ Wrong:
Motor : struct {
  Id : string[20];
  is_running : bool;
  Command : uint;
  Status : int;
}

fstatus : struct {
  type : int;
  status : int;
}
```

</div><br>

<div style="padding: 10px; border-left: 4px solid orange;">

⚠️ ___Important notice___

_Underscore are not allowd._

</div><br>

### __Data Containers__

Data containers are large data structures that hold the program's static variables. Because they are immutable containers, their rules are based on the rules of constants.

> 1. Snake case
> 2. Always in upper case
> 3. Words must be separated by underscores
> 4. Name must always begin with a letter
> 5. Safety data container must always begin with 'F_'

<br>

<div style="padding: 10px; border-left: 4px solid green;">

```c
// ✅ Correct:
MOTOR_1 : DB1;
F_RTG1 : DB1000; // F_RTG means Safety Runtime Group
```
</div><br>

<div style="padding: 10px; border-left: 4px solid red;">

```c
// ❌ Wrong:
db_motor_1 : DB1;
di_f_rtg1 : DB1000;
```
</div><br>

<div style="padding: 10px; border-left: 4px solid orange;">

⚠️ __Important notice__  

_Data container is intended for PLCs such as `Siemens` that use `Data Blocks`._

</div><br>

## __Naming of code elements__

Code containers are one of the two fundamental parts of an application; this is where the lines of code that interact with the data are written.

### __Interruptions / Main Subroutines__

These containers are destinations for `OS` call points to execute programs; they are usually `hardware` interrupts, `cyclic` interrupts, `main` interrupts, etc. Since interrupts are immutable and the main entry points for events, they will be named following the rules for `constants`.

> 1. Snake case
> 2. Always in upper case
> 3. Words must be separated by underscores
> 4. Name must always begin with a letter
> 5. Safety interruption type must always begin with 'F_'

<br>

<div style="padding: 10px; border-left: 4px solid green;">

```c
// ✅ Correct:
call MAIN();
call F_MAIN();
call HW_INTERRUPT();
```
</div><br>

<div style="padding: 10px; border-left: 4px solid red;">

```c
// ❌ Wrong:
call mainSubruitine();
call fMain();
call hw_interrpt();
```
</div><br>

<div style="padding: 10px; border-left: 4px solid orange;">

⚠️ __Important notice__

_In `Siemens`  PLC you can start with the `OB` number, e.g. `OB001_MAIN`._

</div><br>

### __Subroutines__

Subroutines are the skeleton of the program; other subroutines, functions, and directly written code can be placed within them.

It is advisable that subroutines group together functions, actions, events, and states that are directly related to each other.

Subroutines must comply with the following rules:

> 1. Camel case
> 2. Name must always begin with an upper case letter
> 3. Safety variables must always begin with 'F_'

<br>

<div style="padding: 10px; border-left: 4px solid green;">

```c
// ✅ Correct:
call Group1(); // Subroutine to group motor of group 1.
call Hmi_Control(); // Subroutine to group HMI components.
call MotionControlProgram(); // Main subroutine to group al motor groups.
```
</div><br>

<div style="padding: 10px; border-left: 4px solid red;">

```c
// ❌ Wrong:
call group_01();
call hmiControl();
call motion_control_program();
```
</div><br>

<div style="padding: 10px; border-left: 4px solid orange;">

⚠️ __Important notice__

In the case that a `subroutine` has an associated data instance, the name of the instance must comply with the rules of the `data container`, but if the name of the `subroutine` coincides with the name of the `data container` and the programming environment does not distinguish between uppercase and lowercase letters, then it is allowed to add an underscore followed by the word `Control` or similar to the name of the `subroutine`.

```c
// ✅ Correct:
// Subroutine name is Motor, and instance is MOTOR:
call Motor_Control, MOTOR();

// Subroutine name is Conveyor01, and instance is CONVEYOR_01:
call Conveyor01, CONVEYOR_O1(); // or
call Conveyor01_Control, CONVEYOR_O1();
```

</div><br>




<div align="center" style="background-color: yellow; padding: 10px; border: 2px solid #ffc107; border-radius: 5px; margin: 20px 0; color: red;">

__🛠️ WORKING ON THIS DOCUMENT__

_This document is under active development. It may contain incomplete sections or frequent changes._

</div><br>

<br>
<br>
<br>
<br>
<br>


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

<!--div style="background-color: black; padding: 10px; border-left: 4px solid blue;"-->
<!--
### 🔔 Notas Importantes

**💡 CONSEJO:** Esto puede ayudarte a mejorar el rendimiento.

**⚠️ ADVERTENCIA:** Ten cuidado con este paso crítico.

**🚨 IMPORTANTE:** No omitas esta configuración esencial.

**📚 RECUERDA:** Estos conceptos son fundamentales para el proyecto.

-->