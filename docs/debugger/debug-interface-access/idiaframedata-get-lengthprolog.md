---
title: "Idiaframedata::get_lengthprolog – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaFrameData::get_lengthProlog method
ms.assetid: 5f042ff1-e74e-430a-be34-d2cf1b18eff2
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bcf3e7feada0ba35e9001ed7b3f17167cdb4de7a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiaframedatagetlengthprolog"></a>IDiaFrameData::get_lengthProlog
Získá počet bajtů kódu prologu v bloku.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_lengthProlog (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí počet bajtů kódu prologu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Kód prologu je pořadí pokyny, který zachovává registrů, nastaví stav procesoru a vytvoří v zásobníku pro funkci.  
  
## <a name="see-also"></a>Viz také  
 [Idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md)