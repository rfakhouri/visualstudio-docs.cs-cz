---
title: Nainstalujte Dotfuscatoru Community Edition (CE) | Microsoft Docs
ms.date: 2017-06-22
ms.devlang: dotnet
ms.technology: vs-ide-general
ms.topic: article
keywords: "Dotfuscatoru, Dotfuscatoru CE, preemptivní, preemptivní řešení preemptivní ochrana, ochrana, edice community, maskováním, .NET, volná, Visual Studio 2017 instalace"
helpviewer_keywords:
- PreEmptive Protection Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
- Dotfuscator
- obfuscation
- protection
- Dotfuscator installer
- Dotfuscator setup
- install Dotfuscator
- installing Dotfuscator
- set up Dotfuscator
description: "Informace o instalaci bezplatná edice Community Dotfuscatoru součástí Visual Studio 2017."
ms.assetid: f2146651-e24a-4e24-ade8-8ddee8ff4e43
author: Joe-Sewell-PreEmptive
manager: ghogen
ms.openlocfilehash: 6e3151a7ce26fcc998df7fbce1cefda54249a384
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="install-dotfuscator-community-edition-ce"></a>Nainstalujte Dotfuscatoru Community Edition (CE)

Visual Studio 2017 zavádí nové prostředí pro instalaci low impact fungovat.
V důsledku toho Dotfuscatoru Community Edition (Dotfuscatoru CE) není nainstalována ve výchozím nastavení.
Je však snadno nainstalovat Dotfuscatoru CE i v případě, že jste již nainstalovali Visual Studio.

> [!NOTE]
> Kromě verze Dotfuscatoru CE dodávané s verzemi sady Visual Studio preemptivní řešení taky pravidelně nabízí aktualizované verze na jeho Web.
> Pokud chcete stáhnout **nejnovější verzi** přímo místo instalace ze sady Visual Studio,  **[kliknutím sem přejděte na stránku stahování Dotfuscatoru] [ download]** .

## <a name="within-visual-studio"></a>V sadě Visual Studio

V prostředí Visual Studio IDE, můžete nainstalovat Dotfuscatoru CE:

1. V **Snadné spuštění** panelu Hledat (Ctrl + Q), typ `dotfuscator`. <br/> <br/> ![](media/install_from_vs_12.png) <br/> <br/>
2. V rychlé spuštění výsledky zobrazené v části *nainstalovat* záhlaví, vyberte **preemptivní ochrana – Dotfuscatoru (jednotlivé součásti)**.
  * Pokud jste místo toho najdete v části *nabídky* záhlaví, **nástroje - preemptivní ochrana – Dotfuscatoru**, pak Dotfuscatoru CE je již nainstalován. Podrobnosti využití najdete v tématu [stránce Začínáme v úplné uživatelské příručce CE Dotfuscatoru][get-started].
3. Visual Studio Instalační program, který se spustí okno, předem nakonfigurované s instalace Dotfuscatoru CE.
  * Může být nutné zadat přihlašovací údaje správce pokračujte.
4. Zavřete všechny instance Visual Studio IDE. <br/> <br/> ![](media/install_from_vs_345.png) <br/> <br/>
5. V okně Instalační program Visual Studio klikněte na *nainstalovat*.

Po dokončení instalace můžete začít používat Dotfuscatoru CE. Podrobnosti najdete v tématu [stránce Začínáme v úplné uživatelské příručce CE Dotfuscatoru][get-started].

## <a name="during-visual-studio-installation"></a>Při instalaci sady Visual Studio

Pokud jste ještě nenainstalovali Visual Studio 2017, můžete získat instalačního programu z [na webu sady Visual Studio][2017-install].
Při spuštění, zobrazí se možnosti instalace pro vybrané edice sady Visual Studio.

![](media/install_ui.png)

Dotfuscatoru CE můžete nainstalovat jako jednotlivé součást Visual Studio 2017:

1. Vyberte **jednotlivých součástí** kartě.
2. V části *Code nástroje*, zkontrolujte *preemptivní ochrana – Dotfuscatoru* položky.<br/> <br/> ![](media/install_individually_12.png) <br/> <br/>
3. *Souhrn* panelu zobrazí *preemptivní ochrana – Dotfuscatoru* pod *jednotlivých součástí* části. <br/> <br/> ![](media/install_individually_3.png) <br/> <br/>
4. Nakonfigurujte jakákoli další nastavení instalace jako vhodné pro vaše prostředí.
5. Až budete připraveni instalaci sady Visual Studio, klikněte na tlačítko *nainstalovat* tlačítko.

Po dokončení instalace můžete začít používat Dotfuscatoru CE. Podrobnosti najdete v tématu [stránce Začínáme v úplné uživatelské příručce CE Dotfuscatoru][get-started].

## <a name="see-also"></a>Viz také

[Toto téma v úplné Dotfuscatoru CE uživatelská příručka][full]

<!-- Copyright © 2017 PreEmptive Solutions, LLC -->

[2017-install]: https://www.visualstudio.com/downloads/#vs-2017
[get-started]: https://www.preemptive.com/dotfuscator/ce/docs/help/gui_getstarted.html

[download]: https://www.preemptive.com/products/dotfuscator/downloads

[full]: https://www.preemptive.com/dotfuscator/ce/docs/help/intro_install.html
