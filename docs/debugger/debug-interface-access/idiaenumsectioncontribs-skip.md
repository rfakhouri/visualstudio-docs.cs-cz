---
title: Idiaenumsectioncontribs::Skip – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSectionContribs::Skip method
ms.assetid: 7471a178-5134-41b2-80a6-51ff96abe916
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c90c2148fc5a563fef8946bd39acf4603d7d09f6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62833230"
---
# <a name="idiaenumsectioncontribsskip"></a>IDiaEnumSectionContribs::Skip
Vynechá zadaný počet části příspěvků v sekvenci výčtu.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT Skip( 
   ULONG celt
);
```

#### <a name="parameters"></a>Parametry
 `celt`

[in] Počet příspěvků oddíl v pořadí výčtu pro přeskočení.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` Pokud neexistují žádné další příspěvky část přeskočit.

## <a name="see-also"></a>Viz také
- [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)