---
title: "Ukládání informací o symbolech s datovými soubory výkonu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- packsymbols, in profiling tools reports
- profiling tools, packsymbols
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c92373294392dcbf78e57c096f40b0de5d63291a
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2018
---
# <a name="saving-symbol-information-with-performance-data-files"></a>Ukládání informací o symbolech s datovými soubory výkonu

Pokud používáte Visual Studio IDE pro analýzu souborů a máte v úmyslu přesunout soubor VSP do jiného počítače, je nutné nastavit výkon nastavení projektu pro uložení nebo *serializovat* symboly v souboru sestavy. Tím se zvyšuje velikost souboru sestavy. Serializace symboly je třeba dvou důvodů:

- Pro vložení kódu symboly do sestavy výkonu před cíl sestavení jsou ztraceny z umístění v dočasné úložiště.

- Chcete-li zachovat symboly, tak, aby sestava výkonu je přenosný z PROFILOVANÉHO počítače a výstupy stejné informace, pokud sestava je otevřen pro analýzu v jiném počítači, který může mít různé symboly.

Může serializovat symboly v prostředí Visual Studio IDE, nebo z příkazového řádku:

- K serializaci symboly v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE, přejděte na příkaz **nástroje** na řádku nabídek a pak klikněte na tlačítko **možnosti**. V **možnosti** vyberte **nástroje pro sledování výkonu**a pak vyberte **automaticky serializace informací o symbolu** zaškrtávací políčko.

- PACKSYMBOLS je ekvivalentní možnost příkazového řádku při ukládání souborů sestav. K serializaci symboly, zadejte **vsperfreport – /summary:all /packsymbols filename.vsp**.

## <a name="troubleshooting-symbol-problems"></a>Řešení potíží – Symbol

Pokud se nezobrazí žádné symboly v kódu, některá běžná řešení jsou k dispozici:

- /Debugsympath vsperfreport – spusťte v příkazovém řádku, chcete-li zobrazit úplný seznam umístění, kde jsou komponenty profileru načítání informací o symbolu a zda odpovídají symbol soubory, které se používají soubory, které používá váš projekt.

- Ujistěte se, že spustíte vsperfreport – s příznakem /PACKSYMBOLS nebo v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrovaného vývojového prostředí, které máte možnost serializace symbol informace vybraný v možnostech explorer obecný výkon.

- Pokud jste shromáždili data typu, přidejte na příkazový řádek vsperfreport – /SUMMARY:TYPE.

 Pokud nevidíte symboly ze systému Windows nebo další programy společnosti Microsoft:

- Ujistěte se, že jste si nastavili cestu symbol mezipaměti systému Windows. Proveďte jednu z následujících způsobů nastavit cestu k mezipaměti symbol:

  - Sada ladicí program -> symboly v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE na správnou cestu.

  - Přidejte přepínač - symbolpath – k vsperfreport – příkazový řádek, který obsahuje vaše symboly.

- Pokud nevidíte všechny symboly v [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], ujistěte se, že máte symbol serveru pro ASP server správně nastaveny.

## <a name="repacking-symbols"></a>Opětovné symboly

Pokud chcete znovu zabalí symboly do sestavy, můžete to provést pomocí nástroje příkazového řádku vsperfreport –. Pomocí následujících příkazových řádků:

Vsperfreport – - clearpackedsymbols filename.vsp

Vsperfreport – - packsymbols – souhrn: všechny filename.vsp

## <a name="see-also"></a>Viz také

[Ukládání a export výkonu nástrojů pro Data](../profiling/saving-and-exporting-performance-tools-data.md)  
[Postupy: referenční informace o symbolech Windows](../profiling/how-to-reference-windows-symbol-information.md)  
[VSPerfReport](../profiling/vsperfreport.md)