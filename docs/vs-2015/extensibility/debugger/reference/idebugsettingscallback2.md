---
title: IDebugSettingsCallback2 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugSettingsCallback2 interface
ms.assetid: 7e525d0b-7d7a-4d1c-8b78-e1398fa922f2
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 184cab04a4eaca2bf444bd31d6c97a3e6f0f7685
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629640"
---
# <a name="idebugsettingscallback2"></a>IDebugSettingsCallback2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugSettingsCallback2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugsettingscallback2).  
  
Umožňuje ladit weby snadněji číst nastavení metriky vzdáleně.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugSettingsCallback2D : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní je implementované událostí zpětného volání z správce ladění relace a používané ladicí stroj. Je možné využít také místně namísto Dbgmetric [d] lib.  
  
## <a name="methods"></a>Metody  
 V následující tabulce jsou uvedeny metody objektu `IDebugSettingsCallback2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[EnumEEs](../../../extensibility/debugger/reference/idebugsettingscallback2-enumees.md)|Vytvoří výčet vyhodnocení výrazu dostupné zadané identifikátory jazyka a dodavatele.|  
|[GetEELocalObject](../../../extensibility/debugger/reference/idebugsettingscallback2-geteelocalobject.md)|Načte objekt místní Chyba při vyhodnocování výrazu dle metriku.|  
|[GetEEMetricDword](../../../extensibility/debugger/reference/idebugsettingscallback2-geteemetricdword.md)|Načte hodnotu, která odpovídá zadané metriky vyhodnocovací filtr výrazů.|  
|[GetEEMetricFile](../../../extensibility/debugger/reference/idebugsettingscallback2-geteemetricfile.md)|Načte soubor metriky Chyba při vyhodnocování výrazu danou název nebo metriku.|  
|[GetEEMetricGuid](../../../extensibility/debugger/reference/idebugsettingscallback2-geteemetricguid.md)|Získá jedinečný identifikátor pro metriku Chyba při vyhodnocování výrazu jeho název.|  
|[GetEEMetricString](../../../extensibility/debugger/reference/idebugsettingscallback2-geteemetricstring.md)|Načte hodnotu řetězce metriku Chyba při vyhodnocování výrazu jeho název.|  
|[GetMetricDword](../../../extensibility/debugger/reference/idebugsettingscallback2-getmetricdword.md)|Načte hodnotu metriky jeho název.|  
|[GetMetricGuid](../../../extensibility/debugger/reference/idebugsettingscallback2-getmetricguid.md)|Získá jedinečný identifikátor metriku jeho název.|  
|[GetMetricString](../../../extensibility/debugger/reference/idebugsettingscallback2-getmetricstring.md)|Načte řetězec hodnoty metriky jeho název.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje funkci, která se používá **IDebugSettingsCallback2** objektu jako parametr.  
  
```cpp#  
HRESULT GetDebugSettingsCallback (IDebugSettingsCallback2 **ppCallback)  
{  
    HRESULT hRes = E_FAIL;  
  
    if ( ppCallback )  
   {  
        if ( EVAL(m_pdec) )  
            hRes = m_pdec->QueryInterface(IID_IDebugSettingsCallback2, (void **)ppCallback);  
        else  
            hRes = E_FAIL;  
    }  
    else  
        hRes = E_INVALIDARG;  
  
    return ( hRes );  
}  
```

