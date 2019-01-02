---
title: AD_PROCESS_ID_TYPE | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- AD_PROCESS_ID_TYPE
helpviewer_keywords:
- AD_PROCESS_ID_TYPE enumeration
ms.assetid: 0aab80e9-285a-4697-94ac-c864d42a6aaa
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f27791b555d2f18e1e0a338bbfb5893f9047fd4e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53819587"
---
# <a name="adprocessidtype"></a>AD_PROCESS_ID_TYPE
Určuje, jak interpretovat ID procesu v [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) struktury.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_AD_PROCESS_ID {  
   AD_PROCESS_ID_SYSTEM = 0,  
   AD_PROCESS_ID_GUID   = 1  
};  
typedef DWORD AD_PROCESS_ID_TYPE;  
```  
  
```csharp  
public enum enum_AD_PROCESS_ID {  
   AD_PROCESS_ID_SYSTEM = 0,  
   AD_PROCESS_ID_GUID   = 1  
};  
```  
  
## <a name="members"></a>Členové  
 AD_PROCESS_ID_SYSTEM  
 ID procesu je identifikátor systému. Použití `ProcessId.dwProcessId` pole [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) struktury.  
  
 AD_PROCESS_ID_GUID  
 ID procesu je identifikátor GUID. Použití `ProcessId.guidProcessId` pole `AD_PROCESS_ID` struktury.  
  
## <a name="remarks"></a>Poznámky  
 Používá pro `ProcessIdType` člena [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) strukturu, která určuje typ ID procesu, který je obsažen ve struktuře. Určuje, jak interpretovat `ProcessId` sjednocení ve struktuře.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)