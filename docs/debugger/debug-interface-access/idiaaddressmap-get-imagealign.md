---
title: "Idiaaddressmap::get_imagealign – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaAddressMap::get_imageAlign method
ms.assetid: f1ba8071-669c-4cf7-9ac0-02f26d99f366
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e3c9400fe8261b8983c76d59a55e7c457d35e572
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiaaddressmapgetimagealign"></a>IDiaAddressMap::get_imageAlign
Načte aktuální zarovnání obrázku.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_imageAlign (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí hodnotu zarovnání obrázku z spustitelný soubor.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Bitové kopie je zarovnán podle jak bitové kopie byl načteny a vytvořit hranice konkrétní paměti. Zarovnání je obvykle na hranicích 1, 2, 4, 8, 16, 32 nebo 64 bajtů. Zarovnání obrázku lze nastavit pomocí volání [idiaaddressmap::put_imagealign –](../../debugger/debug-interface-access/idiaaddressmap-put-imagealign.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [Idiaaddressmap –](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap::put_imagealign –](../../debugger/debug-interface-access/idiaaddressmap-put-imagealign.md)