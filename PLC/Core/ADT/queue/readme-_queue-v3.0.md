# Queue: _(FIFO - First Input First Output)_ `v3.0`

## Description

You can use `_queue` `function` to `enqueue`, `dequeue` or read the first element (`peek`).

## Dependencies

| Type | Name | Version |
| :--- | :--- | :------ |
| `data type` | `queueInstanceAttributes` | v3.0 |

## Parameters

| Parameter | Declaration | Type | Description |
| :-------- | :---------- | :--- | :---------- |
| method | Input | `int` | Method to be executed:<br>1 = `METHOD_01_INIT` - Initialize<br>10 = `METHOD_10_ENQUEUE` - Add dato to last position<br>11 = `METHOD_11_DEQUEUE` - Remove data from first position<br>12 = `METHOD_12_PEEK` - Peek data from first position |
| instance | InOut | `queueInstanceAttributes` | Queue instance |
| data | InOut | `Variant` | Data array of type `<E>` |
| buffer | InOut | `Variant` | Buffer data of type `<E>` |
| - | Return | `int` | Return status:<br>0x0000 = `STATUS_0000_DONE` - Done<br>0x8002 = `STATUS_8002_DATA_IS_NOT_ARRAY` - Error: Data array is not array<br>0x8003 = `STATUS_8003_DATA_IS_NOT_VALID_ARRAY` - Error: `data` array is not valid array<br>0x8005 = `STATUS_8005_DATA_ARRAY_LESS_THAN_TWO` - Error - Data array is less than two elements<br>0x8010 = `STATUS_8010_IS_EMPTY` - Error - ADT is empty<br>0x8011 = `STATUS_8011_IS_FULL` - Error - ADT is full<br>0x8020 = `STATUS_8020_ERROR_MOVE_BUFFER_TO_DATA` - Error: Movement from buffer to data<br>0x8021 = `STATUS_8021_ERROR_MOVE_DATA_TO_BUFFER` Error: Movement from data to buffer<br>0x8FFF = `STATUS_8FFF_UNKNOWN_METHOD` - Error: Unknown method |

## Example

Use of `_queue`.

## See also

* [menu](/PLC/Core/ADT/queue/readme.md)
* [queueInstanceAttributes](/PLC/Core/ADT/queue/readme-queueInstanceAttributes-v3.0.md)
