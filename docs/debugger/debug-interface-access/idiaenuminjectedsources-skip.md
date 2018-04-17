---
title: Idiaenuminjectedsources::Skip – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumInjectedSources::Skip method
ms.assetid: 4aad6a51-f2d3-4064-b216-60d830d0a560
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b1057aa0a52249f85f57daa39409b7c6fd82e2bf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiaenuminjectedsourcesskip"></a>IDiaEnumInjectedSources::Skip
Přeskočí zadaný počet vloženého zdroje v posloupnosti výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Skip (   
   ULONG celt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 celt  
 [v] Počet vloženého zdroje v pořadí výčtu tak, aby přeskočil.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` Pokud neexistují žádné další vloženého zdroje tak, aby přeskočil.  
  
## <a name="see-also"></a>Viz také  
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)