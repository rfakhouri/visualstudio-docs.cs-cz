---
title: Obecné, prostředí, dialogové okno Možnosti
ms.date: 03/28/2019
ms.topic: reference
f1_keywords:
- VS.Message.0x800a002e
- VS.ToolsOptionsPages.Environment.General
- VS.Environment.General
helpviewer_keywords:
- MRU lists
- windows, customizing
- MDI, environment options
- speed, environment animation
- File menu
- menus, customizing
- Windows menu customizing
- status bars, displaying
- IDE, startup options
- editors, autocompletion
- Options dialog box, General Environment
- General Environment Options dialog box
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4fdbd8c64514854aa77c358145badbf6583996f1
ms.sourcegitcommit: b14b7a938a2aba9fcce4d5e813aadf2040b0dcda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/29/2019
ms.locfileid: "58647268"
---
# <a name="options-dialog-box-environment--general"></a>Dialogové okno Možnosti: Prostředí \> obecné

Pomocí této stránky můžete změnit barevné motivy, nastavení panelu stavu a přidružení přípony souboru, mezi další možnosti pro integrované vývojové prostředí (IDE). Můžete přistupovat **možnosti** dialogové okno tak, že otevřete **nástroje** nabídku, zvolíte **možnosti**, otevřete **prostředí** složky a pak Výběr **Obecné** stránky. Pokud se tato stránka se nezobrazí v seznamu, vyberte **zobrazit všechna nastavení** zaškrtávací políčko **možnosti** dialogové okno.

## <a name="visual-experience"></a>Vzhled

**Barevný motiv**

Zvolte **modré**, **světla**, **tmavě**, nebo **modrý (zvláště kontrastní)** barvy motivu rozhraní IDE.

Můžete nainstalovat další předdefinované motivy a vytvářet vlastní motivy stažením a instalací **Editor motivů sady Visual Studio** z [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.VisualStudio2017ColorThemeEditor). Po instalaci tohoto nástroje, další barevné motivy joinkind **barevný motiv** pole se seznamem.

**Použít první velká písmena na řádku nabídek pro používání stylů**

Nabídky použijte mena všech slov velká ve výchozím nastavení pro používání stylů. Tuto možnost používat všechna velká písmena používání stylů pro místo, zrušte zaškrtnutí.

::: moniker range=">=vs-2019"

**Optimalizace vykreslování pro obrazovky s jinou densities – (vyžaduje restart)**

Tato možnost povolí nebo zakáže na monitorování bodů na palec (DPI) sledování (nebo *PMA*). Když je povolené PMA, uživatelské rozhraní sady Visual Studio se zobrazí zřetelný v jakékoli koeficient měřítka zobrazení monitorování a konfigurace DPI, včetně víc monitorů. Pokud chcete povolit PMA, je třeba Windows 10. dubna 2018 Update nebo novější a rozhraní .NET Framework 4,8 nebo novější. (Tato možnost se zobrazí šedě Pokud se nesplní tyto dva požadavky.)

::: moniker-end

**Automaticky upravit vzhled na základě výkonu klienta**

Určuje, zda sady Visual Studio úpravy automaticky nastaví na vizuální prostředí nebo explicitně nastavit úpravy. Toto nastavení může změnit zobrazení barvy z přechody pro plochý barev, nebo to může omezit použití animací v nabídkách nebo automaticky otevíraného okna windows.

**Povolit vzhled plně funkčního klienta**

Poskytuje možnost celý vizuální prostředí sady Visual Studio, včetně přechody a animace. Při použití připojení ke vzdálené ploše nebo starší grafických adaptérů, protože tyto funkce může dojít ke snížení výkonu v těchto případech, zrušte tuto možnost. Tato možnost je dostupná jenom v případě, že zrušíte výběr **automaticky upravit vzhled na základě klienta** možnost.

**Použít hardwarovou akceleraci grafiky, pokud je k dispozici**

Používá hardwarovou akceleraci grafiky, pokud je k dispozici, nebo softwarové akcelerace.

## <a name="other"></a>Ostatní

**Položky, které chcete zobrazit v nabídce okno**

Přizpůsobí počet období, která se zobrazí v seznamu Windows **okno** nabídky. Zadejte číslo mezi 1 a 24. Výchozí hodnota je 10.

**Počet položek zobrazovaných v seznamech**

Přizpůsobí počet naposledy použitých projekty a soubory, které se zobrazují na **souboru** nabídky. Zadejte číslo mezi 1 a 24. Výchozí hodnota je 10. Toto je snadný způsob, jak načíst nedávno použité projekty a soubory.

**Zobrazit stavový řádek**

Zobrazí stavový řádek. Stavový řádek je umístěn na spodní části okna IDE a zobrazí informace o průběhu probíhající operace.

**Tlačítko Zavřít ovlivní pouze aktivní okno nástrojů**

Určuje, kdy **Zavřít** po kliknutí na tlačítko, jen pro okno nástroje, který má právě fokus, je uzavřený a ne všechny oken nástrojů ukotvených v sadě. Ve výchozím nastavení je tato možnost vybrána.

**Automaticky skrýt ovlivní pouze aktivní okno nástrojů**

Určuje, kdy **automaticky skrýt** po kliknutí na tlačítko, pouze panel nástrojů, který má právě fokus, je skrytý automaticky a nikoli všech oken nástrojů ukotvených v sadě. Ve výchozím nastavení tato možnost není vybraná.

## <a name="see-also"></a>Viz také:

- [Prostředí, dialogové okno Možnosti](../../ide/reference/environment-options-dialog-box.md)
- [Přizpůsobení rozložení oken](../../ide/customizing-window-layouts-in-visual-studio.md)