---
title: Ukládá informace o symbolech s datových souborů výkonu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- packsymbols, in profiling tools reports
- profiling tools, packsymbols
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0bf78c94f8982af78d0f393c9cb5b878bef27d87
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62939505"
---
# <a name="saving-symbol-information-with-performance-data-files"></a>Ukládání informací o symbolech s datových souborů výkonu

Pokud používáte Visual Studio IDE pro analýzu souborů a máte v úmyslu přesunout soubor VSP do jiného počítače, je nutné nastavit výkon nastavení projektu a uložit nebo *serializovat* symbolů v souboru sestavy. Tím se zvyšuje velikost souboru sestavy. Serializaci symbolů je nezbytný dvou důvodů:

- Pro vložení kódu symboly do sestavy výkonu než cílová sestavení jsou ztraceny z umístění dočasného úložiště.

- Chcete-li zachovat symboly, tak, aby sestava výkonu je přenosný z PROFILOVANÉHO počítače a vypíše stejné informace, pokud otevření sestavy pro analýzu v jiném počítači, který může mít různé symboly.

Může serializovat symboly z integrovaného vývojového prostředí sady Visual Studio nebo z příkazového řádku:

- Pro serializaci symbolů v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrovaného vývojového prostředí, přejděte na příkaz **nástroje** na řádku nabídek a pak klikněte na tlačítko **možnosti**. V **možnosti** okně **nástroje pro měření výkonu**a pak vyberte **automaticky serializovat informace o symbolech** zaškrtávací políčko.

- PACKSYMBOLS je ekvivalentní možnosti příkazového řádku při ukládání souborů sestav. Pro serializaci symbolů, zadejte **vsperfreport Summary/packsymbols filename.vsp**.

## <a name="troubleshooting-symbol-problems"></a>Řešení potíží se Symbol

Pokud nevidíte všechny symboly ve svém vlastním kódu, některá běžná řešení jsou k dispozici:

- Spusťte vsperfreport/debugsympath příkazového řádku zobrazíte úplný seznam umístění, kde profiler součásti načítání informací o symbolu a zda porovnat soubory symbolů, které se používají soubory, které používá váš projekt.

- Ujistěte se, že spustíte vsperfreport s příznakem/packsymbols nebo v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrovaného vývojového prostředí, které máte možnost serializace symbolu informace vybraný v možnostech explorer obecné informace o výkonu.

- Pokud jste shromáždili typ dat, přidejte na příkazový řádek vsperfreport /SUMMARY:TYPE.

  Pokud nevidíte symboly z Windows nebo další programy společnosti Microsoft:

- Ujistěte se, že jste nastavili cestu k mezipaměti symbolů Windows. Proveďte jednu z následujících nastavení cesty k symbolu mezipaměti:

  - Sada ladicí program -> symboly – možnost v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí na správnou cestu.

  - Symbolpath – možnost přidáte k příkazovému řádku VSPerfReport zahrnout symboly.

- Pokud nevidíte všechny symboly v [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], ujistěte se, že máte správně nastavené pro ASP server server symbolů.

## <a name="repacking-symbols"></a>Opětovné balení symbolů

Pokud chcete který znovu zabalí symboly do sestavy, můžete to provést pomocí příkazového řádku nástroje VsPerfReport. Pomocí následujících příkazových řádků:

VsPerfReport – clearpackedsymbols filename.vsp

VsPerfReport – packsymbols-summary: all filename.vsp

## <a name="see-also"></a>Viz také:

[Ukládání a export výkonu nástroje Data](../profiling/saving-and-exporting-performance-tools-data.md)
[jak: Informace o symbolech Windows odkaz](../profiling/how-to-reference-windows-symbol-information.md)
[VSPerfReport](../profiling/vsperfreport.md)