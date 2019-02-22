---
title: Idiasession::findchildren – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findChildren method
ms.assetid: 5d19046f-f668-4aa9-8788-95cda9a98997
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c5759d810bf9180522508a6be54e5c94ffcfadb3
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56643077"
---
# <a name="idiasessionfindchildren"></a>IDiaSession::findChildren
Načte všechny podřízené objekty zadaný nadřazený identifikátor odpovídající název a značka typu.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT findChildren ( 
   IDiaSymbol*       parent,
   SymTagEnum        symtag,
   LPCOLESTR         name,
   DWORD             compareFlags,
   IDiaEnumSymbols** ppResult
);
```

#### <a name="parameters"></a>Parametry
 `parent`

[in] [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) představující nadřazeného objektu. Pokud je tento symbol nadřazené funkce, modul nebo blok a pak jeho lexikální podřízené položky jsou vráceny v `ppResult`. Pokud je symbol nadřazeného typu, budou vráceny podřízené třídy. Pokud je tento parametr `NULL`, pak `symtag` musí být nastaveno na `SymTagExe` nebo `SymTagNull`, která vrací globální obor (soubor .exe).

 `symtag`

[in] Určuje symbol značky podřízené položky, který se má načíst. Hodnoty pocházejí ze [symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md) výčtu. Nastavte na `SymTagNull` načíst všechny podřízené objekty.

 `name`

[in] Určuje název podřízenou položku, která se má načíst. Nastavte na `NULL` pro všechny podřízené objekty, které se mají načíst.

 `compareFlags`

[in] Určení možností porovnání využije na odpovídající název. Hodnoty z [namesearchoptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md) výčtu lze použít samostatně nebo v kombinaci.

 `ppResult`

[out] Vrátí [idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md) načíst objekt, který obsahuje seznam podřízenými symboly.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="example"></a>Příklad
 Následující příklad ukazuje, jak najít místní proměnné, funkce `pFunc` nejmenuje shoda `szVarName`.

```C++
IDiaEnumSymbols* pEnum;
pSession->findChildren( pFunc, SymTagData, szVarName, nsCaseSensitive, &pEnum );
```

## <a name="see-also"></a>Viz také
- [Přehled](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)
- [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [NameSearchOptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md)
- [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)