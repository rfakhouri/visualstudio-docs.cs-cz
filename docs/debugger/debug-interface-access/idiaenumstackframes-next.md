---
title: Idiaenumstackframes::Next – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumStackFrames::Next method
ms.assetid: 09378a21-d5e3-4213-b7e2-10f04d85295f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 68e84c31cb98cdbbe69e62aa1e572386100277a0
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31458704"
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