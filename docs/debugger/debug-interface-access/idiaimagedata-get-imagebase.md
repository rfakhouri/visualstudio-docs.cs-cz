---
title: "Idiaimagedata::get_imagebase – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaImageData::get_imageBase method
ms.assetid: 4ba3d9e4-b205-4ee6-a41d-6996972f1f85
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: daaaf26e0a33ce8e90b2b8ac621ed47d299c8276
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [Idiaimagedata –](../../debugger/debug-interface-access/idiaimagedata.md)