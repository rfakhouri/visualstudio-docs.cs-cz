---
title: Idiaenumsourcefiles::Next – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSourceFiles::Next method
ms.assetid: 83bf6317-ff39-4c5c-8987-cba34e7a6983
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 385bbf99e8f1d4bcc3e60ffb8beaa506f37164c4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628196"
---
# <a name="idiaenumsourcefilesnext"></a>IDiaEnumSourceFiles::Next
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiaenumsourcefiles::Next –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumsourcefiles-next).  
  
Načte zadaný počet zdrojových souborů v pořadí výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Next (   
   ULONG            celt,  
   IDiaSourceFile** rgelt,  
   ULONG*           pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 celt  
 [in] Počet zdrojových souborů v enumerátor, který se má načíst.  
  
 rgelt  
 [out] Pole, které je v tankujeme [idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md) objekty, které představují požadované zdrojové soubory.  
  
 pceltFetched  
 [out] Vrátí počet zdrojových souborů načtených enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` Pokud nejsou žádné další zdrojové soubory. V opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumsourcefiles –](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [Idiasession::findlinesbylinenum –](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)



