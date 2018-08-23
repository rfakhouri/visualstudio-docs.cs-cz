---
title: Idiaenumframedata::Next – | Dokumentace Microsoftu
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
- IDiaEnumFrameData::Next method
ms.assetid: 546e2e23-efb2-425a-96a1-808c67c519fb
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 37e9d695c70a3b69357f9d40315ed2359a52fc2f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629676"
---
# <a name="idiaenumframedatanext"></a>IDiaEnumFrameData::Next
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiaenumframedata::Next –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumframedata-next).  
  
Načte zadaný počet snímků datové prvky v pořadí výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Next (   
   ULONG           celt,   
   IDiaFrameData** rgelt,  
   ULONG*          pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 celt  
 [in] Počet datových elementů rámce v enumerátor, který se má načíst.  
  
 rgelt  
 [out] Pole [idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md) objekty vyplní rámce požadované datové prvky.  
  
 pceltFetched  
 [out] Vrátí počet prvků rámce dat načtených enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` Pokud neexistují žádné další záznamy. V opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumframedata –](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)



