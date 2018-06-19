---
title: IDebugCanStopEvent2::GetReason | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCanStopEvent2::GetReason
helpviewer_keywords:
- IDebugCanStopEvent2::GetReason
ms.assetid: f5de31ca-7b8d-4029-9cf9-ba860ac66af6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4c0eaefee714467084898182b338ceda63ebdc0f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31101986"
---
# <a name="idebugcanstopevent2getreason"></a>IDebugCanStopEvent2::GetReason
Získá důvod, proč chce Zastavte ladění modulu (DE).  
  
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
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána obvykle před [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md) metoda tak volajícím určit, zda chcete předat nulová (`TRUE`) k `IDebugCanStopEvent2::CanStop` metoda.  
  
 Z důvodu pro zastavení může být buď `CANSTOP_ENTRYPOINT`, což znamená, že je DE dosáhl vstupního bodu, nebo `CANSTOP_STEPIN`, což znamená, že je DE vstoupí do funkce.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md)   
 [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)