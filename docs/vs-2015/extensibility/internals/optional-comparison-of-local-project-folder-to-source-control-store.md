---
title: Volitelné porovnání místní složky projektu do zdrojového ovládacího prvku Store | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control plug-ins, comparing versions
- source control plug-ins, local project folders
ms.assetid: 65217e8b-15a6-4446-92b0-4cff1c6220f5
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b6806a01127250b2376fee0aa77d55554eeba9bc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670279"
---
# <a name="optional-comparison-of-local-project-folder-to-source-control-store"></a>Volitelné porovnání místní složky projektu a úložiště správy zdrojového kódu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [porovnat složky projektu do zdrojového ovládacího prvku Store](https://docs.microsoft.com/visualstudio/extensibility/internals/optional-comparison-of-local-project-folder-to-source-control-store).  
  
Ve zdroji řízení porovnání mezi místní složce projektu a Správa zdrojového kódu se dá udělat pomocí funkce modulu Plug-in rozhraní API 1.2 [sccdirqueryinfo –](../../extensibility/sccdirqueryinfo-function.md) a [sccdirdiff –](../../extensibility/sccdirdiff-function.md).  
  
 V rámci **Průzkumníka řešení**, pokud je vybrána složka namísto jednotlivých souborů **porovnání verzí** vyvolá novou nabídku [sccdirqueryinfo –](../../extensibility/sccdirqueryinfo-function.md) a [ Sccdirdiff –](../../extensibility/sccdirdiff-function.md) v modulu plug-in správy zdrojového kódu.  
  
## <a name="new-capability-flags"></a>Nové příznaky funkcí  
 `SCC_CAP_DIRECTORYDIFF`  
  
 `SCC_CAP_DIRECTORYCHECKOUT`  
  
## <a name="new-functions"></a>Nové funkce  
 [Sccdirdiff –](../../extensibility/sccdirdiff-function.md)  
  
 [Sccdirqueryinfo –](../../extensibility/sccdirqueryinfo-function.md)  
  
 `SccDirQueryInfo` Funkce je volána před provedením `SccDirDiff` k určení, zda je v pracovním adresáři spravovanými zdroji. `SccDirDiff` Funkce zobrazí rozdíly mezi aktuálním místním adresáři a odpovídající složky správy zdrojového kódu. Tento příkaz zobrazí dotaz, chcete-li zobrazit seznam změn do adresáře, modul plug-in správy zdrojového kódu. Modul plug-in správy zdrojového kódu obsahuje vlastní uživatelské rozhraní pro zobrazení rozdílů.  
  
> [!NOTE]
>  Tato funkce využívá stejné příznaků příkazů jako [sccdiff –](../../extensibility/sccdiff-function.md). Jako poskytovatele správy zdrojového kódu modulu plug-in můžete operace "rychlé diff" pro adresáře není podporována.  
  
## <a name="see-also"></a>Viz také  
 [Co je nového v rozhraní API modulu plug-in správy zdrojového kódu ve verzi 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)

