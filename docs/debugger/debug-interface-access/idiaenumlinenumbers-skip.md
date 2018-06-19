---
title: Idiaenumlinenumbers::Skip – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumLineNumbers::Skip method
ms.assetid: d182c269-8c76-4d8b-8275-c6807c5ae4e1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ebaa7366128a02b9ac0af253c418650a747b657e
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31456699"
---
# <a name="idiaenumlinenumbersskip"></a>IDiaEnumLineNumbers::Skip
Přeskočí zadaný počet čísla řádků v posloupnosti výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Skip (   
   ULONG celt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 celt  
 [v] Počet čísla řádků v pořadí výčtu tak, aby přeskočil.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` Pokud nejsou žádné další čísla řádků tak, aby přeskočil.  
  
## <a name="see-also"></a>Viz také  
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)