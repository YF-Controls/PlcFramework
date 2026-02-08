# Remote access to variables

In all `FBs`, an acronym appears at the beginning of the variable comment.

> staticVariable : Bool; // `IR`: Rest of comment

| Acronym | Type | Access |
| :-----: | :--: | :----: |
| IR | `Input` | `Read` |
| IW | `Input` | `Read/Write` |
| IX | `Input` | `No access` |
| OR | `Output` | `Read` |
| OW | `Output` | `Read/Write` |
| OX | `Output` | `No access` |
| IOR | `InOut` | `Read` |
| IOW | `InOut` | `Read/Write` |
| IOX | `InOut` | `No access` |
| SR | `Static` | `Read` |
| SW | `Static` | `Read/Write` |
| SX | `Static` | `No access` |
