<div align="center">

## Peek and Poke from VB


</div>

### Description

Allows you to Peek and Poke memory

(For those not old enough to remember these commands, read a value from an address in memory and write a value to an address in memory)
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Duncan Jones](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/duncan-jones.md)
**Level**          |Intermediate
**User Rating**    |4.8 (43 globes from 9 users)
**Compatibility**  |VB 5\.0, VB 6\.0
**Category**       |[Windows API Call/ Explanation](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/windows-api-call-explanation__1-39.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/duncan-jones-peek-and-poke-from-vb__1-39808/archive/master.zip)

### API Declarations

```
Private Declare Sub CopyMemory Lib "kernel32" Alias "RtlMoveMemory" (Destination As Long, Source As Long, ByVal Length As Long)
Private Declare Sub CopyMemoryByte Lib "kernel32" Alias "RtlMoveMemory" (Destination As Byte, Source As Long, ByVal Length As Long)
Private Declare Sub CopyMemoryFromByte Lib "kernel32" Alias "RtlMoveMemory" (Destination As Long, Source As Byte, ByVal Length As Long)
```


### Source Code

```
'\\ API Declarations
Private Declare Sub CopyMemory Lib "kernel32" Alias "RtlMoveMemory" (Destination As Long, Source As Long, ByVal Length As Long)
Private Declare Sub CopyMemoryByte Lib "kernel32" Alias "RtlMoveMemory" (Destination As Byte, Source As Long, ByVal Length As Long)
Private Declare Sub CopyMemoryFromByte Lib "kernel32" Alias "RtlMoveMemory" (Destination As Long, Source As Byte, ByVal Length As Long)
'\\ Utility functions
Public Function Peek(Address As Long) As Long
Call CopyMemory(Peek, ByVal Address, Len(Address))
End Function
Public Function PeekByte(Address As Long) As Byte
Call CopyMemoryByte(PeekByte, ByVal Address, Len(PeekByte))
End Function
Public Function Poke(Address As Long, Value As Long)
CopyMemory ByVal Address, Value, LenB(Value)
End Function
Public Function PokeByte(Address As Long, Value As Byte)
CopyMemoryFromByte ByVal Address, Value, LenB(Value)
End Function
```

