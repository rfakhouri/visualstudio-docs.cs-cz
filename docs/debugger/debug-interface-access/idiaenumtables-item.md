---
title: Idiaenumtables::Item – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::Item method
ms.assetid: d65ab262-10c6-48ce-95a3-b5e4cb2c85af
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 68a9dbba4226e0fa4f591bfc48b03add62ad75b3
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumtablesitem"></a>IDiaEnumTables::Item
Načte tabulku index nebo název.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Item (   
   VARIANT     index,  
   IDiaTable** table  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `index`  
 [v] Index nebo název [idiatable –](../../debugger/debug-interface-access/idiatable.md) mají být načteny. Pokud se používá typu variant celé číslo, musí být v rozsahu od 0 do `count`-1, kde `count` jako vrácený [idiaenumtables::get_count –](../../debugger/debug-interface-access/idiaenumtables-get-count.md) metoda.  
  
 `table`  
 [out] Vrátí [idiatable –](../../debugger/debug-interface-access/idiatable.md) objekt reprezentující požadovanou tabulku.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud je zadán hodnotu typu variant řetězec, řetězec názvy konkrétní tabulky. Název musí být jeden z tabulky názvů definované v [konstanty (ladění Interface Access SDK)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md).  
  
## <a name="example"></a>Příklad  
  
```C++  
VARIANT var;  
var.vt = VT_BSTR;  
var.bstrVal = SysAllocString(DiaTable_Symbols );  
IDiaTable* pTable;  
pEnumTables->Item( var, &pTable );  
```  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumtables –](../../debugger/debug-interface-access/idiaenumtables.md)   
 [Idiatable –](../../debugger/debug-interface-access/idiatable.md)   
 [Idiaenumtables::get_count –](../../debugger/debug-interface-access/idiaenumtables-get-count.md)   
 [Konstanty (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md)