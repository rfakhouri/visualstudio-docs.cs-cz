---
title: Idiareadexeatoffsetcallback – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaReadExeAtOffsetCallback interface
ms.assetid: 3c961641-3ce3-4bc3-bd6e-a802fa3bec49
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: df32012a100d36c8d288b6b988b9498ff4afd3b3
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56635732"
---
# <a name="idiareadexeatoffsetcallback"></a>IDiaReadExeAtOffsetCallback
Umožňuje klientské aplikaci slouží k poskytování bajtů spustitelného souboru jako zadaným umístěním souboru.

## <a name="syntax"></a>Syntaxe

```
IDiaReadExeAtOffsetCallback : IUnknown
```

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 V následující tabulce jsou uvedeny metody objektu `IDiaReadExeAtOffsetCallback`.

|Metoda|Popis|
|------------|-----------------|
|[IDiaReadExeAtOffsetCallback::ReadExecutableAt](../../debugger/debug-interface-access/idiareadexeatoffsetcallback-readexecutableat.md)|Přečte zadaný počet bajtů počínaje od určeného posunutí ze spustitelného souboru.|

## <a name="remarks"></a>Poznámky
 Klientská aplikace implementuje toto rozhraní negace bajtů se spustitelný soubor používající absolutní posun do souboru ke spustitelnému souboru. Chcete-li použít relativní virtuální adresu, implementovat [idiareadexeatrvacallback –](../../debugger/debug-interface-access/idiareadexeatrvacallback.md) rozhraní.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Tato metoda je implementované klientská aplikace a předat [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metody jako alternativní metoda pro čtení souboru.

## <a name="requirements"></a>Požadavky
 Záhlaví: Dia2.h

 Knihovna: diaguids.lib

 DLL: msdia80.dll

## <a name="see-also"></a>Viz také
- [Rozhraní (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)
- [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)