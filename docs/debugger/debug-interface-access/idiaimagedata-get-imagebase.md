---
title: IDiaImageData::get_imageBase | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaImageData::get_imageBase method
ms.assetid: 4ba3d9e4-b205-4ee6-a41d-6996972f1f85
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 238eb138f7e7452e942047d776411d973a689c2a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54931437"
---
# <a name="idiaimagedatagetimagebase"></a>IDiaImageData::get_imageBase
Získá umístění v paměti, kde by měla být založena na obrázku.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_imageBase (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí image navrhované základní hodnoty.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Kvůli konfliktům základní image image může přenese se změnami automaticky do umístění nevyužité paměti při spuštění. Tato metoda vrátí základní pomocný parametr (umístění v paměti navrhované), která byla uložená v modulu v době kompilace.  
  
## <a name="see-also"></a>Viz také  
 [IDiaImageData](../../debugger/debug-interface-access/idiaimagedata.md)