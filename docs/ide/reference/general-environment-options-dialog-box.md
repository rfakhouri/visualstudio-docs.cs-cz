---
title: Obecné, prostředí, dialogové okno Možnosti
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
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
- Visual Studio Start page, setting
- IDE, startup options
- editors, autocompletion
- Options dialog box, General Environment
- General Environment Options dialog box
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f12249cc8d0e8bd8396e1e1ebbbfefeddbb22b60
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31948126"
---
# <a name="general-environment-options-dialog-box"></a>Obecné, prostředí, dialogové okno Možnosti

Na této stránce můžete změnit barevné motivy, stav panelu nastavení a přiřazení přípony souboru, mezi další možnosti pro integrované vývojové prostředí (IDE). Dostanete **možnosti** dialogové okno otevřením **nástroje** nabídce Výběr **možnosti**, otevřete **prostředí** složku a potom Výběr **Obecné** stránky. Pokud tato stránka se nezobrazí v seznamu, vyberte **zobrazit všechna nastavení** zaškrtávací políčko **možnosti** dialogové okno.

> [!NOTE]
> Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, otevřete **nástroje** nabídce a potom zvolte **nastavení importu a exportu**. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).

## <a name="visual-experience"></a>Vizuální prostředí

**Barva motivu**

Vyberte **Blue**, **Light** nebo **tmavý** barevný motiv rozhraní IDE.

Můžete nainstalovat další předdefinované motivy a vytvořit vlastní motivy, stahuje a instaluje **Visual Studio barvu motivu editoru** z [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.VisualStudio2017ColorThemeEditor). Po instalaci tohoto nástroje se zobrazí další barevné motivy v seznamu Barva motivu.

**Použít název velká a malá písmena v řádku nabídek**

Nabídky jsou v **Title velká a malá písmena** ve výchozím nastavení. Zrušte výběr této možnosti je nastavena na **velká písmena**.

**Automaticky upravit visual prostředí založené na výkon klienta**

Určuje, zda Visual Studio úpravou automaticky nastaví na visual prostředí nebo explicitně nastavit úpravou. Tato úprava může změnit zobrazení barvy z přechody ploché barvy, ani ho může omezit použití animace v nabídkách nebo místní windows.

**Povolit plně funkčního klienta prostředí**

Umožňuje úplné visual prostředí sady Visual Studio, včetně přechody a animace. Při použití připojení ke vzdálené ploše nebo starší grafických adaptérů, protože tato funkce může dojít ke snížení výkonu v těchto případech, zrušte tuto možnost. Tato možnost je dostupná jenom v případě, že zrušíte výběr **automaticky upravit visual prostředí založené na klienta** možnost.

**Použít hardwarovou akceleraci grafiky, pokud je k dispozici**

Použije hardwarovou akceleraci grafiky, pokud je k dispozici, nikoli akcelerace softwaru.

## <a name="other"></a>Ostatní

**V nabídce okno zobrazené položky**

Přizpůsobí počet windows, které se zobrazují v seznamu Windows **okno** nabídky. Zadejte číslo mezi 1 a 24. Ve výchozím nastavení počet je 10.

**Položky zobrazené v seznamy naposledy použitých**

Přizpůsobí počet nedávno použité projekty a soubory, které se zobrazují na **souboru** nabídky. Zadejte číslo mezi 1 a 24. Ve výchozím nastavení počet je 10. Toto je snadný způsob, jak načíst nedávno použité projekty a soubory.

**Zobrazit stavový řádek**

Zobrazí stavový řádek. Stavový řádek je umístěn v dolní části okna IDE a zobrazí informace o průběhu probíhající operace.

**Tlačítko Zavřít ovlivňuje pouze okno active nástroje**

Určuje, kdy **Zavřít** po kliknutí na tlačítko, panel nástrojů, který má právě fokus, je uzavřený a ne všechny pouze nástroj Windows v sadě ukotveného. Ve výchozím nastavení je tato možnost vybrána.

**Skrýt tlačítko automaticky ovlivňuje pouze okno active nástroje**

Určuje, kdy **skrýt automaticky** po kliknutí na tlačítko, pouze panel nástrojů, který má právě fokus, je skrytý automaticky a není všechna okna nástrojů v sadě ukotveného. Ve výchozím nastavení tato možnost není vybraná.

## <a name="see-also"></a>Viz také

- [Prostředí, dialogové okno Možnosti](../../ide/reference/environment-options-dialog-box.md)
- [Přizpůsobení rozložení oken](../../ide/customizing-window-layouts-in-visual-studio.md)