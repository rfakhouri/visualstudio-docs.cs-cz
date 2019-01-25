---
title: IDebugPendingBreakpoint2::SetCondition | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugPendingBreakpoint2::SetCondition
helpviewer_keywords:
- SetCondition method
- IDebugPendingBreakpoint2::SetCondition method
ms.assetid: 0534224f-654f-4862-bc4d-a9a81a5f8899
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d9db02ada04b236ec190d11568eb1f4f35db6244
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54834339"
---
# <a name="idebugpendingbreakpoint2setcondition"></a>IDebugPendingBreakpoint2::SetCondition
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nastavuje nebo mění podmínky spojené se čekající zarážkou.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT SetCondition(   
   BP_CONDITION bpCondition  
);  
```  
  
```csharp  
int SetCondition(   
   BP_CONDITION bpCondition  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `bpCondition`  
 [in] A [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) struktura, která určuje podmínku, která má nastavit.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Jakoukoli podmínku, která byla dříve přidružená čekající zarážka se ztratí. Všechny zarážky, které jsou vázány z této čekající zarážka se nazývají nastavit jejich stav na hodnotu zadanou v `bpCondition` parametru.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)
