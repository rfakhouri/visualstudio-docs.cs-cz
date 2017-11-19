---
title: "Idiaenumlinenumbers – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumLineNumbers interface
ms.assetid: cdf07b4f-19e4-4dcd-8af8-c2dbca586a7c
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 92d257749e12605fb02c4c25a57b1862880d9a5c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumlinenumbers"></a>IDiaEnumLineNumbers
Provede výčet různých čísla řádků, které jsou obsažené v datovém zdroji.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaEnumLineNumbers : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDiaEnumLineNumbers`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Idiaenumlinenumbers::get__newenum –](../../debugger/debug-interface-access/idiaenumlinenumbers-get-newenum.md)|Načte [IEnumVARIANT rozhraní](http://msdn.microsoft.com/en-us/139e3c93-faef-4003-9079-e0e94494db3e) verzi této enumerátor.|  
|[Idiaenumlinenumbers::get_count –](../../debugger/debug-interface-access/idiaenumlinenumbers-get-count.md)|Načte počet čísla řádků.|  
|[Idiaenumlinenumbers::Item –](../../debugger/debug-interface-access/idiaenumlinenumbers-item.md)|Načte číslo řádku prostřednictvím indexu.|  
|[Idiaenumlinenumbers::Next –](../../debugger/debug-interface-access/idiaenumlinenumbers-next.md)|Načte zadaný počet čísla řádků v pořadí výčtu.|  
|[Idiaenumlinenumbers::Skip –](../../debugger/debug-interface-access/idiaenumlinenumbers-skip.md)|Přeskočí zadaný počet čísla řádků v posloupnosti výčtu.|  
|[Idiaenumlinenumbers::Reset –](../../debugger/debug-interface-access/idiaenumlinenumbers-reset.md)|Návrat na začátek v sekvenci výčtu.|  
|[Idiaenumlinenumbers::clone –](../../debugger/debug-interface-access/idiaenumlinenumbers-clone.md)|Vytvoří enumerátor, který obsahuje stav výčtu jako aktuální enumerátor.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní se získá voláním jednu z následujících metod v [idiasession –](../../debugger/debug-interface-access/idiasession.md) rozhraní:  
  
-   [Idiasession::findlines –](../../debugger/debug-interface-access/idiasession-findlines.md)  
  
-   [Idiasession::findlinesbyaddr –](../../debugger/debug-interface-access/idiasession-findlinesbyaddr.md)  
  
-   [Idiasession::findlinesbyrva –](../../debugger/debug-interface-access/idiasession-findlinesbyrva.md)  
  
-   [Idiasession::findlinesbyva –](../../debugger/debug-interface-access/idiasession-findlinesbyva.md)  
  
-   [Idiasession::findlinesbylinenum –](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak získat `IDiaEnumLineNumbers` rozhraní z relace. V takovém případě příklad ukazuje, jak získat řádek číslo výčtu pro funkci (reprezentována `pSymbol`). Více kompletní příklad, jak pomocí čísla řádků, najdete v článku [idialinenumber –](../../debugger/debug-interface-access/idialinenumber.md) rozhraní.  
  
```C++  
void dumpFunctionLines( IDiaSymbol* pSymbol, IDiaSession* pSession )  
{  
    ULONGLONG length = 0;  
    DWORD isect = 0;  
    DWORD offset = 0;  
    pSymbol->get_addressSection( &isect );  
    pSymbol->get_addressOffset( &offset );  
    pSymbol->get_length( &length );  
    if ( isect != 0 && length > 0 )  
    {  
        CComPtr< IDiaEnumLineNumbers > pLines;  
        if ( SUCCEEDED( pSession->findLinesByAddr(  
                                      isect,  
                                      offset,  
                                      static_cast<DWORD>( length ),  
                                      &pLines )  
                      )  
           )  
        {  
            // Do something with the enumeration  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasession::findlinesbylinenum –](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)   
 [Idiasession::findlinesbyrva –](../../debugger/debug-interface-access/idiasession-findlinesbyrva.md)   
 [Idiasession::findlinesbyva –](../../debugger/debug-interface-access/idiasession-findlinesbyva.md)   
 [Idiasession::findlines –](../../debugger/debug-interface-access/idiasession-findlines.md)   
 [Idiasession::findlinesbyaddr –](../../debugger/debug-interface-access/idiasession-findlinesbyaddr.md)