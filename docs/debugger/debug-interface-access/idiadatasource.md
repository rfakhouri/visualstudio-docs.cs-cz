---
title: "Idiadatasource – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaDataSource interface
ms.assetid: 6260ac76-4f9d-4144-ba22-32f8620b32c2
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9b6ddb2ba2cc568b8f07e6643dcaeb93c0dec8ff
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiadatasource"></a>IDiaDataSource
Iniciuje přístup k zdroj symboly ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaDataSource : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDiaDataSource`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Idiadatasource::get_lasterror –](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md)|Načte název souboru pro poslední chyba zatížení.|  
|[Idiadatasource::loaddatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)|Otevře a připraví soubor programu databáze (.pdb) jako zdroj dat ladění.|  
|[Idiadatasource::loadandvalidatedatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)|Otevře a ověřuje, že soubor databáze (.pdb) programu shoduje podpis informací; připraví soubor .pdb jako zdroj dat ladění.|  
|[Idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)|Otevře a připraví ladění data související s.exe/.dll souboru.|  
|[Idiadatasource::loaddatafromistream –](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)|Připraví ladění data uložená v souboru databáze (.pdb) program přistupovat prostřednictvím v paměti datového proudu.|  
|[Idiadatasource::opensession –](../../debugger/debug-interface-access/idiadatasource-opensession.md)|Otevře relaci pro dotazování symboly.|  
  
## <a name="remarks"></a>Poznámky  
 Volání na jednu z metod zatížení `IDiaDataSource` rozhraní otevře zdroji symbol. Úspěšné volání [idiadatasource::opensession –](../../debugger/debug-interface-access/idiadatasource-opensession.md) metoda vrátí [idiasession –](../../debugger/debug-interface-access/idiasession.md) rozhraní, které podporuje dotazování na zdroj dat. Pokud metoda load vrátí chybu související soubor potom [idiadatasource::get_lasterror –](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md) metoda vrátí hodnotu obsahuje název souboru, který je přidružený k chybě.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní se získá voláním `CoCreateInstance` funkce s identifikátorem třídy `CLSID_DiaSource` a ID rozhraní `IID_IDiaDataSource`. Příklad ukazuje, jak získat toto rozhraní.  
  
## <a name="example"></a>Příklad  
  
```C++  
  
      IDiaDataSource* pSource;  
HRESULT hr = CoCreateInstance(CLSID_DiaSource,  
                              NULL,  
                              CLSCTX_INPROC_SERVER,  
                              IID_IDiaDataSource,  
                              (void**) &pSource);  
if (FAILED(hr))  
{  
    // Report error and exit  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)