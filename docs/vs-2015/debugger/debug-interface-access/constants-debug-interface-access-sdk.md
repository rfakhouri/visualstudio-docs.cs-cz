---
title: Konstanty (přístup k rozhraní SDK ladění) | Dokumentace Microsoftu
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
- constants, DIA SDK
- DIA SDK, constants
ms.assetid: aca4ec77-bc08-4cdd-a6ce-8d4a28ea5ea3
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ff1b473f7e5fdddbb1706d54e44692df3a6022e2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666972"
---
# <a name="constants-debug-interface-access-sdk"></a>Konstanty (Přístup k rozhraní ladění SDK)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [konstanty (Debug Interface Access SDK)](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/constants-debug-interface-access-sdk).  
  
Tyto řetězcové konstanty lze použít k identifikaci různých oddílů sady soubor databáze (PDB) programu ladění prostřednictvím sady DIA SDK.  
  
## <a name="constants"></a>Konstanty  
 Následující jsou deklarovány jako makra jazyka C/C++.  
  
|– Makro|Hodnota|  
|-----------|-----------|  
|`DiaTable_Symbols`|L "Symboly"|  
|`DiaTable_Sections`|L "Části"|  
|`DiaTable_SrcFiles`|L "SourceFiles"|  
|`DiaTable_LineNums`|L "LineNumbers"|  
|`DiaTable_SegMap`|L "SegmentMap"|  
|`DiaTable_Dbg`|L "Dbg"|  
|`DiaTable_InjSrc`|L "InjectedSource"|  
|`DiaTable_FrameData`|L "FrameData"|  
  
## <a name="example"></a>Příklad  
 Tady je příklad pomocí jedné z těchto symbolů:  
  
```cpp#  
HRESULT GetSymbolTable(IDiaEnumTables *pEnumTables, IDiaTable **pTable)  
{  
    HRESULT hr;  
    VARIANT var;  
    var.vt      = VT_BSTR;  
    var.bstrVal = SysAllocString( DiaTable_Symbols );  
    hr = pEnumTables->Item( var, pTable );  
    return(hr);  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: dia2.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)   
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Rozhraní (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)



