---
title: IDiaStackWalkHelper | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackWalkHelper2 interface
ms.assetid: d66e5c84-565d-494e-8486-f91db9a34548
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6cbd88bbe3e8a752721047ee80d847e72cf115b9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiastackwalkhelper"></a>IDiaStackWalkHelper
Usnadňuje procházení zásobníku pomocí souboru databáze (.pdb) ladicí program.  
  
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
|[IDiaStackWalkHelper::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddress.md)|Vyhledá zadaný zásobníku pro nejbližší funkce zpáteční adresu.|  
|[IDiaStackWalkHelper::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkhelper-searchforreturnaddressstart.md)|Vyhledá zadaný zásobníku pro zpáteční adresu nebo blízko adresu zadaným zásobníkem.|  
|[IDiaStackWalkHelper::frameForVA](../../debugger/debug-interface-access/idiastackwalkhelper-frameforva.md)|Načte rámce zásobníku, která obsahuje zadanou virtuální adresu.|  
|[IDiaStackWalkHelper::symbolForVA](../../debugger/debug-interface-access/idiastackwalkhelper-symbolforva.md)|Načte symbol, který obsahuje zadanou virtuální adresu. **Poznámka:** Symbol musí mít typ `SymTagFunctionType` (hodnoty z [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) výčet).|  
|[IDiaStackWalkHelper::pdataForVA](../../debugger/debug-interface-access/idiastackwalkhelper-pdataforva.md)|Vrátí související se zadanou virtuální adresu PDATA datového bloku.|  
|[IDiaStackWalkHelper::imageForVA](../../debugger/debug-interface-access/idiastackwalkhelper-imageforva.md)|Načte výchozí virtuální adresy spustitelný soubor, zadané virtuální adresy někde v paměti ke spustitelnému souboru.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní je volána službou kód DIA ke získání informací o spustitelného souboru vytvořit seznam rámce zásobníku při spuštění programu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Klientská aplikace implementuje toto rozhraní pro podporu procházení zásobníku při spuštění programu. Instance toto rozhraní je předána [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md) nebo [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md)   
 [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)   
 [IDiaStackWalker::getEnumFrames2](../../debugger/debug-interface-access/idiastackwalker-getenumframes2.md)