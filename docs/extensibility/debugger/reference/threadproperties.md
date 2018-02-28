---
title: THREADPROPERTIES | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- THREADPROPERTIES
helpviewer_keywords:
- THREADPROPERTIES structure
ms.assetid: 7d397207-db03-4ec0-9f79-3794056ed89f
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 86fc5231f8d577e0456ce2d9f76c7b6d7f831280
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="threadproperties"></a>THREADPROPERTIES
Popisuje vlastnosti vlákno.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct _tagTHREADPROPERTIES {   
   THREADPROPERTY_FIELDS dwFields;  
   DWORD                 dwThreadId;  
   DWORD                 dwSuspendCount;  
   DWORD                 dwThreadState;  
   BSTR                  bstrPriority;  
   BSTR                  bstrName;  
   BSTR                  bstrLocation;  
} THREADPROPERTIES;  
```  
  
```csharp  
public struct THREADPROPERTIES {   
   public uint   dwFields;  
   public uint   dwThreadId;  
   public uint   dwSuspendCount;  
   public uint   dwThreadState;  
   public string bstrPriority;  
   public string bstrName;  
   public string bstrLocation;  
};  
```  
  
## <a name="members"></a>Členové  
 dwFields  
 Kombinace příznaků z [THREADPROPERTY_FIELDS](../../../extensibility/debugger/reference/threadproperty-fields.md) výčtu popisující pole, která v této struktuře jsou platné.  
  
 dwThreadId  
 ID vlákna.  
  
 dwSuspendCount  
 Vlákno pozastavit count.  
  
 dwThreadState  
 Hodnota z [THREADSTATE](../../../extensibility/debugger/reference/threadstate.md) výčet označující stav operační vlákno.  
  
 bstrPriority  
 Řetězec určující prioritu podprocesu; například "Normální výše", "Normální" nebo "Kritické čas".  
  
 bstName  
 Název vlákna.  
  
 bstrLocation  
 Vlákno umístění (obvykle rámce zásobníku nejhornější), obvykle vyjádřený jako název metody, kde je aktuálně zastavit provádění.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je vyplněna objektem volání [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md) metoda. Proto vrácené informace se obvykle používá při naplňování **vláken** okno.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)   
 [THREADPROPERTY_FIELDS](../../../extensibility/debugger/reference/threadproperty-fields.md)   
 [THREADSTATE](../../../extensibility/debugger/reference/threadstate.md)