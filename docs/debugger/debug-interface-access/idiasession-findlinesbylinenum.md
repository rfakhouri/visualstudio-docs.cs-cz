---
title: Idiasession::findlinesbylinenum – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLinesByLinenum method
ms.assetid: 76d5622d-9a91-4c2a-a98f-263af5d1daef
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9d5999febf6e926ef8e9beb365728a3b150e1a38
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839264"
---
# <a name="idiasessionfindlinesbylinenum"></a>IDiaSession::findLinesByLinenum
Určuje čísla řádků souboru pro kompilaci, který je zadaný počet řádků ve zdrojovém souboru v rámci nebo blízko ní.

## <a name="syntax"></a>Syntaxe

```C++
HRESULT findLinesByLinenum ( 
    IDiaSymbol*           compiland,
    IDiaSourceFile*       file,
    DWORD                 linenum,
    DWORD                 column,
    IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>Parametry
`compiland`

[in] [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt, který reprezentuje kompilace, ve kterém chcete hledat čísla řádků. Tento parametr nemůže mít `NULL`.

`file`

[in] [Idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md) objekt, který reprezentuje zdrojový soubor pro vyhledávání. Tento parametr nemůže mít `NULL`.

`linenum`

[in] Určuje číslo řádku založen na jedničce.

> [!NOTE]
> Nula nelze použít k určení všech řádků (použít [idiasession::findlines –](../../debugger/debug-interface-access/idiasession-findlines.md) metody k vyhledání všech řádků).

`column`

[in] Určuje číslo sloupce. Můžete určit všechny sloupce nula. Sloupec je posun bajtů do řádku.

`ppResult`

[out] Vrátí [idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md) načíst objta, který obsahuje seznam čísel řádků.

## <a name="return-value"></a>Návratová hodnota
Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="example"></a>Příklad
Následující příklad ukazuje, jak otevřít zdrojový soubor, výčet souborech určených ke kompilaci přispěl tento soubor a vyhledejte číslo řádku ve zdrojovém souboru, kde začíná každý kompilace.

```C++
void ShowLinesInCompilands(IDiaSession *pSession, LPCOLESTR filename)
{
    IDiaEnumSourceFiles* pEnum;
    IDiaSourceFile*      pFile;
    DWORD                celt;

    pSession->findFile ( NULL, filename, nsFNameExt, &pEnum );
    while ( pEnum->Next ( 1, &pFile, &celt ) == S_OK ) // for each file
    {
        IDiaEnumSymbols* pEnumCompilands;
        IDiaSymbol* pCompiland;

        pFile->get_compilands ( &pEnumCompilands );
        // for each compiland
        while ( pEnumCompilands->Next ( 1, &pCompiland, &celt ) == S_OK )
        {
            IDiaEnumLineNumbers* pEnum;
            // Find first compiland closest to line 1 of the file.
            if (pSession->findLinesByLinenum( pCompiland, pFile, 1, 0, &pEnum ) == S_OK)
            {
                IDiaLineNumber *pLineNumber;
                DWORD lineCount;
                while ( pEnum->Next(1,&pLineNumber,&lineCount) == S_OK)
                {
                    DWORD lineNum;
                    if (pLineNumber->get_line(&lineNum) == S_OK)
                    {
                        printf("compiland starts in source at line number = %lu\n",lineNum);
                    }
                }
            }
        }
    }
}
```

## <a name="see-also"></a>Viz také
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSession::findLinesByAddr](../../debugger/debug-interface-access/idiasession-findlinesbyaddr.md)
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
