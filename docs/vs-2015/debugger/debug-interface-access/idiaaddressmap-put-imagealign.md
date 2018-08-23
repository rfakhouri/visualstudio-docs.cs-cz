---
title: Idiaaddressmap::put_imagealign – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_imageAlign method
ms.assetid: f9ce875d-c263-43e5-a534-f34c37f9866f
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6743d2a39f2326b167da746fbb2da928c0b75aaf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667127"
---
# <a name="idiaaddressmapputimagealign"></a>IDiaAddressMap::put_imageAlign
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiaaddressmap::put_imagealign –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaaddressmap-put-imagealign).  
  
Nastaví zarovnání obrázku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT put_imageAlign (   
   DWORD NewVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 NewVal  
 [in] Nová hodnota zarovnání obrázku pro spustitelný soubor.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Bitové kopie (načíst spustitelné soubory) je zarovnán zadaná paměťová hranice. Toto uspořádání může mít vliv na aktuální architektura systému a možností v době kompilace a odkaz. Zarovnání obrázku je vždycky aktivní hranice. Platné jsou následující hodnoty zarovnání obrázku: 1, 2, 4, 8, 16, 32 a 64 bajtů hranice.  
  
 Aktuální zarovnání obrázku se dá načíst pomocí volání [idiaaddressmap::get_imagealign –](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md) metody.  
  
> [!NOTE]
>  Na obrázku je již načten v době, kdy tuto metodu lze volat. `put_imageAlign` Metoda se typicky používá při image byla přesunuta nebo změnit, a nové zarovnání je povinný.  
  
## <a name="see-also"></a>Viz také  
 [Idiaaddressmap –](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [IDiaAddressMap::get_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)



