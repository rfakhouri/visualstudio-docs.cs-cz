---
title: "Idiaenumsegments – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumSegments interface
ms.assetid: 0c9edd5e-b9ce-43e1-a791-cd4c5d16d923
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d0f30e266389a3abfa3c0af1275cada34c9cfe11
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumsegments"></a>IDiaEnumSegments
Provede výčet různých segmentů obsažené v datovém zdroji.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaEnumSegments : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDiaEnumSegments`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Idiaenumsegments::get__newenum –](../../debugger/debug-interface-access/idiaenumsegments-get-newenum.md)|Načte [IEnumVARIANT rozhraní](http://msdn.microsoft.com/en-us/139e3c93-faef-4003-9079-e0e94494db3e) verzi této enumerátor.|  
|[Idiaenumsegments::get_count –](../../debugger/debug-interface-access/idiaenumsegments-get-count.md)|Načte počet segmentů.|  
|[Idiaenumsegments::Item –](../../debugger/debug-interface-access/idiaenumsegments-item.md)|Načte segment prostřednictvím indexu.|  
|[Idiaenumsegments::Next –](../../debugger/debug-interface-access/idiaenumsegments-next.md)|Načte zadaný počet segmentů v pořadí výčtu.|  
|[Idiaenumsegments::Skip –](../../debugger/debug-interface-access/idiaenumsegments-skip.md)|Přeskočí zadaný počet segmentů v posloupnosti výčtu.|  
|[Idiaenumsegments::Reset –](../../debugger/debug-interface-access/idiaenumsegments-reset.md)|Návrat na začátek v sekvenci výčtu.|  
|[Idiaenumsegments::clone –](../../debugger/debug-interface-access/idiaenumsegments-clone.md)|Vytvoří enumerátor, který obsahuje stav výčtu jako aktuální enumerátor.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Získat toto rozhraní vyvoláním `QueryInterface` metodu [idiatable –](../../debugger/debug-interface-access/idiatable.md) objektu. Podívejte se na příklad podrobnosti.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak získat `IDiaEnumSections` rozhraní z tabulky. Více kompletní příklad, jak pomocí segmenty, najdete v článku [idiasegment –](../../debugger/debug-interface-access/idiasegment.md) rozhraní.  
  
```C++  
void ShowSegments(IDiaTable *pTable, IDiaSession *pSession)  
{  
    CComPtr<IDiaEnumSegments> pSegments;  
    if ( SUCCEEDED( pTable->QueryInterface(  
                                __uuidof( IDiaEnumSegments ),  
                                (void**)&pSegments )  
                  )  
       )  
    {  
        // Do something with this enumeration  
    }  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiatable –](../../debugger/debug-interface-access/idiatable.md)   
 [Idiasegment –](../../debugger/debug-interface-access/idiasegment.md)