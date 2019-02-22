---
title: Idialoadcallback2 – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback2 interface
ms.assetid: 9a44277d-cbed-4811-9bad-5a2aa0f09323
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: daf0b48aca06b404824059030052223a8545a6b0
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56641452"
---
# <a name="idialoadcallback2"></a>IDiaLoadCallback2
Zpětná volání obdrží od DIA symbol hledání proceduru, která umožňují omezení vynucená pro proces vyhledáním.

## <a name="syntax"></a>Syntaxe

```
IDiaLoadCallback2 : IDiaLoadCallback
```

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Kromě metod v [idialoadcallback –](../../debugger/debug-interface-access/idialoadcallback.md) rozhraní, toto rozhraní poskytuje následující metody:

|Metoda|Popis|
|------------|-----------------|
|[IDiaLoadCallback2::RestrictOriginalPathAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictoriginalpathaccess.md)|Určuje, jestli hledáte souboru .pdb v původní adresář ladění.|
|[IDiaLoadCallback2::RestrictReferencePathAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictreferencepathaccess.md)|Určuje, jestli hledá soubor PDB je povolený v cestě, kde je umístěn soubor .exe.|
|[IDiaLoadCallback2::RestrictDBGAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictdbgaccess.md)|Určuje, jestli hledáte informace o ladění je povolené z soubory dbg.|
|[IDiaLoadCallback2::RestrictSystemRootAccess](../../debugger/debug-interface-access/idialoadcallback2-restrictsystemrootaccess.md)|Určuje, jestli hledání souborů PDB je povolený v kořenovém adresáři systému.|

## <a name="remarks"></a>Poznámky
 Klientská aplikace implementuje toto rozhraní a poskytuje odkaz na jeho ve volání [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metody. Mějte na paměti pro všechny metody v implementaci [idialoadcallback –](../../debugger/debug-interface-access/idialoadcallback.md) a interface.

## <a name="requirements"></a>Požadavky
 Záhlaví: Dia2.h

 Knihovna: diaguids.lib

 DLL: msdia80.dll

## <a name="see-also"></a>Viz také
- [Rozhraní (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)
- [IDiaReadExeAtOffsetCallback](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)
- [IDiaReadExeAtRVACallback](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)
- [IDiaLoadCallback](../../debugger/debug-interface-access/idialoadcallback.md)