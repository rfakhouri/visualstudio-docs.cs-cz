---
title: "Idiaenumtables::Next – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumTables::Next method
ms.assetid: 8d7bd359-d33e-4317-9674-d89283efd7de
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7d62394ae19d62ad5cdd58b95110442bf33cda8c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiaenumtablesnext"></a>IDiaEnumTables::Next
Načte zadaný počet tabulek v pořadí výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Next (   
   ULONG       celt,  
   IDiaTable** rgelt,  
   ULONG*      pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celt`  
 [v] Počet tabulek v enumerátor mají být načteny.  
  
 `rgelt`  
 [out] Pole, které se v pomocí [idiatable –](../../debugger/debug-interface-access/idiatable.md) objekty, které představují požadované tabulky.  
  
 `pceltFetched`  
 [out] Vrátí počet tabulek v načtených enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud nejsou žádné další tabulky. Jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumtables –](../../debugger/debug-interface-access/idiaenumtables.md)   
 [Idiatable –](../../debugger/debug-interface-access/idiatable.md)