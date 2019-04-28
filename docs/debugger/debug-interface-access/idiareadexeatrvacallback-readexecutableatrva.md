---
title: Idiareadexeatrvacallback::readexecutableatrva – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtRVACallback::ReadExecutableAtRVA method
ms.assetid: 3c1e965f-8f05-41a8-86d8-01830b2377c9
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cf423ddc91926fb04adac849783b7c26b4c4f720
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62828461"
---
# <a name="idiareadexeatrvacallbackreadexecutableatrva"></a>IDiaReadExeAtRVACallback::ReadExecutableAtRVA
Přečte zadaný počet bajtů počínaje zadanou relativní virtuální adresu (RVA) ze spustitelného souboru.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT ReadExecutableAtRVA ( 
   DWORD  relativeVirtualAddress,
   DWORD  cbData,
   DWORD* pcbData,
   BYTE   data[]
);
```

#### <a name="parameters"></a>Parametry
 `relativeVirtualAddress`

[in] RVA spustitelného souboru, který má začínat čtení.

 `cbData`

[in] Počet bajtů ke čtení.

 `pcbData`

[out] Vrátí počet přečtených bajtů.

 `data[]`

[out v] Pole, které se vyplní Bajty čtení z tohoto souboru.

## <a name="remarks"></a>Poznámky
 Tato metoda je volána kód podpory, který DIA načtení bajtů dat ze spustitelného souboru pomocí relativní virtuální adresu. Tato metoda je volána z podporu [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metody.

## <a name="see-also"></a>Viz také
- [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)