---
title: Idiaimagedata::get_imagebase – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaImageData::get_imageBase method
ms.assetid: 4ba3d9e4-b205-4ee6-a41d-6996972f1f85
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 032ff3cee51c3c8295395aba6e9e60bfa4e9a400
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiaimagedatagetimagebase"></a>IDiaImageData::get_imageBase
Načte paměti umístění, kde by měla být založena bitovou kopii.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_imageBase (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí hodnotu základní navrhované bitové kopie.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Kvůli konfliktům základní bitovou kopii může být obrázek automaticky rebased do umístění nevyužitou paměť po načtení. Tato metoda vrátí základní nápovědu (umístění navrhované paměti), která byla uložena v modulu v době kompilace.  
  
## <a name="see-also"></a>Viz také  
 [IDiaImageData](../../debugger/debug-interface-access/idiaimagedata.md)