---
title: IDebugProgramProvider2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProgramProvider2
helpviewer_keywords:
- IDebugProgramProvider2 interface
ms.assetid: a9ec7b3e-a59c-4069-b2ee-6f45916eeb78
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6a3ccac5dc60c10983d3b1a33978196fad5197d6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68146314"
---
# <a name="idebugprogramprovider2"></a>IDebugProgramProvider2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní umožňuje ladicí relace správci získávat informace o programech, které jsou "publikovaná" prostřednictvím [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md) rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProgramProvider2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní k poskytnutí informací o programech, které jsou právě laděny. Toto rozhraní je zaregistrovaný v oddíle DE registru pomocí metriku `metricProgramProvider`, jak je popsáno v [Pomocníci sad SDK pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md).  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání modelu COM `CoCreateInstance` pracovat `CLSID` poskytovatele program, který se získal z registru. Podívejte se na příklad.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)|Získá informace o programech pro spuštění, filtrovat v mnoha různými způsoby.|  
|[GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)|Získá uzel program zadané ID konkrétní procesu.|  
|[WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)|Vytvoří zpětné volání ke sledování pro zprostředkovatele událostí spojených s konkrétní druhy procesy.|  
|[SetLocale](../../../extensibility/debugger/reference/idebugprogramprovider2-setlocale.md)|Vytvoří národní prostředí pro všechny prostředky specifické pro jazyk vyžadované DE.|  
  
## <a name="remarks"></a>Poznámky  
 Za normálních okolností proces používá toto rozhraní najdete informace o spuštěné v tomto procesu.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="example"></a>Příklad  
  
```cpp#  
IDebugProgramProvider2 *GetProgramProvider(GUID *pDebugEngineGuid)  
{  
    // This is typically defined globally.  For this example, it is  
    // defined here.  
    static const WCHAR strRegistrationRoot[] = L"Software\\Microsoft\\VisualStudio\\8.0Exp";  
    IDebugProgramProvider2 *pProvider = NULL;  
    if (pDebugEngineGuid != NULL) {  
        CLSID clsidProvider = { 0 };  
        ::GetMetric(NULL,  
                    metrictypeEngine,  
                    *pDebugEngineGuid,  
                    metricProgramProvider,  
                    &clsidProvider,  
                    strRegistrationRoot);  
        if (!IsEqualGUID(clsidProvider,GUID_NULL)) {  
            CComPtr<IDebugProgramProvider2> spProgramProvider;  
            spProgramProvider.CoCreateInstance(clsidProvider);  
            if (spProgramProvider != NULL) {  
                pProvider = spProgramProvider.Detach();  
            }  
        }  
    }  
    return(pProvider);  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramPublisher2](../../../extensibility/debugger/reference/idebugprogrampublisher2.md)   
 [Pomocníci sad SDK pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)
