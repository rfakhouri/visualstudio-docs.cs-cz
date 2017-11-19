---
title: "Idiaenumsourcefiles – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumSourceFiles interface
ms.assetid: 5c0779a6-a2ea-408a-90da-ebdecf2b83c0
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dbcd3e50e1b53a56342b5ab344ec54180001fa80
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumsourcefiles"></a>IDiaEnumSourceFiles
Provede výčet různých zdrojové soubory obsažené v datovém zdroji.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaEnumSourceFiles : IUknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDiaEnumSourceFiles`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Idiaenumsourcefiles::get__newenum –](../../debugger/debug-interface-access/idiaenumsourcefiles-get-newenum.md)|Načte `IEnumVARIANT Interface` verzi této enumerátor.|  
|[Idiaenumsourcefiles::get_count –](../../debugger/debug-interface-access/idiaenumsourcefiles-get-count.md)|Načte počet zdrojové soubory.|  
|[Idiaenumsourcefiles::Item –](../../debugger/debug-interface-access/idiaenumsourcefiles-item.md)|Načte zdrojového souboru pomocí indexu.|  
|[Idiaenumsourcefiles::Next –](../../debugger/debug-interface-access/idiaenumsourcefiles-next.md)|Načte zadaný počet zdrojové soubory v pořadí výčtu.|  
|[Idiaenumsourcefiles::Skip –](../../debugger/debug-interface-access/idiaenumsourcefiles-skip.md)|Přeskočí zadaný počet zdrojové soubory v posloupnosti výčtu.|  
|[Idiaenumsourcefiles::Reset –](../../debugger/debug-interface-access/idiaenumsourcefiles-reset.md)|Návrat na začátek v sekvenci výčtu.|  
|[Idiaenumsourcefiles::clone –](../../debugger/debug-interface-access/idiaenumsourcefiles-clone.md)|Vytvoří enumerátor, který obsahuje stav výčtu jako aktuální enumerátor.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Získat toto rozhraní vyvoláním `QueryInterface` metodu [idiatable –](../../debugger/debug-interface-access/idiatable.md) objektu. Podívejte se na příklad podrobnosti.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak získat `IDiaEnumSourceFiles` rozhraní ze seznamu tabulek do objektu session DIA. Příklad přístup k informacím o zdrojového souboru, najdete v článku [idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md) rozhraní.  
  
```C++  
  
IDiaEnumSourceFiles* GetEnumSourceFiless(IDiaSession *pSession)  
{  
    IDiaEnumSourceFiles * pUnknown    = NULL;  
    REFIID                iid         = __uuidof(IDiaEnumSourceFiles);  
    IDiaEnumTables*       pEnumTables = NULL;  
    IDiaTable*            pTable      = NULL;  
    ULONG                 celt        = 0;  
  
    if (pSession->getEnumTables(&pEnumTables) != S_OK)  
    {  
        wprintf(L"ERROR - GetTable() getEnumTables\n");  
        return NULL;  
    }  
    while (pEnumTables->Next(1, &pTable, &celt) == S_OK && celt == 1)  
    {  
        // There is only one table that matches the given iid  
        HRESULT hr = pTable->QueryInterface(iid, (void**)&pUnknown);  
        pTable->Release();  
        if (hr == S_OK)  
        {  
            break;  
        }  
    }  
    pEnumTables->Release();  
    return pUnknown;  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiasession::FindFile –](../../debugger/debug-interface-access/idiasession-findfile.md)   
 [Idiasession::findlinesbylinenum –](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)   
 [Idiatable –](../../debugger/debug-interface-access/idiatable.md)