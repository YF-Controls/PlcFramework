# Queue Instance Attributes `v3.0`

## Description

This `data type` is used to store instance data for a `_queue`.

## Parameters

| Parameter | Type | Init. value | Description |
| :-------- | :--: | :---------: | :---------- |
| front | `dint` | 0 | Front pointer of queue |
| length | `dInt` | 0 | Queue size (current value) |
| total | `dInt` | 0 | Queue maximum size (constant value) |
| isEmpty | `bool` | 1 | 1=Queue is empty |
| isFull | `bool` | 0 | 1=Queue is full |
| isInitialized | `bool` | 0 | 1=Queue is initialized and ready to work |
| mutex | `bool` | 0 | Used to block or enable access to queue (User defines the rules) |

## See also

* [menu](/S7-1200-1500/Core/ADT/queue/readme.md)
* [_queue](/S7-1200-1500/Core/ADT/queue/readme-_queue-v3.0.md)
