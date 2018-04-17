---
title: Idiaframedata::get_type – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_type method
ms.assetid: efca38b5-c479-4d0a-a164-f903f25c5509
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d67c2331475afe63f4aa05da0f66886d2de7e486
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiaframedatagettype"></a>IDiaFrameData::get_type
Načte typ kompilátoru konkrétní rámce.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_type (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí hodnotu z [StackFrameTypeEnum – výčet](../../debugger/debug-interface-access/stackframetypeenum.md) výčet, který určuje typ kompilátoru konkrétní rámce.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. Jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md)   
 [StackFrameTypeEnum – výčet](../../debugger/debug-interface-access/stackframetypeenum.md)