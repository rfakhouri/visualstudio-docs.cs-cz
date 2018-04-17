---
title: IDiaSymbol::findSymbolsForAcceleratorPointerTag | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: fb66852c-c5f7-4140-b9fe-20cb4e51a9fe
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f0223b498a0187546b2e48f5049f9947ce6ac571
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolfindsymbolsforacceleratorpointertag"></a>IDiaSymbol::findSymbolsForAcceleratorPointerTag
Vrátí počet značek ukazatel akcelerátoru ve funkci se zakázaným inzerováním C++ AMP.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findSymbolsForAccleratorPointerTag (   
   DWORD             tagValue,  
   IDiaEnumSymbols** ppResult);  
```  
  
#### <a name="parameters"></a>Parametry  
 `tagValue`  
 [v] Hodnota značky ukazatele, pro které se nacházejí na pointee symbol záznamy.  
  
 `ppResult`  
 [out] Ukazatel na `IDiaEnumSymbols` ukazatel rozhraní, které se inicializuje výsledek.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)