---
title: Idiaenumsegments – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments interface
ms.assetid: 0c9edd5e-b9ce-43e1-a791-cd4c5d16d923
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 426d8dc998bfdf6859735e508595f9661b5c38d2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54939215"
---
# <a name="idiaenumsegments"></a>IDiaEnumSegments
Provede výčet různých segmentů obsažené ve zdroji dat.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaEnumSegments : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDiaEnumSegments`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDiaEnumSegments::get__NewEnum](../../debugger/debug-interface-access/idiaenumsegments-get-newenum.md)|Načte [rozhraní IEnumVARIANT](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-ienumvariant) verzi výčet.|  
|[IDiaEnumSegments::get_Count](../../debugger/debug-interface-access/idiaenumsegments-get-count.md)|Získá počet segmentů.|  
|[IDiaEnumSegments::Item](../../debugger/debug-interface-access/idiaenumsegments-item.md)|Segment, který načte prostřednictvím indexu.|  
|[IDiaEnumSegments::Next](../../debugger/debug-interface-access/idiaenumsegments-next.md)|Načte zadaný počet segmentů v pořadí výčtu.|  
|[IDiaEnumSegments::Skip](../../debugger/debug-interface-access/idiaenumsegments-skip.md)|Vynechá zadaný počet segmentů v sekvenci výčtu.|  
|[IDiaEnumSegments::Reset](../../debugger/debug-interface-access/idiaenumsegments-reset.md)|Návrat na začátek sekvence výčtu.|  
|[IDiaEnumSegments::Clone](../../debugger/debug-interface-access/idiaenumsegments-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Získat po zavolání tohoto rozhraní `QueryInterface` metodu [idiatable –](../../debugger/debug-interface-access/idiatable.md) objektu. Podívejte se na příklad podrobnosti.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak získat `IDiaEnumSections` rozhraní z tabulky. Úplný příklad použití segmenty, najdete v článku [idiasegment –](../../debugger/debug-interface-access/idiasegment.md) rozhraní.  
  
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
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiatable –](../../debugger/debug-interface-access/idiatable.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)