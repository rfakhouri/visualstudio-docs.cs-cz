---
title: Idiastackwalkframe – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame interface
ms.assetid: 42d82845-d6f6-4846-9ecd-9dd169216077
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c525d2c19f3bc4ab7ea540ac129931583064db01
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628229"
---
# <a name="idiastackwalkframe"></a>IDiaStackWalkFrame
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiastackwalkframe –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackwalkframe).  
  
Zásobník kontextu mezi voláními udržuje [idiaframedata::Execute –](../../debugger/debug-interface-access/idiaframedata-execute.md) metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaStackWalkFrame : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDiaStackWalkFrame`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDiaStackWalkFrame::get_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-get-registervalue.md)|Načte hodnotu registru.|  
|[IDiaStackWalkFrame::put_registerValue](../../debugger/debug-interface-access/idiastackwalkframe-put-registervalue.md)|Nastaví hodnotu registru.|  
|[IDiaStackWalkFrame::readMemory](../../debugger/debug-interface-access/idiastackwalkframe-readmemory.md)|Přečte paměti z image.|  
|[IDiaStackWalkFrame::searchForReturnAddress](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddress.md)|Vyhledá zadaný zásobník snímků pro nejbližší zpáteční adresu funkce.|  
|[IDiaStackWalkFrame::searchForReturnAddressStart](../../debugger/debug-interface-access/idiastackwalkframe-searchforreturnaddressstart.md)|Vyhledá zadaný zásobník snímků pro zpáteční adresu na nebo blízko ní zadané adrese.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní se používá při provádění programu pro čtení a zápis registry také přístup k paměti a najít návratový adresy.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Klientská aplikace implementuje toto rozhraní a předá instance rozhraní [idiaframedata::Execute –](../../debugger/debug-interface-access/idiaframedata-execute.md) metody. Stejnou instanci toto rozhraní je používán znovu a znovu pro zachování stavu registrů při každé vyvolání sady `execute` metody. `execute` Metody tohoto rozhraní používá rovněž k určení zpáteční adresu.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaFrameData::execute](../../debugger/debug-interface-access/idiaframedata-execute.md)



