---
title: "Porovnání projektu složku pro zdrojové ovládací prvek úložiště | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, comparing versions
- source control plug-ins, local project folders
ms.assetid: 65217e8b-15a6-4446-92b0-4cff1c6220f5
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cde0a7c34fe81c86d9f500bb1800006e5291ee92
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="optional-comparison-of-local-project-folder-to-source-control-store"></a>Volitelné porovnání projektu místní složku pro zdrojové úložiště ovládací prvek
Ve zdroji řízení 1.2 rozhraní API modulu Plugin porovnání mezi složky místní projektu a Správa zdrojového kódu se dá udělat pomocí funkce [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md) a [SccDirDiff](../../extensibility/sccdirdiff-function.md).  
  
 V rámci **Průzkumníku řešení**, pokud je vybrána složka místo jednotlivých souborů, **porovnat verze** místní nabídky vyvolá nové [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md) a [ SccDirDiff](../../extensibility/sccdirdiff-function.md) v modulu plug-in zdrojového kódu.  
  
## <a name="new-capability-flags"></a>Nové funkce příznaky  
 `SCC_CAP_DIRECTORYDIFF`  
  
 `SCC_CAP_DIRECTORYCHECKOUT`  
  
## <a name="new-functions"></a>Nové funkce  
 [SccDirDiff](../../extensibility/sccdirdiff-function.md)  
  
 [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md)  
  
 `SccDirQueryInfo` Funkce je volána před provedením `SccDirDiff` lze zjistit pracovní adresář je řízený zdroje. `SccDirDiff` Funkce zobrazí rozdíly mezi aktuálním místním adresáři a odpovídající zdrojové složky ovládacího prvku. Tento příkaz zobrazí dotaz, modul plug-in zobrazíte seznam změn do adresáře zdrojového kódu. Správa zdrojového kódu modulu plug-in poskytuje vlastní uživatelské rozhraní k zobrazení rozdíly.  
  
> [!NOTE]
>  Tato funkce používá stejné příznaky příkazu jako [SccDiff](../../extensibility/sccdiff-function.md). Jako modul plugin poskytovatele správy zdrojového kódu můžete se rozhodnout nebude podporovat operace "rychlý rozdílové" pro adresáře.  
  
## <a name="see-also"></a>Viz také  
 [Co je nového v zdroj ovládacího prvku modulu Plug-in rozhraní API verze 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)