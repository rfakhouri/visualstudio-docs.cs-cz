---
title: "Synchronizovat nastavení v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/23/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.ToolsOptionsPages.Environment.RoamingSettings
ms.assetid: a3d2ea29-be5d-4012-9820-44b06adbb7dd
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9d9c163063cfa4e2a78f8a07ab74efbecb355448
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="synchronize-your-settings-in-visual-studio"></a>Synchronizovat nastavení v sadě Visual Studio

Při přihlášení k sadě Visual Studio na několika počítačích pomocí stejného účtu, přizpůsobení, ve výchozím nastavení nastavení jsou synchronizovány do všech počítačů.

## <a name="synchronized-settings"></a>Synchronizovaná nastavení

Ve výchozím nastavení jsou synchronizovány následující nastavení.

- Nastavení pro vývoj (musíte vybrat sadu nastavení při prvním spuštění sady Visual Studio, ale můžete změnit výběr kdykoli. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).)

- Následující možnosti v **nástroje &#124; Možnosti** stránky:

    - **Motiv** a nabídky panelu velká a malá písmena nastavení, na **prostředí**, **Obecné** stránka Možnosti

    - Všechna nastavení na **prostředí**, **písma a barev** stránka Možnosti

    - Všechny klávesové zkratky, na **prostředí**, **klávesnice** stránka Možnosti

    - Všechna nastavení na **prostředí, karty a okna** stránka Možnosti

    - Všechna nastavení na **prostředí**, **spuštění** stránka Možnosti

    - Všechna nastavení na **textového editoru** možnosti stránky

    - Všechna nastavení na **návrháře XAML** možnosti stránky

- Aliasy příkazů definovaný uživatelem. Další informace o tom, jak definovat aliasy příkazů najdete v tématu [aliasy příkazů Visual Studio](../ide/reference/visual-studio-command-aliases.md).

- Rozložení oken uživatelem definované v **okno &#124; Spravovat rozložení oken** stránky

## <a name="turn-off-synchronized-settings-on-a-particular-computer"></a>Vypnout synchronizovaná nastavení v určitém počítači

Synchronizovaná nastavení pro sadu Visual Studio jsou ve výchozím nastavení zapnuté. Synchronizovaná nastavení v počítači můžete vypnout přechodem na **nástroje &#124; Možnosti &#124; Prostředí &#124; Synchronizovat nastavení** stránku a po zrušení zaškrtnutí políčka.  Například pokud se rozhodnete nechcete synchronizovat nastavení sady Visual Studio v počítači A jakékoli změny nastavení v počítači provedeny proveďte, nejsou zobrazeny na počítačích B nebo počítač C. počítačích B a C bude pokračovat k synchronizaci mezi sebou, ale není s počítačem A.

## <a name="synchronize-settings-across-visual-studio-family-products-and-editions"></a>Synchronizovat nastavení v sadě Visual Studio rodiny produktů a verzí

Nastavení lze synchronizovat mezi libovolná edice sady Visual Studio, včetně edice Community. Nastavení jsou také synchronizovány mezi produkty řady Visual Studio. Ale těchto rodiny produktů může mít svůj vlastní nastavení, které nejsou sdílet pomocí sady Visual Studio. Například nastavení, které jsou specifické pro jeden produkt v počítači A budou sdílet s jinou počítače b, ale ne pomocí sady Visual Studio v počítači A nebo B.

## <a name="side-by-side-synchronized-settings"></a>Synchronizovaná nastavení vedle sebe

Visual Studio 15.3 a novější, jsme jste zastavena, sdílení určitých nastavení, například rozložení okna nástroj, mezi různé instalace Visual Studio 2017 vedle sebe, tak, že změníte umístění `CurrentSettings.vssettings` v soubor `%userprofile%\Documents\Visual Studio 2017\Settings` do konkrétní instalace složky, která je podobná `%localappdata%\Microsoft\VisualStudio\15.0_xxxxxxxx\Settings`.

**Poznámka:**: Chcete-li použít nastavení specifická pro novou instalaci, musíte provést novou instalací. Když upgradujete existující instalaci sady Visual Studio 2017 na nejaktuálnější aktualizaci, použije se existující sdílené umístění. Pokud aktuálně máte vedle sebe instalace Visual Studio 2017 a rozhodnete upgradovat a chcete používat nové umístění souboru konkrétní nastavení instalace, postupujte takto:

1. Po dokončení upgradu, použijte Průvodce nastavení Import\Export naše stávající nastavení exportovat do některé umístění mimo `%localappdata%\Microsoft\VisualStudio\15.0_xxxxxxxx` složky.
2. Otevřete **příkazový řádek vývojáře pro VS 2017** upgradovaný instalaci sady Visual Studio a spustit `devenv /resetuserdata` z něj.
3. Spusťte sadu Visual Studio a naimportujte uložená nastavení ze souboru s vyexportovaným nastavením.

## <a name="see-also"></a>Viz také

[Přizpůsobení integrovaného vývojového prostředí](../ide/personalizing-the-visual-studio-ide.md)
