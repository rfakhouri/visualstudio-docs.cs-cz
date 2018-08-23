---
title: 'Postupy: omezení instrumentace na konkrétní funkce | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance tools, limiting instrumentation to functions
ms.assetid: bd98d6bf-2560-4eba-b063-2facb09f87c4
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ab089bd02fafc4dc711fa01c49a9690bbd9f6a65
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672063"
---
# <a name="how-to-limit-instrumentation-to-specific-functions"></a>Postupy: Omezení instrumentace na konkrétní funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: omezení instrumentace na konkrétní funkce](https://docs.microsoft.com/visualstudio/profiling/how-to-limit-instrumentation-to-specific-functions).  
  
Instrumentace a shromažďování dat na jeden nebo více funkcí můžete omezit tím, že nastavíte možnosti **Upřesnit** stránku **relace výkonu** nebo cílové stránky binárních vlastností:  
  
-   Pokud zadáte na stránce vlastností relace výkonu funkce, jsou podporovány pouze funkce, v instrumentovaných binárních souborů relace.  
  
-   Pokud zadáte na stránce vlastností cílový binární soubor funkce, pouze funkce, které jsou v tom, že jsou instrumentovány konkrétní binární soubor. Funkce v jiných binárních souborů výkonu jsou podporovány jako obvykle.  
  
 Limitující kolekce dat tímto způsobem je podporována pouze v případě, že je vybraná metoda profilace instrumentace.  
  
> [!NOTE]
>  Můžete také použít **Upřesnit** stránku **relace výkonu** stránky vlastností pro nastavení Další možnosti, které jsou k dispozici pro nástroje pro profilaci [VSInstr](../profiling/vsinstr.md) příkazového řádku Nástroj instrumentace.  
  
### <a name="to-limit-instrumentation-to-specific-functions-in-a-performance-session"></a>K omezení instrumentace na konkrétní funkce během relace výkonu  
  
1.  V **prohlížeč výkonu**, klikněte pravým tlačítkem na název relace a potom klikněte na tlačítko **vlastnosti**.  
  
     **Stránky vlastností** se zobrazí dialogové okno.  
  
2.  Na **stránky vlastností** dialogové okno, klikněte na tlačítko **Upřesnit**.  
  
3.  V **dalších možností instrumentace** textové pole, použijte následující syntax k zadání názvu funkce, které chcete instrumentovat:  
  
     **/ include:** `FuncSpec` **[;** `FuncSpec` **]** `...`  
  
     `FuncSpec` je název oboru názvů a funkce. Má formát `Namespace` **::**`FunctionName`. K oddělení více funkcí použijte středník. Použijte hvězdičku (\*) Chcete-li zadat zástupný znak pro jeden nebo více znaků. Například **/ include: MyNS::\***  Určuje všechny funkce v oboru názvů MyNS.  
  
    > [!NOTE]
    >  Seznam funkcí v binární soubor, otevřete okno příkazového řádku v instalačním adresáři nástroje pro profilaci (obvykle adresář nástrojů \Team Tools\Performance pod [!INCLUDE[vsprvsts](../includes/vsprvsts-md.md)] instalační adresář) a pak zadejte **vsinstr / DumpFuncs**  
  
### <a name="to-limit-instrumentation-to-specific-functions-in-a-binary"></a>K omezení instrumentace na konkrétní funkce v binární soubor  
  
1.  V **prohlížeč výkonu**, vyhledejte binární název v **cíle** uzlu relace výkonu.  
  
2.  Klikněte pravým tlačítkem na název v binárním a potom klikněte na tlačítko **vlastnosti**.  
  
     **Stránky vlastností** se zobrazí dialogové okno.  
  
3.  Na **stránky vlastností** dialogové okno, klikněte na tlačítko **Upřesnit**.  
  
4.  V **dalších možností instrumentace** textové pole, použijte následující syntax k zadání názvu funkce, které chcete instrumentovat:  
  
     **/ include:** `FuncSpec` **[;** `FuncSpec` **]** `...`  
  
     `FuncSpec` je název oboru názvů a funkce. Má formát `Namespace` **::**`FunctionName`. K oddělení více funkcí použijte středník. Použijte hvězdičku (\*) Chcete-li zadat zástupný znak pro jeden nebo více znaků. Například **/ include: MyNS::\***  Určuje všechny funkce v oboru názvů MyNS.  
  
    > [!NOTE]
    >  Seznam funkcí v binární soubor, otevřete okno příkazového řádku v instalačním adresáři nástroje pro profilaci (obvykle adresář nástrojů \Team Tools\Performance pod [!INCLUDE[vsprvsts](../includes/vsprvsts-md.md)] instalační adresář) a pak zadejte **vsinstr / DumpFuncs**  
  
## <a name="see-also"></a>Viz také  
 [Řízení sběru dat](../profiling/controlling-data-collection.md)   
 [Postupy: omezení instrumentace na konkrétní knihovny DLL](../profiling/how-to-limit-instrumentation-to-specific-dlls.md)   
 [Postupy: určení dalších možností instrumentace](../profiling/how-to-specify-additional-instrumentation-options.md)



