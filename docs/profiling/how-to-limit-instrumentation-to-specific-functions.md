---
title: "Postupy: omezení instrumentace na konkrétní funkce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance tools, limiting instrumentation to functions
ms.assetid: bd98d6bf-2560-4eba-b063-2facb09f87c4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 69cc476dc43562e5226ebd6564dfb2733f1d57ae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-limit-instrumentation-to-specific-functions"></a>Postupy: Omezení instrumentace na konkrétní funkce
Instrumentace a shromažďování dat pro jednu nebo více funkcí můžete omezit nastavením možností v **Upřesnit** stránky **výkonnostní relace** nebo cílení binární vlastnosti stránky:  
  
-   Pokud zadáte na stránce vlastností relace výkonu funkce, pouze tyto funkce jsou vybaveny v instrumentované binární soubory relace.  
  
-   Pokud zadáte funkce na stránce vlastností cíli binární, pouze funkce, které jsou v tom, že jsou vybaveny konkrétní binární. Funkce v jiných binární soubory výkonu jsou vybaveny jako obvykle.  
  
 Omezení shromažďování dat tímto způsobem je podporovaná jenom v případě, že je vybraná metoda profilování instrumentace.  
  
> [!NOTE]
>  Můžete také **Upřesnit** stránky **výkonnostní relace** stránky vlastností nastavit další možnosti, které jsou k dispozici na nástrojích pro profilaci [vsinstr –](../profiling/vsinstr.md) příkazového řádku Nástroj instrumentace.  
  
### <a name="to-limit-instrumentation-to-specific-functions-in-a-performance-session"></a>K omezení instrumentace na konkrétní funkce v výkonnostní relace  
  
1.  V **prohlížeč výkonu**, klikněte pravým tlačítkem na název relace a pak klikněte na tlačítko **vlastnosti**.  
  
     **Stránky vlastností** se zobrazí dialogové okno.  
  
2.  Na **stránky vlastností** dialogové okno, klikněte na tlačítko **Upřesnit**.  
  
3.  V **dalších možností instrumentace** textové pole, použijte tuto syntaxi a zadejte název funkce, které chcete nástrojích:  
  
     **/ include:** `FuncSpec` **[;** `FuncSpec` **]**`...`  
  
     `FuncSpec`je název oboru názvů a funkce. Má formát `Namespace` **::**`FunctionName`. K oddělení více funkcí použijte středník. Pomocí hvězdičky (\*) k určení zástupný znak pro jeden nebo více znaků. Například **/ include: MyNS::\***  Určuje všechny funkce v oboru názvů MyNS.  
  
    > [!NOTE]
    >  Pro zobrazení seznamu funkcí v binární, otevřete okno příkazového řádku v nástrojích pro profilaci instalační adresář (obvykle adresáře nástroje \Team Tools\Performance pod [!INCLUDE[vsprvsts](../code-quality/includes/vsprvsts_md.md)] instalační adresář) a pak zadejte **vsinstr – / DumpFuncs**  
  
### <a name="to-limit-instrumentation-to-specific-functions-in-a-binary"></a>K omezení instrumentace na konkrétní funkce v binárním  
  
1.  V **prohlížeč výkonu**, vyhledejte v binární název **cíle** uzlu výkonnostní relace.  
  
2.  Klikněte pravým tlačítkem na název v binárním formátu a potom klikněte na **vlastnosti**.  
  
     **Stránky vlastností** se zobrazí dialogové okno.  
  
3.  Na **stránky vlastností** dialogové okno, klikněte na tlačítko **Upřesnit**.  
  
4.  V **dalších možností instrumentace** textové pole, použijte tuto syntaxi a zadejte název funkce, které chcete nástrojích:  
  
     **/ include:** `FuncSpec` **[;** `FuncSpec` **]**`...`  
  
     `FuncSpec`je název oboru názvů a funkce. Má formát `Namespace` **::**`FunctionName`. K oddělení více funkcí použijte středník. Pomocí hvězdičky (\*) k určení zástupný znak pro jeden nebo více znaků. Například **/ include: MyNS::\***  Určuje všechny funkce v oboru názvů MyNS.  
  
    > [!NOTE]
    >  Pro zobrazení seznamu funkcí v binární, otevřete okno příkazového řádku v nástrojích pro profilaci instalační adresář (obvykle adresáře nástroje \Team Tools\Performance pod [!INCLUDE[vsprvsts](../code-quality/includes/vsprvsts_md.md)] instalační adresář) a pak zadejte **vsinstr – / DumpFuncs**  
  
## <a name="see-also"></a>Viz také  
 [Řízení shromažďování dat](../profiling/controlling-data-collection.md)   
 [Postupy: omezení instrumentace na konkrétní knihovny DLL](../profiling/how-to-limit-instrumentation-to-specific-dlls.md)   
 [Postupy: určení dalších možností instrumentace](../profiling/how-to-specify-additional-instrumentation-options.md)