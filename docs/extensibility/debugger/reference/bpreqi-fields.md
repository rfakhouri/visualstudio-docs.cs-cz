---
title: BPREQI_FIELDS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BPREQI_FIELDS
helpviewer_keywords:
- BPREQI_FIELDS enumeration
ms.assetid: 679e771e-4a79-484e-af37-f962ef4aa245
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ff66a2c23f96ad083d84a937a45c1b2b8cf3ddec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="bpreqifields"></a>BPREQI_FIELDS
Určuje informace, které mají být načteny o žádosti o zarážek.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_BPREQI_FIELDS {   
   BPREQI_BPLOCATION   = 0x0001,  
   BPREQI_LANGUAGE     = 0x0002,  
   BPREQI_PROGRAM      = 0x0004,  
   BPREQI_PROGRAMNAME  = 0x0008,  
   BPREQI_THREAD       = 0x0010,  
   BPREQI_THREADNAME   = 0x0020,  
   BPREQI_PASSCOUNT    = 0x0040,  
   BPREQI_CONDITION    = 0x0080,  
   BPREQI_FLAGS        = 0x0100,  
   BPREQI_ALLOLDFIELDS = 0x01ff  
   BPREQI_VENDOR       = 0x0200,   // BP_REQUEST_INFO2 only  
   BPREQI_CONSTRAINT   = 0x0400,   // BP_REQUEST_INFO2 only  
   BPREQI_TRACEPOINT   = 0x0800,   // BP_REQUEST_INFO2 only  
   BPREQI_ALLFIELDS    = 0x0fff    // BP_REQUEST_INFO2 only  
};  
typedef DWORD BPREQI_FIELDS;  
```  
  
```csharp  
public enum enum_BPREQI_FIELDS {   
   BPREQI_BPLOCATION   = 0x0001,  
   BPREQI_LANGUAGE     = 0x0002,  
   BPREQI_PROGRAM      = 0x0004,  
   BPREQI_PROGRAMNAME  = 0x0008,  
   BPREQI_THREAD       = 0x0010,  
   BPREQI_THREADNAME   = 0x0020,  
   BPREQI_PASSCOUNT    = 0x0040,  
   BPREQI_CONDITION    = 0x0080,  
   BPREQI_FLAGS        = 0x0100,  
   BPREQI_ALLOLDFIELDS = 0x01ff  
   BPREQI_VENDOR       = 0x0200,   // BP_REQUEST_INFO2 only  
   BPREQI_CONSTRAINT   = 0x0400,   // BP_REQUEST_INFO2 only  
   BPREQI_TRACEPOINT   = 0x0800,   // BP_REQUEST_INFO2 only  
   BPREQI_ALLFIELDS    = 0x0fff    // BP_REQUEST_INFO2 only  
};  
```  
  
## <a name="members"></a>Členové  
 BPREQI_BPLOCATION  
 Inicializace nebo použití `bpLocation` (zarážek umístění) pole [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) nebo [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) struktura.  
  
 BPREQI_LANGUAGE  
 Inicializace nebo použití `guidLanguage` pole z `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.  
  
 BPREQI_PROGRAM  
 Inicializace nebo použití `pProgram` pole z `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.  
  
 BPREQI_PROGRAMNAME  
 Inicializace nebo použití `bstrProgramName` pole z `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.  
  
 BPREQI_THREAD  
 Inicializace nebo použití `pThread` pole z `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.  
  
 BPREQI_THREADNAME  
 Inicializace nebo použití `bstrThreadName` pole z `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.  
  
 BPREQI_PASSCOUNT  
 Inicializace nebo použití `bpPassCount` pole z `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.  
  
 BPREQI_CONDITION  
 Inicializovat nebo použití `bpCondition` (podmínka zarážek) pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktura.  
  
 BPREQI_FLAGS  
 Inicializace nebo použití `dwFlags` pole z `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.  
  
 BPREQI_ALLOLDFIELDS  
 Inicializovat nebo použít pro všechna pole v z `BP_REQUEST_INFO` struktura.  
  
 BPREQI_VENDOR  
 Inicializace nebo pomocí `guidVendor` pole z `BP_REQUEST_INFO2` struktura.  
  
 BPREQI_CONSTRAINT  
 Inicializace nebo pomocí `bstrConstraint` pole z `BP_REQUEST_INFO2` struktura.  
  
 BPREQI_TRACEPOINT  
 Inicializace nebo pomocí `bstrTracepoint` pole z `BP_REQUEST_INFO2` struktura.  
  
 BPREQI_ALLFIELDS  
 Určuje pro všechna pole `BP_REQUEST_INFO2` struktura.  
  
## <a name="remarks"></a>Poznámky  
 Předat jako argument k [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md) a [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) metody k určení, které pole [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) a [BP_REQUEST_INFO2 ](../../../extensibility/debugger/reference/bp-request-info2.md) struktury mají být inicializován.  
  
 Tyto příznaky se také používají k označení které pole `BP_REQUEST_INFO` a `BP_REQUEST_INFO2` struktury jsou používány a platný, pokud je vrácen každou strukturu.  
  
 Tyto hodnoty mohou být kombinovány s bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)