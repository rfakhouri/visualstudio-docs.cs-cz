---
title: IDiaStackWalkHelper | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2 interface
ms.assetid: d66e5c84-565d-494e-8486-f91db9a34548
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 315af434271d57a8547963f2538ff1b799ef4fd3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68150026"
---
# <a name="idiastackwalkhelper"></a>IDiaStackWalkHelper
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Usnadňuje procházení zásobníku pomocí programového souboru databáze (PDB) ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
IDiaStackWalkHelper: IUnknown  
  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce VTable pořadí  
 Následující tabulka uvádí metody `IDiaStackWalkHelper`:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDiaStackWalkHelper::get_registerValue](../../debugger/debug-interface-access/idiastackwalkhelper-get-registervalue.md)|Načte hodnotu registru.|  
|[IDiaStackWalkHelper::put_registerValue](../../debugger/debug-interface-access/idiastackwalkhelper-put-registervalue.md)|Nastaví hodnotu registru.|  
|[IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)|Čte blok dat z ke spustitelnému souboru bitové kopie v paměti.|  
|[IDiaStackWalkHelper::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddress.md)|Vyhledá zadaný zásobník snímků pro nejbližší zpáteční adresu funkce.|  
|[IDiaStackWalkHelper::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddressstart.md)|Vyhledá zadaný zásobník snímků pro zpáteční adresu na nebo blízko ní adresu určeném zásobníku.|  
|[IDiaStackWalkHelper::frameForVA](../../debugger/debug-interface-access/idiastackwalkhelper-frameforva.md)|Obnoví rámec zásobníku, který obsahuje zadanou virtuální adresu.|  
|[IDiaStackWalkHelper::symbolForVA](../../debugger/debug-interface-access/idiastackwalkhelper-symbolforva.md)|Načte symbol, který obsahuje zadanou virtuální adresu. **Poznámka:**  Symbol, musí být typu `SymTagFunctionType` (hodnoty z [symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md) výčet).|  
|[IDiaStackWalkHelper::pdataForVA](../../debugger/debug-interface-access/idiastackwalkhelper-pdataforva.md)|Vrátí související se zadanou virtuální adresu PDATA datového bloku.|  
|[IDiaStackWalkHelper::imageForVA](../../debugger/debug-interface-access/idiastackwalkhelper-imageforva.md)|Načte výchozí virtuální adresy spustitelného souboru, zadaný virtuální adresu někde v paměti ke spustitelnému souboru.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní je volán kód DIA k získání informací o spustitelný soubor pro vytvoření seznamu bloků zásobníku při provádění programu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Klientská aplikace implementuje toto rozhraní pro podporu procházení zásobníku během provádění programu. Instance toto rozhraní je předán [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md) nebo [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: dia2.h  
  
 Knihovna: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [Symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)   
 [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)
