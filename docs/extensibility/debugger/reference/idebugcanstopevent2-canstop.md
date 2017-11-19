---
title: IDebugCanStopEvent2::CanStop | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCanStopEvent2::CanStop
helpviewer_keywords: IDebugCanStopEvent2::CanStop
ms.assetid: 7d61adbe-6b3d-41f3-86a1-45d9cc01a7f8
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d9008410831d3c2c7b6e93d4f35a1d08914a5336
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugcanstopevent2canstop"></a>IDebugCanStopEvent2::CanStop
Upozorní modul ladění (DE), zda chcete zastavit aktuální umístění kódu nebo jenom v provádění pokračovat.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CanStop (   
   BOOL fCanStop  
);  
```  
  
```csharp  
int CanStop (   
   int fCanStop  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `fCanStop`  
 [v] Nenulová (`TRUE`) Pokud je DE by se měla zastavit do aktuálního umístění kódu; jinak hodnota nula (`FALSE`).  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Příjemce této události obvykle volá [getreason –](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md) metoda chcete zjistit, proč je DE chce zastavit a poté zavolá `IDebugCanStopEvent2::CanStop` metoda s odpovídající odpověď.  
  
 Pokud je DE zastaví, odešle událost, která popisuje příčinou zastavit. Obvykle existují dvě události, které se odesílají zalomení uživatele nebo signál reprezentována [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) rozhraní a zarážek události, které [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)   
 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)   
 [Getreason –](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)