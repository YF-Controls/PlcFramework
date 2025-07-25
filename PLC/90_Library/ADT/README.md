# Abstract Data Types

[TOC]

## Methods

| Class | Int | Constant | Description |
|-------|-----|----------|-------------|
| Queue | 0 | METHOD_00_NIL | Method 00: Null |
| Queue | 1 | METHOD_01_INIT | Method 01: Initialize ADT |
| Queue | 10 | METHOD_10_ENQUEUE | Method 10: Add dato to last position |
| Queue | 11 | METHOD_11_DEQUEUE | Method 11: Remove data from first position |
| Queue | 12 | METHOD_12_PEEK | Method 12: Peek data from first position |
|  |  |  |  |
| Stack | 0 | METHOD_00_NIL | Method 00: Null |
| Stack | 1 | METHOD_01_INIT | Method 01: Initialize ADT |
| Stack | 10 | METHOD_10_PUSH | Method 10: Push data in stack |
| Stack | 11 | METHOD_11_POP | Method 11: Pop data from stack |
| Stack | 12 | METHOD_12_PEEK | Method 12: Peek data from stack |
|  |  |  |  |
| Linked List | 0 | METHOD_00_NIL | Method 00: Null |
| Linked List | 1 | METHOD_01_INIT | Method 01: Initialize ADT |
| Linked List | 10 | METHOD_10_ADD_FIRST | Method 10: Add first node element in list |
| Linked List | 11 | METHOD_11_ADD_LAST | Method 11: Add last node element in list |
| Linked List | 12 | METHOD_12_ADD_INDEX | Method 12: Add indexed node element in list |
| Linked List | 13 | METHOD_13_ADD_FIRST_HIGH_PRIORITY | Method 13: Add first high priority node element in list |
| Linked List | 14 | METHOD_14_ADD_LAST_HIGH_PRIORITY | Method 14: Add last high priority node element in list |
| Linked List | 15 | METHOD_15_ADD_FIRST_LOW_PRIORITY | Method 15: Add first low priority node element in list |
| Linked List | 16 | METHOD_16_ADD_LAST_LOW_PRIORITY | Method 16: Add last low priority node element in list |
| Linked List | 20 | METHOD_20_REMOVE_FIRST | Method 20: Remove first node element from list |
| Linked List | 21 | METHOD_21_REMOVE_LAST | Method 21: Remove last node element from list |
| Linked List | 22 | METHOD_22_REMOVE_INDEX | Method 22: Remove indexed node element from list |
| Linked List | 23 | METHOD_23_REMOVE_FIRST_PRIORITY | Method 23: Remove first priority node element from list |
| Linked List | 24 | METHOD_24_REMOVE_LAST_PRIORITY | Method 24: Remove last priority node element from list |
| Linked List | 30 | METHOD_30_READ_FIRST | Method 30: Read first node element from list |
| Linked List | 31 | METHOD_31_READ_LAST | Method 31: Read last node element from list |
| Linked List | 32 | METHOD_32_READ_INDEX | Method 32: Read indexed node element from list |
| Linked List | 33 | METHOD_33_READ_FIRST_PRIORITY | Method 33: Read first priority node element from list |
| Linked List | 34 | METHOD_34_READ_LAST_PRIORITY | Method 34: Read last priority node element from list |
|  |  |  |  |
| Hash Table | 0 | METHOD_00_NIL | Method 00: Null |
| Hash Table | 1 | METHOD_01_INIT | Method 01: Initialize ADT |
| Hash Table | 10 | METHOD_10_ADD | Method 10: Add data to hash table |
| Hash Table | 11 | METHOD_11_REMOVE | Method 11: Remove data from hash table |
| Hash Table | 12 | METHOD_12_READ | Method 12: Read data from hash table |

## Return (status)

