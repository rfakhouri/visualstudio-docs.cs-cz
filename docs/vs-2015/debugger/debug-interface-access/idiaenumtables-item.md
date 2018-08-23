---
title: Idiaenumtables::Item – | Dokumentace Microsoftu
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
- IDiaEnumTables::Item method
ms.assetid: d65ab262-10c6-48ce-95a3-b5e4cb2c85af
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ea80cbcda60b54f17e79e492c43058579465ad90
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670759"
---
# <a name="idiaenumtablesitem"></a>IDiaEnumTables::Item
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiaenumtables::Item –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumtables-item).  
  
Načte index nebo název tabulky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Item (   
   VARIANT     index,  
   IDiaTable** table  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `index`  
 [in] Index nebo název [idiatable –](../../debugger/debug-interface-access/idiatable.md) se má načíst. Pokud varianta celé číslo se používá, musí být v rozsahu 0 až `count`-1, kde `count` je vrácená rozhraním [idiaenumtables::get_count –](../../debugger/debug-interface-access/idiaenumtables-get-count.md) metody.  
  
 `table`  
 [out] Vrátí [idiatable –](../../debugger/debug-interface-access/idiatable.md) objekt představující požadovanou tabulku.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud je zadán typ variant řetězec, řetězec názvy konkrétní tabulku. Název by měl být jeden z názvů tabulek definovaných v [konstanty (Debug Interface Access SDK)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md).  
  
## <a name="example"></a>Příklad  
  
```cpp#  
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



