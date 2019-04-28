---
title: IDiaPropertyStorage::ReadLONG | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadLONG
ms.assetid: 32054cbc-db55-4513-a1b4-de80e77aac8a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2fb277368e23cf51a4d3d3b69226ee6bf093d6c3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839612"
---
# <a name="idiapropertystoragereadlong"></a>IDiaPropertyStorage::ReadLONG
Přečte `LONG` hodnoty v sadu vlastností.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT ReadDLONG ( 
   PROPID id,
   LONG*  pValue
);
```

#### <a name="parameters"></a>Parametry
 `id`

[in] Identifikátor vlastnosti pro čtení (`PROPID` je definována v WTypes.h jako `ULONG`).

 `pValue`

[out] Vrátí hodnotu vlastnosti.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_INVALIDARG` Pokud vlastnost není typu `LONG`.

## <a name="remarks"></a>Poznámky
 A `LONG` je definován Windows jako 32bitové celé číslo se znaménkem.

## <a name="see-also"></a>Viz také
- [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)