# Esc Output `v2.2`

## Description

This `data type` is used as a result of the `_esc` function.

## Parameters

| Parameter | Type | Init. value | Description |
| :-------- | :--: | :---------: | :---------- |
| om | `struct`| - | Operating modes. [See om table](#om-structure) |
| oc | `struct`| - | Operating cycles. [See oc table](#oc-structure) |
| stopping | `bool` | 0 | 1=Stopping sequence before to Control OFF |
| errorAckn | `bool` | 0 | 1=Error acknowledgement |
| emrgAckn | `bool` | 0 | 1=Emergency acknowledgement |
| lampTest | `bool` | 0 | 1=Lamp test |

### om structure

| Parameter | Type | Init. value | Description |
| :-------- | :--: | :---------: | :---------- |
| SEL | `USInt` | 0 | 0= `OM_0_CONTROL_OFF` - Control off<br>1= `OM_1_WARM_RESTART` - Warmrestart<br>2= `OM_2_STOP` - Stop<br>3= `OM_3_MAINT` - Maintenance<br>4= `OM_4_MANUAL` - Manual<br>5= `OM_5_SEMIAUTO` - Semiautomatic<br>6= `OM_6_AUTO` - Automatic<br>7= `OM_7_EMRG_STOP_UNACKN` - Emergency Stop unack.<br>8= `OM_8_EMRG_STOP_TRIGGERED` - Emergency Stop triggered |
| controlOn | `bool` | 0 | 1=Control on |
| warmRestart | `bool` | 0 | 1=Warmrestart (from any mode to automatic) |
| stopMode | `bool` | 0 | 1=Stop mode |
| maintMode | `bool` | 0 | 1=Maintenance mode |
| manualMode | `bool` | 0 | 1=Manual mode |
| semiMode | `bool` | 0 | 1=Semiautomatic mode |
| autoMode | `bool` | 0 | 1=Automatic mode |
| emrgStopUnackn | `bool` | 0 | 1=Emergency stop unacknowledged. (released but not ackn.) |
| emrgStopTriggered | `bool` | 0 | 1=Emergency stop triggered |
| emrgStopOk | `bool` | 0 | 1=Emergency stop ok |

### oc structure

| Parameter | Type | Init. value | Description |
| :-------- | :--: | :---------: | :---------- |
| SEL | `USInt` | 0 | 0= `OC_0_NIL` - No cycle<br>3= `OC_3_MAINT_MOV` - Maintenance movement<br>4= `OC_4_MANUAL_MOV` - Manual movement<br>5= `OC_5_SEMIAUTO_STEP` - Semiautomatic step<br>6= `OC_6_AUTO_CYCLE` - Automatic cycle |
| maintMov | `bool` | 0 | 1=Maintenance movement ready |
| manualMov | `bool` | 0 | 1=Manual movement ready |
| semiStep | `bool` | 0 | 1=Semiautomatic step ready |
| autoCycle | `bool` | 0 | 1=Automatic cycle ready |

## See also


