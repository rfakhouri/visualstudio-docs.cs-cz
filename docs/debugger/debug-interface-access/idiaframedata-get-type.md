---
title: Idiaframedata::get_type – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: 5b95262fb5cc9afce25e9f4120b981543939e5be
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31460437"
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