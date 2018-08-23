---
title: Idiaaddressmap::get_relativevirtualaddressenabled – | Dokumentace Microsoftu
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
- IDiaAddressMap::get_relativeVirtualAddressEnabled method
ms.assetid: 4c48af81-7148-4d9a-818e-dbe62cbfc638
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d64f41285c0114d78df4035d11a6d92c714717bd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671346"
---
# <a name="idiaaddressmapgetrelativevirtualaddressenabled"></a>IDiaAddressMap::get_relativeVirtualAddressEnabled
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiaaddressmap::get_relativevirtualaddressenabled –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaaddressmap-get-relativevirtualaddressenabled).  
  
Určuje, zda je povoleno výpočtu a používání relativních virtuálních adres (RVA).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_relativeVirtualAddressEnabled (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pRetVal  
 [out] Vrátí `TRUE` Pokud výpočet RVA je povolené.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 RVA jsou povolené, pokud segmenty byl zpočátku načtena ze souboru PDB. Použití RVA je dočasně zakázat voláním [idiaaddressmap::put_relativevirtualaddressenabled –](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md) metody.  
  
 Navíc lze vytvořit nové hlavičky bitové kopie voláním [idiaaddressmap::set_imageheaders –](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md) metoda za nímž následuje volání `put_relativeVirtualAddressEnabled` metoda povolit používání RVA pomocí nové hlavičky bitové kopie.  
  
## <a name="see-also"></a>Viz také  
 [Idiaaddressmap –](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap::set_imageheaders –](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)   
 [IDiaAddressMap::put_relativeVirtualAddressEnabled](../../debugger/debug-interface-access/idiaaddressmap-put-relativevirtualaddressenabled.md)



