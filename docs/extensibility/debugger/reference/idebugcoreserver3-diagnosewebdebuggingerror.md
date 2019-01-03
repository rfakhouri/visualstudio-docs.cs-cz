---
title: IDebugCoreServer3::DiagnoseWebDebuggingError | Dokumentace Microsoftu
ms.date: 11/04/2016
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
ms.openlocfilehash: 1ba22bb5f8f20446b87236a4784b02e7ad2eb41e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53990750"
---
# <a name="idebugcoreserver3diagnosewebdebuggingerror"></a>IDebugCoreServer3::DiagnoseWebDebuggingError
Nepovedlo se pokusí zjistit, proč auto-attach.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT DiagnoseWebDebuggingError(  
   LPCWSTR pszUrl  
);  
```  
  
```csharp  
int DiagnoseWebDebuggingError(  
   string pszUrl  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszUrl`  
 [in] Není v současné době nepoužívá; musí být vždy nastavená na hodnotu null.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Tady jsou další typické návratové kódy:  
  
|Kód|Popis|  
|----------|-----------------|  
|`S_WEBDBG_UNABLE_TO_DIAGNOSE`|Nelze určit, proč se nepodařilo spustit ladění vzdáleném serveru.|  
|`S_WEBDBG_DEBUG_VERB_BLOCKED`|Nelze ladit na vzdáleném serveru, pravděpodobně z důvodu nedostatečných oprávnění nebo proto, že není povolen příkaz DEBUG.|  
|`E_WEBDBG_DEBUG_VERB_BLOCKED`|Webový server byl uzamčen a blokuje slovo DEBUG, která jsou nutná pro povolení ladění.|  
  
## <a name="see-also"></a>Viz také  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)