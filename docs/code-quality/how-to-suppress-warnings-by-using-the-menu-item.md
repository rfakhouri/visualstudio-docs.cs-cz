---
title: "Postupy: potlačení upozornění použitím položky nabídky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- warnings, suppressing
- code analysis, suppressing warnings
ms.assetid: 36bd1850-dcde-4ed0-9bc3-0b83df434362
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5ce2369b5b97f1767a17686d3de2d4127150c05d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-suppress-warnings-by-using-the-menu-item"></a>Postupy: Potlačení upozornění použitím položky nabídky
> [!NOTE]
>  Ve zdroji potlačení nepodporuje pro webové projekty.  
  
 Okno analýzy kódu můžete použít k potlačení upozornění analýzy kódu. Potlačení upozornění není stejný jako jeho zakázání. Když je potlačit upozornění, vztahuje se pouze na konkrétní instanci porušení zásady. Další porušení stejné upozornění se ohlásí stále v okně Seznam chyb.  
  
 Po spuštění analýzy kódu může určit, že jeden nebo více upozornění analýzy kódu, které se zobrazují v okně nástroje Analýza kódu neplatí pro aplikace. Například může určit, zda je správný, jako je kód. Nebo ji může být v případě, že některé porušení s nízkou prioritou a není určena v aktuální cyklu vývoje. Bez ohledu na důvod, proč je často užitečné znamenat, že upozornění umožníte členové týmu vědět, že byl přečetli kód a aby bylo zjištěno, že může potlačit upozornění nepoužitelné. Ve zdroji potlačení je užitečné, protože vám umožňuje umístit potlačení blízko nichž se vyvolá upozornění.  
  
 Můžete vybrat, zda se ve zdrojovém kódu nebo v souboru globální potlačení zobrazí potlačení. Některé suppressions musí být umístěny v souboru globální potlačení. Pokud ano, **zdroje v** možnost vypnuta.  
  
### <a name="to-suppress-a-warning-by-using-menu-item"></a>K potlačení upozornění použitím položky nabídky  
  
1.  Na **analyzovat** nabídce zvolte **Windows** a potom zvolte **analýza kódu**.  
  
2.  V **analýza kódu** okně vyberte potlačit upozornění.  
  
3.  Zvolte Akce, a potom vyberte **potlačit zprávy**a potom vyberte buď **zdroje v** nebo **v souboru projektu potlačení**.  
  
     Upozornění na konkrétní potlačeno a toto upozornění se zobrazí v okně Analýza kódu s přeškrtnutí.  
  
> [!NOTE]
>  V souboru globální potlačení zobrazí suppressions, které nemají atribut target.