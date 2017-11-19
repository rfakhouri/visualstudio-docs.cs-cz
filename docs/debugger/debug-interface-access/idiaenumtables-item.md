---
title: "Idiaenumtables::Item – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumTables::Item method
ms.assetid: d65ab262-10c6-48ce-95a3-b5e4cb2c85af
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 26acf7b8f9ad54a1ef1ed25497cd408c51c745c5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [Konstanty (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md)