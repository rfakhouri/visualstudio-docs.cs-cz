---
title: Sccaddfromscc – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccAddFromScc
helpviewer_keywords:
- SccAddFromScc function
ms.assetid: 902e764d-200e-46e1-8c42-4da7b037f9a0
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e8f37ce82630b72d5a01c66c8848431e8f6c2891
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66334035"
---
# <a name="sccaddfromscc-function"></a>Sccaddfromscc – funkce
Tato funkce umožňuje uživateli procházet soubory, které jsou již v systému správy zdrojového kódu a následně provést tyto soubory součástí aktuálního projektu. Například můžete tuto funkci získat společný soubor hlaviček do aktuálního projektu bez kopírování souboru. Vrácené pole souborů, `lplpFileNames`, obsahuje seznam souborů, které chce uživatel přidat do projektu integrovaném vývojovém prostředí.

## <a name="syntax"></a>Syntaxe

```cpp
SCCRTN SccAddFromScc (
   LPVOID   pvContext,
   HWND     hWnd,
   LPLONG   lpnFiles,
   LPCSTR** lplpFileNames
);
```

### <a name="parameters"></a>Parametry
 pvContext

[in] Struktura kontext modulu plug-in zdroje ovládacího prvku.

 hWnd

[in] Popisovač okna integrovaného vývojového prostředí, které modul plug-in správy zdrojového kódu můžete použít jako nadřazený pro všechna dialogová okna, které poskytuje.

 lpnFiles

[out v] Vyrovnávací paměť pro počet souborů, které se přidávají v. (Toto je `NULL` pokud paměť odkazované `lplpFileNames` odemčen. Podrobnosti najdete v části poznámky.)

 lplpFileNames

[out v] Pole ukazatelů na název souboru bez cesty k adresářům. Toto pole je přiděleno a uvolněno modul plug-in správy zdrojového kódu. Pokud `lpnFiles` = 1 a `lplpFileNames` není `NULL`, křestní jméno v poli odkazované `lplpFileNames` obsahuje cílové složky.

## <a name="return-value"></a>Návratová hodnota
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:

|Hodnota|Popis|
|-----------|-----------------|
|SCC_OK|Soubory byly úspěšně umístěn a přidány do projektu.|
|SCC_I_OPERATIONCANCELED|Operace byla zrušena s žádný vliv.|
|SCC_I_RELOADFILE|Soubor nebo projekt je potřeba znovu načíst.|

## <a name="remarks"></a>Poznámky
 Integrované vývojové prostředí volá tuto funkci. Pokud modul plug-in správy zdrojového kódu podporuje zadávání místní cílovou složku, rozhraní IDE předá `lpnFiles` = 1 a předá název místní složky do `lplpFileNames`.

 Při volání `SccAddFromScc` funkce vrátí, modul plug-in má přiřazeny hodnoty do `lpnFiles` a `lplpFileNames`, přidělení paměti pro pole název souboru podle potřeby (Všimněte si, že toto přidělení nahradí ukazatel v `lplpFileNames`). Modul plug-in správy zdrojového kódu je odpovědná za umístění všech souborů v adresáři uživatele nebo ve složce zadané označení. Rozhraní IDE potom přidá soubory do projektu integrovaném vývojovém prostředí.

 A konečně, integrovaném vývojovém prostředí volá tuto funkci, podruhé, předejte `NULL` pro `lpnFiles`. To je interpretován jako speciální signál k uvolnění paměti přidělené pro pole název souboru v modulu plug-in správy zdrojového kódu `lplpFileNames``.`

 `lplpFileNames` je `char ***` ukazatele. Modul plug-in správy zdrojového kódu umístí ukazatel na pole ukazatelů na názvy souborů, tedy předání seznamu ve standardní způsob pro toto rozhraní API.

> [!NOTE]
> Počáteční verze rozhraní API VSSCI neposkytl způsob, jak určit cílový projekt pro přidání souborů. Aby se tomuto sémantika `lplpFIleNames` parametr vylepšené a nastavte ji jako parametr ve vstupně-výstupní spíše než výstupní parametr. Pokud pouze jeden soubor je zadán, tedy hodnota na které odkazuje `lpnFiles` = 1, pak první prvek `lplpFileNames` obsahuje cílové složky. Použití těchto nových sémantiku volání integrovaného vývojového prostředí `SccSetOption` pracovat `nOption`parametr nastaven na `SCC_OPT_SHARESUBPROJ`. Pokud modul plug-in správy zdrojového kódu nepodporuje sémantiku, vrátí `SCC_E_OPTNOTSUPPORTED`. To tedy zakáže použití **přidat ze správy zdrojových kódů** funkce. Pokud modul plug-in podporuje **přidat ze správy zdrojových kódů** funkci (`SCC_CAP_ADDFROMSCC`), pak musí podporovat nové sémantiku a vracet `SCC_I_SHARESUBPROJOK`.

## <a name="see-also"></a>Viz také:
- [Funkce modulu plug-in API zdrojového ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)
- [SccSetOption](../extensibility/sccsetoption-function.md)