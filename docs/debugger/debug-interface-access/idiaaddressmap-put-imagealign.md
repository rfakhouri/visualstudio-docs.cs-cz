---
title: Idiaaddressmap::put_imagealign – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaAddressMap::put_imageAlign method
ms.assetid: f9ce875d-c263-43e5-a534-f34c37f9866f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2126d59d223e4923609071fa130b1cac465073ad
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56616947"
---
# <a name="idiaaddressmapputimagealign"></a>IDiaAddressMap::put_imageAlign
Nastaví zarovnání obrázku.

## <a name="syntax"></a>Syntaxe

```C++
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
 Bitové kopie (načíst spustitelné soubory) je zarovnán zadaná paměťová hranice. Toto uspořádání může mít vliv na aktuální architektura systému a možností v době kompilace a odkaz. Zarovnání obrázku je vždycky aktivní hranice. Platné jsou následující hodnoty zarovnání obrázku: hranice 1, 2, 4, 8, 16, 32 a 64 bajtů.

 Aktuální zarovnání obrázku se dá načíst pomocí volání [idiaaddressmap::get_imagealign –](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md) metody.

> [!NOTE]
>  Na obrázku je již načten v době, kdy tuto metodu lze volat. `put_imageAlign` Metoda se typicky používá při image byla přesunuta nebo změnit, a nové zarovnání je povinný.

## <a name="see-also"></a>Viz také
- [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)
- [IDiaAddressMap::get_imageAlign](../../debugger/debug-interface-access/idiaaddressmap-get-imagealign.md)