---
title: BP_REQUEST_INFO2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- BP_REQUEST_INFO2
helpviewer_keywords:
- BP_REQUEST_INFO2 structure
ms.assetid: 008c87f7-a76e-43d3-8904-11b225d6a9a5
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 65edef6585fd8367c6fb23c291bf4e8376de8861
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68153350"
---
# <a name="bprequestinfo2"></a>BP_REQUEST_INFO2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Obsahuje informace potřebné k implementaci zarážku, včetně dodavatele identifikátor GUID, omezení a zarážky s trasováním.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
typedef struct _BP_REQUEST_INFO2 {  
   BPREQI_FIELDS   dwFields;  
   GUID            guidLanguage;  
   BP_LOCATION     bpLocation;  
   IDebugProgram2* pProgram;  
   BSTR            bstrProgramName;  
   IDebugThread2*  pThread;  
   BSTR            bstrThreadName;  
   BP_CONDITION    bpCondition;  
   BP_PASSCOUNT    bpPassCount;  
   BP_FLAGS        dwFlags;  
   GUID            guidVendor;  
   BSTR            bstrConstraint;  
   BSTR            bstrTracepoint;  
} BP_REQUEST_INFO2;  
```  
  
```csharp  
public struct BP_REQUEST_INFO2 {  
   public uint           dwFields;  
   public Guid           guidLanguage;  
   public BP_LOCATION    bpLocation;  
   public IDebugProgram2 pProgram;  
   public string         bstrProgramName;  
   public IDebugThread2  pThread;  
   public string         bstrThreadName;  
   public BP_CONDITION   bpCondition;  
   public BP_PASSCOUNT   bpPassCount;  
   public uint           dwFlags;  
   public Guid           guidVendor;  
   public string         bstrConstraint;  
   public string         bstrTracepoint;  
};  
```  
  
## <a name="members"></a>Členové  
 `dwFields`  
 Kombinace příznaků z [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md) výčet, který určuje, která pole jsou vyplněna.  
  
 `guidLanguage`  
 Identifikátor GUID jazyka.  
  
 `bpLocation`  
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) struktura, která určuje typ umístění zarážky.  
  
 `pProgram`  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt, který reprezentuje aplikaci, ve kterém dochází k zarážce.  
  
 `bstrProgramName`  
 Název aplikace, ve kterém dochází k zarážce.  
  
 `pThread`  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objekt, který reprezentuje vláken, ve kterém dochází k zarážce.  
  
 `bstrThreadName`  
 Název vlákna, ve kterém dochází k zarážce.  
  
 `bpCondition`  
 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) struktura, která popisuje podmínky, za kterých se zarážka aktivuje.  
  
 `bpPassCount`  
 [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) strukturu, která obsahuje informace o počtu průchodu této zarážky.  
  
 `dwFlags`  
 Kombinace příznaků z [BP_FLAGS](../../../extensibility/debugger/reference/bp-flags.md) výčet, který určuje příznaky pro požadované zarážky.  
  
 `guidVendor`  
 Identifikátor GUID dodavatele. Může mít hodnotu null.  
  
 `bstrConstraint`  
 Název omezení zarážku. Může mít hodnotu null.  
  
 `bstrTracepoint`  
 Název bodu trasování. Může mít hodnotu null.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je vrácený [GetRequestInfo2](../../../extensibility/debugger/reference/idebugbreakpointrequest3-getrequestinfo2.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetRequestInfo2](../../../extensibility/debugger/reference/idebugbreakpointrequest3-getrequestinfo2.md)   
 [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)   
 [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)   
 [BP_FLAGS](../../../extensibility/debugger/reference/bp-flags.md)
