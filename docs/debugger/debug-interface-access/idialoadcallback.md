---
title: Idialoadcallback – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback interface
ms.assetid: 2f18c64c-2cf0-43fc-a447-21e82702ca2a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5d7d13416b76b9271cff0f1271fddea5495e20f7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
|[IDiaLoadCallback::NotifyDebugDir](../../debugger/debug-interface-access/idialoadcallback-notifydebugdir.md)|Volá se při ladění adresář byl nalezen v souboru .exe.|  
|[IDiaLoadCallback::NotifyOpenDBG](../../debugger/debug-interface-access/idialoadcallback-notifyopendbg.md)|Volá se při otevřel soubor dbg candidate.|  
|[IDiaLoadCallback::NotifyOpenPDB](../../debugger/debug-interface-access/idialoadcallback-notifyopenpdb.md)|Volá se při otevřel soubor .pdb candidate.|  
|[IDiaLoadCallback::RestrictRegistryAccess](../../debugger/debug-interface-access/idialoadcallback-restrictregistryaccess.md)|Určuje, pokud registru dotazy slouží k vyhledání cesty pro hledání symbolů.|  
|[IDiaLoadCallback::RestrictSymbolServerAccess](../../debugger/debug-interface-access/idialoadcallback-restrictsymbolserveraccess.md)|Určuje, pokud je povolen přístup k serveru symbol přeložit symboly.|  
  
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
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)