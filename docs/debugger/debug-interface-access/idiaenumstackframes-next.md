---
title: "Idiaenumstackframes::Next – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumStackFrames::Next method
ms.assetid: 09378a21-d5e3-4213-b7e2-10f04d85295f
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8bfdf9e71bfb13c9f8cc730a33ecb2813e117e5e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiaenumstackframesnext"></a>IDiaEnumStackFrames::Next
Načte zadaný počet elementů rámce zásobníku z pořadí výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Next(   
   ULONG             celt,  
   IDiaStackFrame**  rgelt,  
   ULONG*            pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 celt  
 [v] Počet elementů stackframe v enumerátor mají být načteny.  
  
 rgelt  
 [out] Pole, které má být vyplněna s požadovaným [idiastackframe –](../../debugger/debug-interface-access/idiastackframe.md) objekty.  
  
 pceltFetched  
 [out] Vrátí počet zásobníku elementy rámce v načtených enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud nejsou žádné další rámce zásobníku. Jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumstackframes –](../../debugger/debug-interface-access/idiaenumstackframes.md)   
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)