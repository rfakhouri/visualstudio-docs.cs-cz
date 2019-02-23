---
title: Sccaddfilesfromscc – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccAddFilesFromSCC
helpviewer_keywords:
- SccAddFilesFromSCC function
ms.assetid: f21a3500-ade8-4dd8-8647-10e2179be9c1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e94d42e75af69de7e28e27979493d3178ca7d0a3
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56684764"
---
# <a name="sccaddfilesfromscc-function"></a>Sccaddfilesfromscc – funkce
Tato funkce přidá seznam souborů ze správy zdrojových kódů aktuálně otevřeném projektu.

## <a name="syntax"></a>Syntaxe

```cpp
SCCRTN SccAddFilesFromSCC(
   LPVOID  pContext,
   HWND    hWnd,
   LPSTR   lpUser,
   LPSTR   lpAuxProjPath,
   LONG    cFiles,
   LPCSTR* lpFilePaths,
   LPCSTR  lpDestination,
   LPCSTR  lpComment,
   LPBOOL  pbResults
);
```

### <a name="parameters"></a>Parametry
 pContext

[in] Ukazatel kontext modulu plug-in zdroje ovládacího prvku.

 hWnd

[in] Popisovač okna integrovaného vývojového prostředí, které modul plug-in správy zdrojového kódu můžete použít jako nadřazený pro všechna dialogová okna, které poskytuje.

 lpUser

[out v] Uživatelské jméno (až SCC_USER_SIZE, včetně ukončovacího znaku null).

 lpAuxProjPath

[out v] Pomocné řetězec, který identifikuje projektu (až `SCC_PRJPATH_`velikost, včetně ukončovacího znaku null).

 cFiles

[in] Počet souborů, které jsou uvedena v každém `lpFilePaths`.

 lpFilePaths

[out v] Pole názvy souborů přidejte do aktuálního projektu.

 lpDestination

[in] Cílová cesta kde soubory jsou k zapsání.

 lpComment

[in] Komentář, který se má použít pro všechny přidávané soubory.

 pbResults

[out v] Pole příznaky, které jsou sady, čímž indikuje úspěšné provedení (nenulovou hodnotu nebo hodnotu TRUE) nebo selhání (nula nebo hodnotu NEPRAVDA) pro každý soubor (velikost pole musí být dlouhý aspoň `cFiles` dlouhý).

## <a name="return-value"></a>Návratová hodnota
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:

|Hodnota|Popis|
|-----------|-----------------|
|SCC_E_PROJNOTOPEN|Projekt není otevřen.|
|SCC_E_OPNOTPERFORMED|Připojení není na stejný projekt podle specifikace `lpAuxProjPath.`|
|SCC_E_NOTAUTHORIZED|Uživatel nemá oprávnění k aktualizaci databáze.|
|SCC_E_NONSPECIFICERROR|Neznámá chyba|
|SCC_I_RELOADFILE|Soubor nebo projekt je potřeba znovu načíst.|

## <a name="see-also"></a>Viz také:
- [Funkce modulu plug-in API zdrojového ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)