---
title: Idiaframedata::get_lengthlocals – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_lengthLocals method
ms.assetid: 51fe15c3-4cd6-4a06-8a41-a56502209762
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: da9c50b6c63176fdb3156b2daa15d6c0e1bbefbb
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54754101"
---
# <a name="idiaframedatagetlengthlocals"></a>IDiaFrameData::get_lengthLocals
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Získá počet bajtů lokálních proměnných posunuto v zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_lengthLocals (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí počet bajtů místních proměnných.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Hodnota vrácená touto metodou se obvykle používá při interpretaci řetězec programu (najdete v článku [idiaframedata::get_program –](../../debugger/debug-interface-access/idiaframedata-get-program.md) metodu pro definici řetězce program).  
  
## <a name="see-also"></a>Viz také  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaFrameData::get_program](../../debugger/debug-interface-access/idiaframedata-get-program.md)
