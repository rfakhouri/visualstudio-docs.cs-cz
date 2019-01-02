---
title: DISASSEMBLY_STREAM_FIELDS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DISASSEMBLY_STREAM_FIELDS
helpviewer_keywords:
- DISASSEMBLY_STREAM_FIELDS enumeration
ms.assetid: cfc9b4de-c756-4844-bea7-d9f186a51d1b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8f7513ae0ac5094d51d4de2c7c4e0a49295110c2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53867472"
---
# <a name="disassemblystreamfields"></a>DISASSEMBLY_STREAM_FIELDS
Určuje, jaké informace se mají načíst o pole zpětný překlad.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_DISASSEMBLY_STREAM_FIELDS {   
   DSF_ADDRESS          = 0x00000001,  
   DSF_ADDRESSOFFSET    = 0x00000002,  
   DSF_CODEBYTES        = 0x00000004,  
   DSF_OPCODE           = 0x00000008,  
   DSF_OPERANDS         = 0x00000010,  
   DSF_SYMBOL           = 0x00000020,  
   DSF_CODELOCATIONID   = 0x00000040,  
   DSF_POSITION         = 0x00000080,  
   DSF_DOCUMENTURL      = 0x00000100,  
   DSF_BYTEOFFSET       = 0x00000200,  
   DSF_FLAGS            = 0x00000400,  
   DSF_OPERANDS_SYMBOLS = 0x00010000,  
   DSF_ALL              = 0x000107ff  
};  
typedef DWORD DISASSEMBLY_STREAM_FIELDS;  
```  
  
```csharp  
public enum enum_DISASSEMBLY_STREAM_FIELDS {   
   DSF_ADDRESS          = 0x00000001,  
   DSF_ADDRESSOFFSET    = 0x00000002,  
   DSF_CODEBYTES        = 0x00000004,  
   DSF_OPCODE           = 0x00000008,  
   DSF_OPERANDS         = 0x00000010,  
   DSF_SYMBOL           = 0x00000020,  
   DSF_CODELOCATIONID   = 0x00000040,  
   DSF_POSITION         = 0x00000080,  
   DSF_DOCUMENTURL      = 0x00000100,  
   DSF_BYTEOFFSET       = 0x00000200,  
   DSF_FLAGS            = 0x00000400,  
   DSF_OPERANDS_SYMBOLS = 0x00010000,  
   DSF_ALL              = 0x000107ff  
};  
```  
  
## <a name="members"></a>Členové  
 DSF_ADDRESS  
 Inicializace/použít `bstrAddress` pole.  
  
 DSF_ADDRESSOFFSET  
 Inicializace/použít `bstrAddressOffset` pole.  
  
 DSF_CODEBYTES  
 Inicializace/použít `bstrCodeBytes` pole.  
  
 DSF_OPCODE  
 Inicializace/použít `bstrOpCode` pole.  
  
 DSF_OPERANDS  
 Inicializace/použít `bstrOperands` pole.  
  
 DSF_SYMBOL  
 Inicializace/použít `bstrSymbol` pole.  
  
 DSF_CODELOCATIONID  
 Inicializace/použít `uCodeLocationId` pole.  
  
 DSF_POSITION  
 Inicializace/použít `posBeg` a `posEnd` pole.  
  
 DSF_DOCUMENTURL  
 Inicializace/použít `bstrDocumentUrl` pole.  
  
 DSF_BYTEOFFSET  
 Inicializace/použít `dwByteOffset` pole.  
  
 DSF_FLAGS  
 Inicializace/použít `dwFlags` ([DISASSEMBLY_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md)) pole.  
  
 DSF_OPERANDS_SYMBOLS  
 Zahrnout názvy symbolů v `bstrOperands` pole.  
  
 DSF_ALL  
 Určuje všechna pole pro datový proud zpětný překlad.  
  
## <a name="remarks"></a>Poznámky  
 Předán jako parametr [čtení](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md) indikace polí s [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) struktury mají být inicializovány.  
  
 Používá pro `dwFields` člena `DisassemblyData` struktury k označení pole, která se používá a je platný vrátila strukturu.  
  
 Tyto hodnoty lze kombinovat pomocí logické bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)   
 [Pro čtení](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)   
 [DISASSEMBLY_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md)