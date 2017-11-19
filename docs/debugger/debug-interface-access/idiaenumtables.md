---
title: "Idiaenumtables – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumTables interface
ms.assetid: 016190c5-09e4-48f2-bf60-9b02603a03e0
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 913fdcefc4e90ea09030e416cb6a300e50855478
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumtables"></a>IDiaEnumTables
Provede výčet různých tabulky obsažené v datovém zdroji.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaEnumTables : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDiaEnumTables`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Idiaenumtables::get__newenum –](../../debugger/debug-interface-access/idiaenumtables-get-newenum.md)|Načte [IEnumVARIANT rozhraní](http://msdn.microsoft.com/en-us/139e3c93-faef-4003-9079-e0e94494db3e) verzi této enumerátor.|  
|[Idiaenumtables::get_count –](../../debugger/debug-interface-access/idiaenumtables-get-count.md)|Načte počet tabulek.|  
|[Idiaenumtables::Item –](../../debugger/debug-interface-access/idiaenumtables-item.md)|Načte tabulku prostřednictvím index nebo název.|  
|[Idiaenumtables::Next –](../../debugger/debug-interface-access/idiaenumtables-next.md)|Načte zadaný počet tabulek v pořadí výčtu.|  
|[Idiaenumtables::Skip –](../../debugger/debug-interface-access/idiaenumtables-skip.md)|Přeskočí zadaný počet tabulek v posloupnosti výčtu.|  
|[Idiaenumtables::Reset –](../../debugger/debug-interface-access/idiaenumtables-reset.md)|Návrat na začátek v sekvenci výčtu.|  
|[Idiaenumtables::clone –](../../debugger/debug-interface-access/idiaenumtables-clone.md)|Vytvoří enumerátor, který obsahuje stav výčtu jako aktuální enumerátor.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Získat voláním toto rozhraní [idiasession::getenumtables –](../../debugger/debug-interface-access/idiasession-getenumtables.md) metoda.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak získat `IDiaEnumTables` rozhraní z relace. Více kompletní příklad, jak pomocí tabulky, najdete v článku [idiatable –](../../debugger/debug-interface-access/idiatable.md) rozhraní.  
  
```C++  
void ShowTableNames(IDiaSession *pSession)  
{  
    CComPtr<IDiaEnumTables> pTables;  
    if ( FAILED( psession->getEnumTables( &pTables ) ) )  
    {  
        Fatal( "getEnumTables" );  
    }  
    // Do something with table  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiasession::getenumtables –](../../debugger/debug-interface-access/idiasession-getenumtables.md)