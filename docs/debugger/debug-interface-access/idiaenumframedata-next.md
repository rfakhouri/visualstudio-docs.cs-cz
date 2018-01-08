---
title: "Idiaenumframedata::Next – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumFrameData::Next method
ms.assetid: 546e2e23-efb2-425a-96a1-808c67c519fb
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e5182cd0b6655792df168359e8d8df1121db387d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiaenumframedatanext"></a>IDiaEnumFrameData::Next
Načte zadaný počet elementů dat rámce v pořadí výčtu.  
  
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
 [v] Počet elementů rámce data v enumerátor mají být načteny.  
  
 rgelt  
 [out] Pole [idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md) objekty pro vyplnění rámce požadované datové prvky.  
  
 pceltFetched  
 [out] Vrátí počet datových elementů rámce v načtených enumerátor.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud neexistují žádné další záznamy. Jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumframedata –](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)