<h1>Alarm Library</h1>

<h2 style="color: black;">Data types</h2>

<table style="border-collapse: collapse; font-family: sans-serif; font-size: 14px;">
  <thead>
    <tr style="background-color: #f2f2f2; font-weight: bold;">
      <th style="border: 1px solid #ccc; padding: 4px 8px;">Data type</th>
      <th style="border: 1px solid #ccc; padding: 4px 8px;">Dependency</th>
    </tr>
  </thead>
  <tbody>
    <tr style="background-color: #fff;">
      <td style="border: 1px solid #ccc; padding: 4px 8px;">abstractAlarmLevel</td>
      <td style="border: 1px solid #ccc; padding: 4px 8px;">-</td>
    </tr>
    <tr style="background-color: #f2f2f2;">
      <td style="border: 1px solid #ccc; padding: 4px 8px;">abstractAlarmData</td>
      <td style="border: 1px solid #ccc; padding: 4px 8px;">abstractAlarmLevel</td>
    </tr>
    <tr style="background-color: #fff;">
      <td style="border: 1px solid #ccc; padding: 4px 8px;">alarmTraceGroupLevel</td>
      <td style="border: 1px solid #ccc; padding: 4px 8px;">-</td>
    </tr>
    <tr style="background-color: #f2f2f2;">
      <td style="border: 1px solid #ccc; padding: 4px 8px;">alarmTraceGroupData</td>
      <td style="border: 1px solid #ccc; padding: 4px 8px;">alarmTraceGroupLevel</td>
    </tr>
    <tr style="background-color: #fff;">
      <td style="border: 1px solid #ccc; padding: 4px 8px;">alarmTraceSuperLevel</td>
      <td style="border: 1px solid #ccc; padding: 4px 8px;">-</td>
    </tr>
    <tr style="background-color: #f2f2f2;">
      <td style="border: 1px solid #ccc; padding: 4px 8px;">alarmTraceSuperData</td>
      <td style="border: 1px solid #ccc; padding: 4px 8px;">alarmTraceSuperLevel</td>
    </tr>
    <tr style="background-color: #fff;">
      <td style="border: 1px solid #ccc; padding: 4px 8px;">alarmTraceGlobalLevel</td>
      <td style="border: 1px solid #ccc; padding: 4px 8px;">-</td>
    </tr>
    <tr style="background-color: #f2f2f2;">
      <td style="border: 1px solid #ccc; padding: 4px 8px;">alarmTraceGlobalData</td>
      <td style="border: 1px solid #ccc; padding: 4px 8px;">alarmTraceGlobalLevel</td>
    </tr>
  </tbody>
</table>


## Call Hierarchy

### Set alarm in object

#### Set alarm bit

| Function | Dependencies |
|:-------|:-------------|
| _alarmBit | - |
| _alarmBitWithOm | - |

#### Set alarm ID

| Function | Dependencies |
|:-------|:-------------|
| _alarmBit01Id | - |
| _alarmBit02Id | - |
| _alarmBit04Id | - |
| _alarmBit08Id | - |
| _alarmBit16Id | - |

#### Set alarm bit in map

| Function | Dependencies |
|:-------|:-------------|
| _alarmBitMap | - |

#### Set alarm level

| Function | Dependencies |
|:-------|:-------------|
| _alarmBitLevel | - |

#### Set alarm for Safety

| Function | Dependencies |
|:-------|:-------------|
| _alarmBitForSafety | _alarmBit |

### Alarm Trace

| Trace level | Function/Type | Dependencies |
|:------|:-------|:-------------|
| Object | abstractAlarmLevel | - |
| Object | abstractAlarmData | abstractAlarmLevel |
||||
| Group | alarmTraceGroupLevel | - |
| Group | alarmTraceGroupData | alarmTraceGroupLevel |
| Group | _alarmTraceGroupCollector | alarmTraceGroupData |
| Group | _alarmTraceGroupUpdater | alarmTraceGroupData |
||||
| Super | alarmTraceSuperLevel | - |
| Super | alarmTraceSuperData | alarmTraceSuperLevel |
| Super | _alarmTraceSuperCollector | alarmTraceGroupData <br> alarmTraceSuperData |
| Super | _alarmTraceSuperUpdater | alarmTraceSuperData |
||||
| Global | alarmTraceGlobalLevel | - |
| Global | alarmTraceGlobalData | alarmTraceGlobalLevel |
| Super | _alarmTraceGlobalCollector | alarmTraceSuperData <br> alarmTraceGlobalData |
| Super | _alarmTraceGlobalUpdater | alarmTraceGlobalData |

## Integration Layout

![__ doc __.svg](__doc__.svg)
