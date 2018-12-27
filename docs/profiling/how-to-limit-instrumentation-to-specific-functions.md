---
title: 'Postupy: Omezení instrumentace na konkrétní funkce | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- performance tools, limiting instrumentation to functions
ms.assetid: bd98d6bf-2560-4eba-b063-2facb09f87c4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e145a50c3fdb643affb67989ae11346bf7e30f9
ms.sourcegitcommit: 34840a954ed3446c789e80ee87da6cbf1203cbb5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/18/2018
ms.locfileid: "53592856"
---
# <a name="how-to-limit-instrumentation-to-specific-functions"></a>Postupy: Omezení instrumentace na konkrétní funkce
Instrumentace a shromažďování dat na jeden nebo více funkcí můžete omezit tím, že nastavíte možnosti **Upřesnit** stránku **relace výkonu** nebo cílové stránky binárních vlastností:  
  
- Pokud zadáte na stránce vlastností relace výkonu funkce, jsou podporovány pouze funkce, v instrumentovaných binárních souborů relace.  
  
- Pokud zadáte na stránce vlastností cílový binární soubor funkce, pouze funkce, které jsou v tom, že jsou instrumentovány konkrétní binární soubor. Funkce v jiných binárních souborů výkonu jsou podporovány jako obvykle.  
  
  Limitující kolekce dat tímto způsobem je podporována pouze v případě, že je vybraná metoda profilace instrumentace.  
  
> [!NOTE]
>  Můžete také použít **Upřesnit** stránku **relace výkonu** stránky vlastností pro nastavení Další možnosti, které jsou k dispozici pro nástroje pro profilaci [VSInstr](../profiling/vsinstr.md) příkazového řádku Nástroj instrumentace.  
  
### <a name="to-limit-instrumentation-to-specific-functions-in-a-performance-session"></a>K omezení instrumentace na konkrétní funkce během relace výkonu  
  
1. V **prohlížeč výkonu**, klikněte pravým tlačítkem na název relace a potom klikněte na tlačítko **vlastnosti**.  
  
    **Stránky vlastností** se zobrazí dialogové okno.  
  
2. Na **stránky vlastností** dialogové okno, klikněte na tlačítko **Upřesnit**.  
  
3. V **dalších možností instrumentace** textové pole, použijte následující syntax k zadání názvu funkce, které chcete instrumentovat:  
  
    **/ include:** `FuncSpec` **[;** `FuncSpec` **]** `...`  
  
    `FuncSpec` je název oboru názvů a funkce. Má formát `Namespace` **::**`FunctionName`. K oddělení více funkcí použijte středník. Použijte hvězdičku (\*) Chcete-li zadat zástupný znak pro jeden nebo více znaků. Například **/ include: MyNS::\\*** Určuje všechny funkce v oboru názvů MyNS.  
  
   > [!NOTE]
   >  Seznam funkcí v binární soubor, otevřete okno příkazového řádku v instalačním adresáři nástroje pro profilaci (naleznete v tématu [zadejte cestu k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)) a pak zadejte **vsinstr /DumpFuncs**  
  
### <a name="to-limit-instrumentation-to-specific-functions-in-a-binary"></a>K omezení instrumentace na konkrétní funkce v binární soubor  
  
1. V **prohlížeč výkonu**, vyhledejte binární název v **cíle** uzlu relace výkonu.  
  
2. Klikněte pravým tlačítkem na název v binárním a potom klikněte na tlačítko **vlastnosti**.  
  
    **Stránky vlastností** se zobrazí dialogové okno.  
  
3. Na **stránky vlastností** dialogové okno, klikněte na tlačítko **Upřesnit**.  
  
4. V **dalších možností instrumentace** textové pole, použijte následující syntax k zadání názvu funkce, které chcete instrumentovat:  
  
    **/ include:** `FuncSpec` **[;** `FuncSpec` **]** `...`  
  
    `FuncSpec` je název oboru názvů a funkce. Má formát `Namespace` **::**`FunctionName`. K oddělení více funkcí použijte středník. Použijte hvězdičku (\*) Chcete-li zadat zástupný znak pro jeden nebo více znaků. Například **/ include: MyNS::\\*** Určuje všechny funkce v oboru názvů MyNS.  
  
   > [!NOTE]
   >  Seznam funkcí v binární soubor, otevřete okno příkazového řádku v instalačním adresáři nástroje pro profilaci (naleznete v tématu [zadejte cestu k nástrojům příkazového řádku](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)) a pak zadejte **vsinstr /DumpFuncs**  
  
## <a name="see-also"></a>Viz také:  
 [Řízení shromažďování dat](../profiling/controlling-data-collection.md)   
 [Postupy: Omezení instrumentace na konkrétní knihovny DLL](../profiling/how-to-limit-instrumentation-to-specific-dlls.md)   
 [Postupy: Určení dalších možností instrumentace](../profiling/how-to-specify-additional-instrumentation-options.md)