| ENO | Int | Constant | Comment | Queue | Stack | Linked List | Hash Table |
|-----|-----|----------|---------|-------|-------|-------------|------------|
| TRUE | 16#0000 | STATUS_0000_DONE | Status: Done | Yes | Yes | Yes | Yes |
| FALSE | 16#8FFF | STATUS_8FFF_UNKNOWN_METHOD | Status: Error - Unknown method | Yes | Yes | Yes | Yes |
| FALSE | 16#8000 | STATUS_8000_NODE_LOWER_LIMIT_NOT_ZERO | Status: Error - Lower limit of node array is not zero | No | No | Yes | Yes |
| FALSE | 16#8001 | STATUS_8001_NODE_UPPER_LIMIT_LESS_THAN_ONE | Status: Error - Upper limit of node array is less than one | No | No | Yes | Yes |
| FALSE | 16#8002 | STATUS_8002_DATA_IS_NOT_ARRAY | Status: Error - Data array is not array | Yes | Yes | Yes | Yes |
| FALSE | 16#8003 | STATUS_8003_DATA_IS_NOT_VALID_ARRAY | Status: Error - Data array is not valid array | Yes | Yes | Yes | Yes |
| FALSE | 16#8004 | STATUS_8004_DATA_AND_NODE_DIFF_LEN | Status: Error - Data array and Node array have different length | No | No | Yes | Yes |
| FALSE | 16#8005 | STATUS_8005_DATA_ARRAY_LESS_THAN_TWO | Status: Error - Data array is less than two elements | Yes | Yes | Yes | Yes |
| FALSE | 16#8006 | STATUS_8006_KEY_IS_NOT_ARRAY | Status: Error - Key array is not array | No | No | No | Yes |
| FALSE | 16#8007 | STATUS_8007_KEY_IS_NOT_VALID_ARRAY | Status: Error - Key array is not valid array | No | No | No | Yes |
| FALSE | 16#8008 | STATUS_8008_KEY_AND_NODE_DIFF_LEN | Status: Error - Key array and Node array have different length | No | No | No | Yes |
| FALSE | 16#8009 | STATUS_8009_KEY_ARRAY_LESS_THAN_TWO | Status: Error - Key array is less than two elements | No | No | No | Yes |
| FALSE | 16#800A | STATUS_800A_MAP_LOWER_LIMIT_NOT_ZERO | Status: Error - Lower limit of map array is not zero | No | No | No | Yes |
| FALSE | 16#800B | STATUS_800B_MAP_UPPER_LIMIT_LESS_THAN_ONE | Status: Error - Upper limit of map array is less than one | No | No | No | Yes |
| FALSE | 16#8010 | STATUS_8010_IS_EMPTY | Status: Error - ADT is empty | Yes | Yes | Yes | Yes |
| FALSE | 16#8011 | STATUS_8011_IS_FULL | Status: Error - ADT is full | Yes | Yes | Yes | Yes |
| FALSE | 16#8012 | STATUS_8012_HASH_MAP_IS_EMPTY | Status: Error - Hash map is empty | No | No | No | Yes |
| FALSE | 16#8020 | STATUS_8020_ERROR_MOVE_BUFFER_TO_DATA | Status: Error - Movement from buffer to data | Yes | Yes | Yes | Yes |
| FALSE | 16#8021 | STATUS_8021_ERROR_MOVE_DATA_TO_BUFFER | Status: Error - Movement from data to buffer | Yes | Yes | Yes | Yes |
| FALSE | 16#8032 | STATUS_8022_ERROR_MOVE_BUFFER_TO_KEY | Status: Error - Movement from buffer key to key | No | No | No | Yes |
| FALSE | 16#8033 | STATUS_8023_ERROR_MOVE_KEY_TO_BUFFER | Status: Error - Movement from key to buffer key | No | No | No | Yes |
| FALSE | 16#8030 | STATUS_8030_INDEX_OUT_OF_RANGE | Status: Error - Index out of range | No | No | Yes | Yes |
| FALSE | 16#8031 | STATUS_8031_NODE_WAS_NOT_FOUND | Status: Error - Node was not found | No | No | Yes | Yes |
| FALSE | 16#8032 | STATUS_8032_KEY_WAS_NOT_FOUND | Status: Error - Key was not found | No | No | No | Yes |
