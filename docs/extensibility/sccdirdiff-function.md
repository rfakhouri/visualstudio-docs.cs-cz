---
title: Sccdirdiff – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccDirDiff
helpviewer_keywords:
- SccDirDiff function
ms.assetid: 26c9ba92-e3b9-4dd2-bd5e-76b17745e308
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c3d207a171acba4127849cd479a1049afafa8492
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66351900"
---
# <a name="sccdirdiff-function"></a>Sccdirdiff – funkce
Tato funkce zobrazí rozdíly mezi aktuální místní adresáře na disku klienta a odpovídající projekt pod správou zdrojových kódů.

## <a name="syntax"></a>Syntaxe

```cpp
SCCRTN SccDirDiff(
   LPVOID    pContext,
   HWND      hWnd,
   LPCSTR    lpDirName,
   LONG      dwFlags,
   LPCMDOPTS pvOptions
);
```

### <a name="parameters"></a>Parametry
 pContext

[in] Struktura kontext modulu plug-in zdroje ovládacího prvku.

 hWnd

[in] Popisovač okna integrovaného vývojového prostředí, které modul plug-in správy zdrojového kódu můžete použít jako nadřazený pro všechna dialogová okna, které poskytuje.

 lpDirName

[in] Plně kvalifikovaná cesta k místnímu adresáři, pro které chcete zobrazit visual rozdíl.

 dwFlags

[in] Příkaz příznaky (viz poznámky části).

 pvOptions

[in] Možností správy zdrojového kódu plug-konkrétní.

## <a name="return-value"></a>Návratová hodnota
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:

|Hodnota|Popis|
|-----------|-----------------|
|SCC_OK|Adresáře na disku je stejný jako projektu ve správě zdrojového kódu.|
|SCC_I_FILESDIFFER|Adresáře na disku se liší od projektu ve správě zdrojového kódu.|
|SCC_I_RELOADFILE|Soubor nebo projekt je potřeba znovu načíst.|
|SCC_E_FILENOTCONTROLLED|Adresář není pod správou zdrojového kódu.|
|SCC_E_NOTAUTHORIZED|Uživatel nemůže k provedení této operace.|
|SCC_E_ACCESSFAILURE|Došlo k problému, přístup k systému správy zdrojového kódu, pravděpodobně kvůli problémům se síti nebo kolize. Doporučuje se zkuste to znovu.|
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|K nespecifikované chybě.|
|SCC_E_FILENOTEXIST|Místní adresář se nenašel.|

## <a name="remarks"></a>Poznámky
 Tato funkce slouží k dáte pokyn, aby pro uživatele zobrazíte seznam změn v zadaném adresáři modulu plug-in správy zdrojového kódu. Modul plug-in otevře vlastního okna, ve formátu podle svého výběru, chcete-li zobrazit rozdíly mezi uživatele adresáře na disku a odpovídající projektu v rámci správy verzí.

 Pokud modul plug-in podporuje porovnání adresářů vůbec, musí podporovat porovnání adresářů na základě názvu souboru i v případě, že se nepodporují možnosti "rychlé diff".

|`dwFlags`|interpretace|
|---------------|--------------------|
|SCC_DIFF_IGNORECASE|Porovnávání (lze použít pro rychlé diff nebo vizuálu).|
|SCC_DIFF_IGNORESPACE|Ignoruje prázdné znaky (lze použít pro rychlé diff nebo vizuálu).|
|SCC_DIFF_QD_CONTENTS|Pokud se podporuje modul plug-in správy zdrojového kódu, porovná tiše adresáři bajt po bajtu.|
|SCC_DIFF_QD_CHECKSUM|Pokud se podporuje modul plug-in, tiše porovnává adresáře prostřednictvím kontrolní součet nebo, pokud není podporován, spadne zpět na SCC_DIFF_QD_CONTENTS.|
|SCC_DIFF_QD_TIME|Pokud se podporuje modul plug-in, tiše porovnává adresáře prostřednictvím její časové razítko nebo, pokud není podporován, přejde na SCC_DIFF_QD_CHECKSUM nebo SCC_DIFF_QD_CONTENTS.|

> [!NOTE]
> Tato funkce využívá stejné příznaků příkazů, jako [sccdiff –](../extensibility/sccdiff-function.md). Modul plug-in správy zdrojového kódu však rozhodnout operace "rychlé diff" pro adresáře není podporována.

## <a name="see-also"></a>Viz také:
- [Funkce modulu plug-in API zdrojového ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)