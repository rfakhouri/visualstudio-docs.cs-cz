---
title: Idiareadexeatoffsetcallback::readexecutableat – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtOffsetCallback::ReadExecutableAt method
ms.assetid: 30b1cef0-b366-4712-8e89-d21f640964f8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bda25b870c110324962d0249948929b207d98826
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56619677"
---
# <a name="idiareadexeatoffsetcallbackreadexecutableat"></a>IDiaReadExeAtOffsetCallback::ReadExecutableAt
Přečte zadaný počet bajtů počínaje od určeného posunutí ze spustitelného souboru.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT ReadExecutableAt ( 
   DWORDLONG fileOffset,
   DWORD     cbData,
   DWORD*    pcbData,
   BYTE      data[]
);
```

#### <a name="parameters"></a>Parametry
 fileOffset

[in] Posun ve spustitelném souboru má začínat čtení.

 cbData

[in] Počet bajtů ke čtení.

 pcbData

[out] Vrátí počet přečtených bajtů.

 data[]
- [out v] Pole, které se vyplní přečtených ze souboru bajtů.

## <a name="remarks"></a>Poznámky
 Tato metoda je volána kód podpory, který DIA načtení bajtů dat ze spustitelného souboru pomocí posun absolutní. Tato metoda je volána z podporu [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metody.

## <a name="see-also"></a>Viz také
- [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)