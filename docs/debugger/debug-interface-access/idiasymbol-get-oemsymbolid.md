---
title: "Idiasymbol::get_oemsymbolid – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_oemSymbolId method
ms.assetid: 187801f0-bd82-4c5b-9fae-8eeb1a4ac0ce
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ef2581d357fe2b35ad80f4d2085b0f8f2dbb28cb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetoemsymbolid"></a>IDiaSymbol::get_oemSymbolId
Načte hodnotu ID symbol výrobce (OEM).  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_oemSymbolId (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí výrobce OEM interně přiřazené symbolů ID.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Identifikátor je jedinečný hodnota vytvořené DIA SDK k označení všechny symboly jako jedinečný.  
  
 Tato vlastnost se vztahuje pouze na symboly s [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) typ `SymTagCustomType`.  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)