---
title: Idiaenuminjectedsources::Next – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumInjectedSources::Next method
ms.assetid: 38af80fc-748f-4b15-bff1-823db21dd4d0
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d40ed9acf9e8c82fa315517c0abc3eb6f6d3b036
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62580502"
---
# <a name="idiaenuminjectedsourcesnext"></a>IDiaEnumInjectedSources::Next
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte zadaný počet vloženého zdroje v pořadí výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Next (   
   ULONG                celt,   
   IDiaInjectedSource** rgelt,  
   ULONG*               pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 celt  
 [in] Počet vloženého zdroje v enumerátor, který se má načíst.  
  
 rgelt  
 [out] Vrátí pole [idiainjectedsource –](../../debugger/debug-interface-access/idiainjectedsource.md) objekty, které představuje požadované vloženého zdroje.  
  
 pceltFetched  
 [out] Vrátí počet vloženého zdroje v načtených enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` Pokud neexistují žádné další vloženého zdroje. V opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenuminjectedsources –](../../debugger/debug-interface-access/idiaenuminjectedsources.md)   
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)
