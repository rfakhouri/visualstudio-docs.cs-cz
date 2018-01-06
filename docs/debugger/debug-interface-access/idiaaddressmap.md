---
title: "Idiaaddressmap – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaAddressMap interface
ms.assetid: e6467529-508c-4328-85d7-89444ae4d1c1
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6cdd8c9d2e581df3e7b0ebeba092a212fb7a89f5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiaaddressmap"></a>IDiaAddressMap
Umožňuje řídit způsob vypočítá DIA SDK virtuální a relativní virtuální adresy ladění objekty.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaAddressMap : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDiaAddressMap`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDiaAddressMap::get_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-addressmapenabled.md)|Určuje, zda bylo úspěšně navázáno adres mapují konkrétní relace.|  
|[IDiaAddressMap::put_addressMapEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)|Určuje, zda má být použita adres mapují k překladu adres symbol.|  
|[IDiaAddressMap::get_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled.md)|Určuje, zda je povoleno výpočet a použít relativní virtuálních adres.|  
|[IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)|Umožňuje klientovi k povolení nebo zakázání výpočtu relativní virtuální adresy.|  
|[IDiaAddressMap::get_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)|Načte aktuální zarovnání obrázku.|  
|[IDiaAddressMap::put_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-put-imagealign.md)|Nastaví zarovnání obrázku.|  
|[IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)|Nastaví obrázek hlavičky, chcete-li povolit překlad relativní virtuálních adres.|  
|[IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)|Poskytuje mapování adres pro podporu rozložení překlady bitovou kopii.|  
  
## <a name="remarks"></a>Poznámky  
 Ovládací prvek poskytované toto rozhraní je zapouzdřené v dvě sady dat zadáte: obrázek hlavičky a vyřešte mapy. Většina klienti používat [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metoda najít informace o správné ladění pro bitovou kopii a metodu, lze obvykle zjistit všechny potřebné hlavičky a mapy samotná data. Ale někteří klienti implementují specializované zpracování a hledání pro data. Tito klienti používat metody třídy `IDiaAddressMap` rozhraní zajistit DIA SDK ve výsledcích vyhledávání.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je k dispozici z objektu relace DIA. Volání klienta `QueryInterface` metoda DIA relace objekt rozhraní, obvykle [idiasession –](../../debugger/debug-interface-access/idiasession.md), načíst `IDiaAddressMap` rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)