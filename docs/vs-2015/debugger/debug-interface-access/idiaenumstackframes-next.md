---
title: Idiaenumstackframes::Next – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumStackFrames::Next method
ms.assetid: 09378a21-d5e3-4213-b7e2-10f04d85295f
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1c66e8b281f27e13a1176dd32f21856367e5f1ac
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68189743"
---
# <a name="idiaenumstackframesnext"></a>IDiaEnumStackFrames::Next
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte zadaný počet prvků rámce zásobníku v pořadí výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Next(   
   ULONG             celt,  
   IDiaStackFrame**  rgelt,  
   ULONG*            pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 celt  
 [in] Počet prvků stackframe v enumerátor, který se má načíst.  
  
 rgelt  
 [out] Pole, které je pro vyplnění s požadovaným [idiastackframe –](../../debugger/debug-interface-access/idiastackframe.md) objekty.  
  
 pceltFetched  
 [out] Vrátí počet zásobníku rámce prvků načtených enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` Pokud nejsou žádné další rámce zásobníku. V opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumstackframes –](../../debugger/debug-interface-access/idiaenumstackframes.md)   
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
