---
title: "Idialoadcallback – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaLoadCallback interface
ms.assetid: 2f18c64c-2cf0-43fc-a447-21e82702ca2a
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7dc5034967fe94b8be6503a9c86f7b6bc6ee14ed
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idialoadcallback"></a>IDiaLoadCallback
Zpětná volání obdrží z symbol DIA postup vyhledání, čímž umožní uživatelské rozhraní hlásit průběh pokus o umístění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaLoadCallback : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Toto rozhraní se zveřejňují následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Idialoadcallback::notifydebugdir –](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md)|Volá se při ladění adresář byl nalezen v souboru .exe.|  
|[Idialoadcallback::notifyopendbg –](../../debugger/debug-interface-access/idialoadcallback-notifyopendbg.md)|Volá se při otevřel soubor dbg candidate.|  
|[Idialoadcallback::notifyopenpdb –](../../debugger/debug-interface-access/idialoadcallback-notifyopenpdb.md)|Volá se při otevřel soubor .pdb candidate.|  
|[Idialoadcallback::restrictregistryaccess –](../../debugger/debug-interface-access/idialoadcallback-restrictregistryaccess.md)|Určuje, pokud registru dotazy slouží k vyhledání cesty pro hledání symbolů.|  
|[Idialoadcallback::restrictsymbolserveraccess –](../../debugger/debug-interface-access/idialoadcallback-restrictsymbolserveraccess.md)|Určuje, pokud je povolen přístup k serveru symbol přeložit symboly.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní implementuje klientskou aplikaci a poskytuje odkaz na jeho ve volání [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metoda.  
  
 Další omezení, které můžete ukládat, proces načítání, najdete v článku [idialoadcallback2 –](../../debugger/debug-interface-access/idialoadcallback2.md) rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)   
 [Idiareadexeatoffsetcallback –](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [Idiareadexeatrvacallback –](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)   
 [Idialoadcallback2 –](../../debugger/debug-interface-access/idialoadcallback2.md)