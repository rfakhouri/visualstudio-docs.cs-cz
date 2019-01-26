---
title: IDebugCanStopEvent2::GetReason | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugCanStopEvent2::GetReason
helpviewer_keywords:
- IDebugCanStopEvent2::GetReason
ms.assetid: f5de31ca-7b8d-4029-9cf9-ba860ac66af6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b6b58e1a7a1f3595084a92f8db41d13875e47c0d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55041773"
---
# <a name="idebugcanstopevent2getreason"></a>IDebugCanStopEvent2::GetReason
Získá důvod, proč chce zastavit ladicí stroj (DE).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetReason(   
   CANSTOP_REASON* pcr  
);  
```  
  
```csharp  
int GetReason(   
   out enum_CANSTOP_REASON pcr  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pcr`  
 [out] Vrátí hodnotu z [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md) výčet, který je popsaný i důvod pro tuto událost.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je obvykle volána před provedením [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md) metodu, volající můžete určit, jestli se má předat nenulovou (`TRUE`) k `IDebugCanStopEvent2::CanStop` metody.  
  
 Může být důvodem zastavení `CANSTOP_ENTRYPOINT`, což znamená, že je DE dosáhla vstupní bod, nebo `CANSTOP_STEPIN`, což znamená, že je DE vstoupí do funkce.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md)   
 [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)