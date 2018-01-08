---
title: "Idiaenumsymbols::Skip – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumSymbols::Skip method
ms.assetid: e601fbc9-b10b-41c7-8180-959e57efabe8
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 23df339101ada3ad6f2d59311c38380d0cdfc201
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiaenumsymbolsskip"></a>IDiaEnumSymbols::Skip
Přeskočí zadaný počet symboly v posloupnosti výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Skip (   
   ULONG celt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 celt  
 [v] Počet symboly v pořadí výčtu tak, aby přeskočil.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` Pokud neexistují žádné další symboly tak, aby přeskočil.  
  
## <a name="see-also"></a>Viz také  
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)