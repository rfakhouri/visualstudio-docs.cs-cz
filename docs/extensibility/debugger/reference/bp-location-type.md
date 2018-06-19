---
title: BP_LOCATION_TYPE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_LOCATION_TYPE
helpviewer_keywords:
- BP_LOCATION_TYPE structure
ms.assetid: 0248430a-3b61-4809-87a9-e9b6bb7d1130
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: db35e354b2cfbe91b9c6041dc6239d2dfd2531f8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31108940"
---
# <a name="bplocationtype"></a>BP_LOCATION_TYPE
Určuje umístění druh Breakpoint – pro žádost o zarážek.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_BP_LOCATION_TYPE {   
   BPLT_NONE               = 0x00000000,  
   BPLT_FILE_LINE          = 0x00010000,  
   BPLT_FUNC_OFFSET        = 0x00020000,  
   BPLT_CONTEXT            = 0x00030000,  
   BPLT_STRING             = 0x00040000,  
   BPLT_ADDRESS            = 0x00050000,  
   BPLT_RESOLUTION         = 0x00060000,  
   BPLT_CODE_FILE_LINE     = BPT_CODE | BPLT_FILE_LINE,  
   BPLT_CODE_FUNC_OFFSET   = BPT_CODE | BPLT_FUNC_OFFSET,  
   BPLT_CODE_CONTEXT       = BPT_CODE | BPLT_CONTEXT,  
   BPLT_CODE_STRING        = BPT_CODE | BPLT_STRING,  
   BPLT_CODE_ADDRESS       = BPT_CODE | BPLT_ADDRESS ,  
   BPLT_DATA_STRING        = BPT_DATA | BPLT_STRING,  
   BPLT_TYPE_MASK          = 0x0000FFFF,  
   BPLT_LOCATION_TYPE_MASK = 0xFFFF0000  
};  
typedef DWORD BP_LOCATION_TYPE;  
```  
  
```csharp  
public enum enum_BP_LOCATION_TYPE {   
   BPLT_NONE               = 0x00000000,  
   BPLT_FILE_LINE          = 0x00010000,  
   BPLT_FUNC_OFFSET        = 0x00020000,  
   BPLT_CONTEXT            = 0x00030000,  
   BPLT_STRING             = 0x00040000,  
   BPLT_ADDRESS            = 0x00050000,  
   BPLT_RESOLUTION         = 0x00060000,  
   BPLT_CODE_FILE_LINE     = BPT_CODE | BPLT_FILE_LINE,  
   BPLT_CODE_FUNC_OFFSET   = BPT_CODE | BPLT_FUNC_OFFSET,  
   BPLT_CODE_CONTEXT       = BPT_CODE | BPLT_CONTEXT,  
   BPLT_CODE_STRING        = BPT_CODE | BPLT_STRING,  
   BPLT_CODE_ADDRESS       = BPT_CODE | BPLT_ADDRESS ,  
   BPLT_DATA_STRING        = BPT_DATA | BPLT_STRING,  
   BPLT_TYPE_MASK          = 0x0000FFFF,  
   BPLT_LOCATION_TYPE_MASK = 0xFFFF0000  
};  
```  
  
## <a name="members"></a>Členové  
 BPLT_NONE  
 Určuje bez zarážek umístění.  
  
 BPLT_FILE_LINE  
 Určuje typ umístění zarážce jako řádek souboru.  
  
 BPLT_FUNC_OFFSET  
 Určuje typ umístění zarážce jako klauzuli offset funkce.  
  
 BPLT_CONTEXT  
 Určuje typ umístění zarážce kontext.  
  
 BPLT_STRING  
 Určuje typ umístění zarážce jako řetězec.  
  
 BPLT_ADDRESS  
 Určuje typ umístění zarážce adresy.  
  
 BPLT_RESOLUTION  
 Určuje typ umístění zarážce jako řešení.  
  
 BPLT_CODE_FILE_LINE  
 Určuje typ umístění zarážce jako řádek zdrojového kódu.  
  
 BPLT_CODE_FUNC_OFFSET  
 Určuje typ umístění zarážce jako klauzuli offset funkce kódu.  
  
 BPLT_CODE_CONTEXT  
 Určuje typ umístění zarážce jako kontext kódu.  
  
 BPLT_CODE_STRING  
 Určuje typ umístění zarážce jako řetězec v kódu.  
  
 BPLT_CODE_ADDRESS  
 Určuje typ umístění zarážce jako adresu, kódem.  
  
 BPLT_DATA_STRING  
 Určuje typ umístění zarážce jako řetězec data.  
  
 BPLT_TYPE_MASK  
 Určuje bitová maska, tak, aby typ zarážek lze extrahovat mimo hodnotu.  
  
 BPLT_LOCATION_TYPE_MASK  
 Určuje bitová maska, tak, aby typ zarážek umístění lze extrahovat mimo hodnotu.  
  
## <a name="remarks"></a>Poznámky  
 Předá jako parametr, který se [GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md) metoda.  
  
 Typ umístění zarážek se skládá z typu zarážek a typ umístění. To znamená, že typu zarážek umístění se nikdy právě typu zarážek (například `BPT_CODE`) nebo typ umístění (například `BPLT_FILE_LINE`). Předdefinované konstanty pro všechny typy zarážek umístění aktuálně podporované jsou součástí tento výčet (`BPLT_CODE_FILE_LINE` prostřednictvím `BPLT_DATA_STRING`).  
  
 `BPT_CODE` a `BPT_DATA` jsou členy [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md) výčtu.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md)   
 [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md)