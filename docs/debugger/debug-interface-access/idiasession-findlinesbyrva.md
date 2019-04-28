---
title: Idiasession::findlinesbyrva – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLinesByRVA method
ms.assetid: 06f53b0b-b5b4-42cf-9252-dcee0dbe2d71
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4316bfa423392a98946fc0bb86af2f2e9836aba2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62827681"
---
# <a name="idiasessionfindlinesbyrva"></a>IDiaSession::findLinesByRVA
Načte řádky v zadané kompilace, které obsahují zadaný relativní virtuální adresu (RVA).

## <a name="syntax"></a>Syntaxe

```C++
HRESULT findLinesByRVA ( 
    DWORD                 rva,
    DWORD                 length,
    IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>Parametry
`rva`

[in] Určuje adresu jako adresu RVA.

`length`

[in] Určuje počet bajtů rozsah adres, aby pokryl s Tento dotaz.

`ppResult`

[out] Vrátí [idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md) objekt, který obsahuje seznam všech řádku čísla tohoto krytí zadaný rozsah adres.

## <a name="return-value"></a>Návratová hodnota
Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="example"></a>Příklad
Tento příklad ukazuje funkci, která získá všechna čísla řádků obsažená v zadanou funkci pomocí funkce relativní virtuální adresu a délku.

```C++
IDiaEnumLineNumbers* GetLineNumbersByRVA(IDiaSymbol *pFunc, IDiaSession *pSession)
{
    IDiaEnumLineNumbers* pEnum = NULL;
    DWORD                rva;
    ULONGLONG            length;

    if (pFunc->get_relativeVirtualAddress ( &rva ) == S_OK)
    {
        pFunc->get_length ( &length );
        pSession->findLinesByRVA( rva, static_cast<DWORD>( length ), &pEnum );
    }
    return(pEnum);
}
```

## <a name="see-also"></a>Viz také
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
