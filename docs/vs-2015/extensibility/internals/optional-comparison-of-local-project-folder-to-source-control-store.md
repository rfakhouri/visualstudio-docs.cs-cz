---
title: Volitelné porovnání místní složky projektu do zdrojového ovládacího prvku Store | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, comparing versions
- source control plug-ins, local project folders
ms.assetid: 65217e8b-15a6-4446-92b0-4cff1c6220f5
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: be26b4195e0db7b3b78fcc2223ff2a6f8bde47d3
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63438941"
---
# <a name="optional-comparison-of-local-project-folder-to-source-control-store"></a>Volitelné porovnání místní složky projektu a úložiště správy zdrojového kódu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ve zdroji řízení porovnání mezi místní složce projektu a Správa zdrojového kódu se dá udělat pomocí funkce modulu Plug-in rozhraní API 1.2 [sccdirqueryinfo –](../../extensibility/sccdirqueryinfo-function.md) a [sccdirdiff –](../../extensibility/sccdirdiff-function.md).  
  
 V rámci **Průzkumníka řešení**, pokud je vybrána složka namísto jednotlivých souborů **porovnání verzí** vyvolá novou nabídku [sccdirqueryinfo –](../../extensibility/sccdirqueryinfo-function.md) a [ Sccdirdiff –](../../extensibility/sccdirdiff-function.md) v modulu plug-in správy zdrojového kódu.  
  
## <a name="new-capability-flags"></a>Nové příznaky funkcí  
 `SCC_CAP_DIRECTORYDIFF`  
  
 `SCC_CAP_DIRECTORYCHECKOUT`  
  
## <a name="new-functions"></a>Nové funkce  
 [SccDirDiff](../../extensibility/sccdirdiff-function.md)  
  
 [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md)  
  
 `SccDirQueryInfo` Funkce je volána před provedením `SccDirDiff` k určení, zda je v pracovním adresáři spravovanými zdroji. `SccDirDiff` Funkce zobrazí rozdíly mezi aktuálním místním adresáři a odpovídající složky správy zdrojového kódu. Tento příkaz zobrazí dotaz, chcete-li zobrazit seznam změn do adresáře, modul plug-in správy zdrojového kódu. Modul plug-in správy zdrojového kódu obsahuje vlastní uživatelské rozhraní pro zobrazení rozdílů.  
  
> [!NOTE]
> Tato funkce využívá stejné příznaků příkazů jako [sccdiff –](../../extensibility/sccdiff-function.md). Jako poskytovatele správy zdrojového kódu modulu plug-in můžete operace "rychlé diff" pro adresáře není podporována.  
  
## <a name="see-also"></a>Viz také  
 [Co je nového v rozhraní API modulu plug-in správy zdrojového kódu ve verzi 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)
