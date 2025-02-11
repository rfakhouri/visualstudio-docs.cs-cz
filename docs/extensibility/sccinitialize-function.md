---
title: Sccinitialize – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccInitialize
helpviewer_keywords:
- SccInitialize function
ms.assetid: 5bc0d28b-2c68-4d43-9e51-541506a8f76e
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a855ecbc65211234b29808fc9e4cf256cd6b25f7
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66353587"
---
# <a name="sccinitialize-function"></a>SccInitialize – funkce
Tato funkce inicializuje modul plug-in správy zdrojového kódu a poskytuje možnosti a omezení pro integrované vývojové prostředí (IDE).

## <a name="syntax"></a>Syntaxe

```cpp
SCCRTN SccInitialize (
   LPVOID* ppvContext,
   HWND    hWnd,
   LPCSTR  lpCallerName,
   LPSTR   lpSccName,
   LPLONG  lpSccCaps,
   LPSTR   lpAuxPathLabel,
   LPLONG  pnCheckoutCommentLen,
   LPLONG  pnCommentLen
);
```

#### <a name="parameters"></a>Parametry
 `ppvContext`

[in] Modul plug-in správy zdrojového kódu můžete sem umístěte ukazatel na strukturu jeho kontext.

 `hWnd`

[in] Popisovač okna integrovaného vývojového prostředí, které modul plug-in správy zdrojového kódu můžete použít jako nadřazený pro všechna dialogová okna, které poskytuje.

 `lpCallerName`

[in] Název programu, volání modulu plug-in správy zdrojového kódu.

 `lpSccName`

[out v] Pokud modul plug-in správy zdrojového kódu vloží svůj vlastní název vyrovnávací paměti (která nepřekročí `SCC_NAME_LEN`).

 `lpSccCaps`

[out] Vrátí ovládací prvek zdroje modulu plug-in příznaky funkcí.

 `lpAuxPathLabel`

[out v] Vyrovnávací paměť, kde modul plug-in správy zdrojového kódu vloží řetězec, který popisuje `lpAuxProjPath` s parametrem vráceným [sccopenproject –](../extensibility/sccopenproject-function.md) a [sccgetprojpath –](../extensibility/sccgetprojpath-function.md) (která nepřekročí `SCC_AUXLABEL_LEN`).

 `pnCheckoutCommentLen`

[out] Vrátí maximální povolenou délku pro komentář registrace.

 `pnCommentLen`

[out] Vrátí maximální povolenou délku pro další komentáře.

## <a name="return-value"></a>Návratová hodnota
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:

|Value|Popis|
|-----------|-----------------|
|SCC_OK|Zdrojový ovládací prvek Inicializace byla úspěšná.|
|SCC_E_INITIALIZEFAILED|Systém nemohl být inicializován.|
|SCC_E_NOTAUTHORIZED|Uživatel nemůže provést zadanou operaci.|
|SCC_E_NONSPECFICERROR|Obecná chyba; systému správy zdrojového kódu nebyla inicializována.|

## <a name="remarks"></a>Poznámky
 Integrované vývojové prostředí volá tuto funkci při prvním načtení modulu plug-in správy zdrojového kódu. Umožňuje rozhraní IDE k předání určité informace, jako je jméno volajícího, v modulu plug-in. Integrované vývojové prostředí také získá zpět určité informace, jako je maximální povolená délka pro komentáře a modul plug-in vaší funkce.

 `ppvContext` Odkazuje `NULL` ukazatele. Modul plug-in správy zdrojového kódu můžete přidělit strukturu pro vlastní použití a ukládají ukazatel na danou strukturu v `ppvContext`. Rozhraní IDE předá tento ukazatel všechny ostatní funkce rozhraní API VSSCI, povolení modulu plug-in mít informace o kontextu k dispozici bez nutnosti uchýlit se do globální paměti a podporují více instancí modulu plug-in. By měla být odebrána tuto strukturu, kdy [sccuninitialize –](../extensibility/sccuninitialize-function.md) je volána.

 `lpCallerName` a `lpSccName` parametry povolení integrovaného vývojového prostředí a modulu plug-in správy zdrojového kódu k výměně názvy. Tyto názvy lze jednoduše k rozlišení mezi několik instancí, nebo ve skutečnosti jsou zobrazeny v nabídkách a dialogových oknech.

 `lpAuxPathLabel` Parametr je řetězec, který slouží k identifikaci pomocné projektu k cestě, která je uložena v souboru řešení a předat při volání k modulu plug-in správy zdrojového kódu jako komentáře [sccopenproject –](../extensibility/sccopenproject-function.md). [!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] použije řetězec "SourceSafe projektu:"; Pomocí tohoto konkrétního řetězce neměly by být další ovládací prvek moduly plug-in zdrojového kódu.

 `lpSccCaps` Parametr poskytuje správu zdrojového kódu modulu plug-in místo k uložení bitové příznaky určující modul plug-in vaší funkce. (Úplný seznam příznaky bitflag schopností najdete v tématu [příznaky funkcí](../extensibility/capability-flags.md)). Například pokud modul plug-in plány pro zápis výsledky do funkce poskytované volající zpětného volání, modul plug-in byste nastavit možnost bit SCC_CAP_TEXTOUT. To by signalizuje, že rozhraní IDE k vytvoření okna pro výsledky kontroly verzí.

## <a name="see-also"></a>Viz také
- [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)
- [SccUninitialize](../extensibility/sccuninitialize-function.md)
- [SccOpenProject](../extensibility/sccopenproject-function.md)
- [Příznaky funkcí](../extensibility/capability-flags.md)