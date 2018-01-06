---
title: "Ukládání informací o symbolech s datovými soubory výkonu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- packsymbols, in profiling tools reports
- profiling tools, packsymbols
ms.assetid: 8b802505-e94d-4ee0-83e4-fdd790a332c1
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: dd963c269ee5fe18d3f490bf85bab5dcf3afbf9a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="saving-symbol-information-with-performance-data-files"></a>Ukládání informací o symbolech s datovými soubory výkonu
Pokud používáte [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE) k analýze souborů a plánování přesunutí souboru VSP do jiného počítače, musíte nastavit výkon nastavení projektu pro uložení nebo *serializovat* symboly v váš soubor sestavy. Tím se zvyšuje velikost souboru sestavy. Serializace symboly je třeba dvou důvodů:  
  
-   Pro vložení kódu symboly do sestavy výkonu před cíl sestavení jsou ztraceny z umístění v dočasné úložiště.  
  
-   Chcete-li zachovat symboly, tak, aby sestava výkonu je přenosný z PROFILOVANÉHO počítače a výstupy stejné informace, pokud sestava je otevřen pro analýzu v jiném počítači, který může mít různé symboly.  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 Může serializovat symboly z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE nebo z příkazového řádku:  
  
-   K serializaci symboly v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE, přejděte na příkaz **nástroje** na řádku nabídek a pak klikněte na tlačítko **možnosti**. V **možnosti** vyberte **nástroje pro sledování výkonu**a pak vyberte **automaticky serializace informací o symbolu** zaškrtávací políčko.  
  
-   PACKSYMBOLS je ekvivalentní možnost příkazového řádku při ukládání souborů sestav. K serializaci symboly, zadejte **vsperfreport – /summary:all /packsymbols filename.vsp**.  
  
## <a name="troubleshooting-symbol-problems"></a>Řešení potíží – Symbol  
 Pokud se nezobrazí žádné symboly v kódu, některá běžná řešení jsou k dispozici:  
  
-   /Debugsympath vsperfreport – spusťte v příkazovém řádku, chcete-li zobrazit úplný seznam umístění, kde jsou komponenty profileru načítání informací o symbolu a zda odpovídají symbol soubory, které se používají soubory, které používá váš projekt.  
  
-   Ujistěte se, že spustíte vsperfreport – s příznakem /PACKSYMBOLS nebo v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrovaného vývojového prostředí, které máte možnost serializace symbol informace vybraný v možnostech explorer obecný výkon.  
  
-   Pokud jste shromáždili data typu, přidejte na příkazový řádek vsperfreport – /SUMMARY:TYPE.  
  
 Pokud nevidíte symboly ze systému Windows nebo další programy společnosti Microsoft:  
  
-   Ujistěte se, že jste si nastavili cestu symbol mezipaměti systému Windows. Proveďte jednu z následujících způsobů nastavit cestu k mezipaměti symbol:  
  
    -   Sada ladicí program -> symboly v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE na správnou cestu.  
  
    -   Přidejte přepínač - symbolpath – k vsperfreport – příkazový řádek, který obsahuje vaše symboly.  
  
-   Pokud nevidíte všechny symboly v [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], ujistěte se, že máte symbol serveru pro ASP server správně nastaveny.  
  
## <a name="repacking-symbols"></a>Opětovné symboly  
 Pokud chcete znovu zabalí symboly do sestavy, můžete to provést pomocí nástroje příkazového řádku vsperfreport –. Pomocí následujících příkazových řádků:  
  
 Vsperfreport – - clearpackedsymbols filename.vsp  
  
 Vsperfreport – - packsymbols – souhrn: všechny filename.vsp  
  
## <a name="see-also"></a>Viz také  
 [Ukládání a export výkonu nástrojů pro Data](../profiling/saving-and-exporting-performance-tools-data.md)   
 [Postupy: referenční informace o symbolech Windows](../profiling/how-to-reference-windows-symbol-information.md)   
 [VSPerfReport](../profiling/vsperfreport.md)