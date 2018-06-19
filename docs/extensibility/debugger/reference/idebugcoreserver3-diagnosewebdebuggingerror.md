---
title: IDebugCoreServer3::DiagnoseWebDebuggingError | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCoreServer3::DiagnoseWebDebuggingError
helpviewer_keywords:
- IDebugCoreServer3::DiagnoseWebDebuggingError
ms.assetid: 8c4570ca-ae55-42f2-bbaa-8d8e75d2fa19
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d0facdbd5da7d17061039e0a9e7faed2be3bbe4b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31105061"
---
# <a name="idebugcoreserver3diagnosewebdebuggingerror"></a>IDebugCoreServer3::DiagnoseWebDebuggingError
Pokusí se zjistit, proč auto-attach se nezdařilo.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT DiagnoseWebDebuggingError(  
   LPCWSTR pszUrl  
);  
```  
  
```csharp  
int DiagnoseWebDebuggingError(  
   string pszUrl  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszUrl`  
 [v] Není právě používána; musí být vždy nastavená na hodnotu null.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. Tady jsou ostatní typické návratové kódy:  
  
|Kód|Popis|  
|----------|-----------------|  
|`S_WEBDBG_UNABLE_TO_DIAGNOSE`|Nelze určit, proč se nepodařilo spustit ladění vzdáleného serveru.|  
|`S_WEBDBG_DEBUG_VERB_BLOCKED`|Nelze ladění na vzdáleném serveru, pravděpodobně z důvodu nedostatečných oprávnění nebo protože není povolen příkaz DEBUG.|  
|`E_WEBDBG_DEBUG_VERB_BLOCKED`|Webový server byl uzamčen a blokuje příkaz DEBUG, který je nutný pro povolení ladění.|  
  
## <a name="see-also"></a>Viz také  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)