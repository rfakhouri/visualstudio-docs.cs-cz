---
title: Idiaenumframedata::Next – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::Next method
ms.assetid: 546e2e23-efb2-425a-96a1-808c67c519fb
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e7905a9226d120c14a4b9e6472e14714167c1b09
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54949386"
---
# <a name="idiaenumframedatanext"></a>IDiaEnumFrameData::Next
Načte zadaný počet snímků datové prvky v pořadí výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
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
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)