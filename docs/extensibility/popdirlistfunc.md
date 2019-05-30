---
title: POPDIRLISTFUNC | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- POPLISTFUNC
helpviewer_keywords:
- POPDIRLISTFUNC callback function
ms.assetid: 0ee90fd2-5467-4154-ab4c-7eb02ac3a14c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0fef3ab783c736fd2573e8d9df1a513e25d37020
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66326136"
---
# <a name="popdirlistfunc"></a>POPDIRLISTFUNC
Toto je funkce zpětného volání k [sccpopulatedirlist –](../extensibility/sccpopulatedirlist-function.md) funkce se aktualizovat kolekci adresářů a (volitelně) názvy souborů a zjistěte, které jsou pod správou zdrojových kódů.

 `POPDIRLISTFUNC` Zpětného volání lze volat pouze pro tyto adresáře a názvy souborů (v seznamu udělená `SccPopulateDirList` funkce), které jsou ve skutečnosti pod správou zdrojových kódů.

## <a name="signature"></a>podpis

```cpp
typedef BOOL (*POPDIRLISTFUNC)(
   LPVOID pvCallerData,
   BOOL bFolder,
   LPCSTR lpDirectoryOrFileName
);
```

## <a name="parameters"></a>Parametry
 pvCallerData

[in] Hodnota uživatele na [sccpopulatedirlist –](../extensibility/sccpopulatedirlist-function.md).

 bFolder

[in] `TRUE` -li název v `lpDirectoryOrFileName` jedná se o adresář jinak název je název souboru.

 lpDirectoryOrFileName

[in] Úplná místní cesta k názvu adresáře nebo souboru, který je pod správou zdrojového kódu.

## <a name="return-value"></a>Návratová hodnota
 Rozhraní IDE vrátí odpovídající chybový kód:

|Value|Popis|
|-----------|-----------------|
|SCC_OK|Pokračujte ve zpracování.|
|SCC_I_OPERATIONCANCELED|Zastavte zpracování.|
|SCC_E_xxx|Všechny chyby příslušný zdrojový ovládací prvek by se měla zastavit zpracování.|

## <a name="remarks"></a>Poznámky
 Pokud `fOptions` parametr `SccPopulateDirList` obsahuje funkce `SCC_PDL_INCLUDEFILES` příznak, bude pravděpodobně obsahovat seznam názvů souborů, jakož i názvy adresářů.

## <a name="see-also"></a>Viz také:
- [Funkce zpětného volání implementované integrovaným vývojovým prostředím](../extensibility/callback-functions-implemented-by-the-ide.md)
- [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)
- [Kódy chyb](../extensibility/error-codes.md)