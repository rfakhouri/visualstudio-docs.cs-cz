---
title: Porovnat složky projektu do zdrojového ovládacího prvku Store | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, comparing versions
- source control plug-ins, local project folders
ms.assetid: 65217e8b-15a6-4446-92b0-4cff1c6220f5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d675868e10a99a192681c52495ad3b37e384d390
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350703"
---
# <a name="optional-comparison-of-local-project-folder-to-source-control-store"></a>Volitelné porovnání místní složky projektu a úložiště správy zdrojového kódu
Ve zdroji řízení porovnání mezi místní složce projektu a Správa zdrojového kódu se dá udělat pomocí funkce modulu Plug-in rozhraní API 1.2 [sccdirqueryinfo –](../../extensibility/sccdirqueryinfo-function.md) a [sccdirdiff –](../../extensibility/sccdirdiff-function.md).

 V rámci **Průzkumníka řešení**, pokud je vybrána složka namísto jednotlivých souborů **porovnání verzí** vyvolá novou nabídku [sccdirqueryinfo –](../../extensibility/sccdirqueryinfo-function.md) a [ Sccdirdiff –](../../extensibility/sccdirdiff-function.md) v modulu plug-in správy zdrojového kódu.

## <a name="new-capability-flags"></a>Nové příznaky funkcí
 `SCC_CAP_DIRECTORYDIFF`

 `SCC_CAP_DIRECTORYCHECKOUT`

## <a name="new-functions"></a>Nové funkce
- [SccDirDiff](../../extensibility/sccdirdiff-function.md)

- [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md)

 `SccDirQueryInfo` Funkce je volána před provedením `SccDirDiff` k určení, zda je v pracovním adresáři spravovanými zdroji. `SccDirDiff` Funkce zobrazí rozdíly mezi aktuálním místním adresáři a odpovídající složky správy zdrojového kódu. Tento příkaz zobrazí dotaz, chcete-li zobrazit seznam změn do adresáře, modul plug-in správy zdrojového kódu. Modul plug-in správy zdrojového kódu obsahuje vlastní uživatelské rozhraní pro zobrazení rozdílů.

> [!NOTE]
> Tato funkce využívá stejné příznaků příkazů jako [sccdiff –](../../extensibility/sccdiff-function.md). Jako poskytovatele správy zdrojového kódu modulu plug-in můžete operace "rychlé diff" pro adresáře není podporována.

## <a name="see-also"></a>Viz také
- [Co je nového v rozhraní API modulu plug-in správy zdrojového kódu ve verzi 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)