---
title: IDiaSymbol::findChildrenEx | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::findChildrenEx
ms.assetid: 6e045045-da8c-4338-9423-81a1ca20c405
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2b833353beb009bb4eabbf000d45e0eb44a5794f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56611409"
---
# <a name="idiasymbolfindchildrenex"></a>IDiaSymbol::findChildrenEx
Načte podřízené objekty daného symbolu. Místní symboly, které jsou vráceny zahrnují informace o rozsahu za provozu, pokud je program zkompilován s optimalizací na.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT findChildrenEx ( 
   enum SymTagEnum   symtag,
   LPCOLESTR         name,
   DWORD             compareFlags,
   IDiaEnumSymbols** ppResult
);
```

#### <a name="parameters"></a>Parametry
 `symtag`

[in] Určuje symbol značky podřízené položky, které se mají načíst, jak jsou definovány v [symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md). Nastavte na `SymTagNull` pro všechny podřízené objekty, které se mají načíst.

 `name`

[in] Určuje název podřízenou položku, která se má načíst. Nastavte na `NULL` pro všechny podřízené objekty, které se mají načíst.

 `compareFlags`

[in] Určení možností porovnání uplatňovat na odpovídající název. Hodnoty z [namesearchoptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md) výčtu lze použít samostatně nebo v kombinaci.

 `ppResult`

[out] Vrátí [idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md) načíst objekt, který obsahuje seznam podřízenými symboly.

## <a name="return-value"></a>Návratová hodnota
 Vrátí `S_OK` Pokud byl nalezen nejméně jeden podřízený prvek symbolu nebo vrátí `S_FALSE` Pokud nebyly nalezeny žádné podřízené položky; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda je rozšířenou verzi [idiasymbol::findchildren –](../../debugger/debug-interface-access/idiasymbol-findchildren.md).

## <a name="requirements"></a>Požadavky
 Záhlaví: Dia2.h

 Knihovna: diaguids.lib

 DLL: msdia100.dll

## <a name="see-also"></a>Viz také
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
- [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)
- [NameSearchOptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md)