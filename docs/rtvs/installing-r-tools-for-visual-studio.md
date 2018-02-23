---
title: "Instalace nástrojů R pro sadu Visual Studio | Microsoft Docs"
description: "Postup instalace R nástrojů pro Visual Studio ve Visual Studio 2017 a Visual Studio 2015, včetně offline instalace."
ms.custom: 
ms.date: 01/24/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
ms.tgt_pltfrm: 
dev_langs:
- R
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: 76dc2623edebed6cca48c40c0ad0bc96f783e39d
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2018
---
# <a name="how-to-install-r-tools-for-visual-studio"></a>Postup instalace R nástrojů pro Visual Studio

V tomto článku:

- [Podporované verze sady Visual Studio](#supported-versions-of-visual-studio)
- [Instalace RTVS v Visual Studio 2017](#installing-rtvs-in-visual-studio-2017)
- [Instalace RTVS ve Visual Studiu 2015](#installing-rtvs-in-visual-studio-2015)
- [Offline instalace](#offline-installation-of-visual-studio-and-rtvs)

> [!Note]
> Po instalaci nástrojů pro R, můžete chtít nakonfigurovat Visual Studio rozložení vědecký pracovník optimalizovaná data, jak je popsáno na [možnosti](options-for-r-tools-in-visual-studio.md) článku.

## <a name="supported-versions-of-visual-studio"></a>Podporované verze sady Visual Studio

R nástrojů pro Visual Studio (RTVS) je podporována v systému Windows se Community (zdarma), Professional a verze Enterprise Edition obou [Visual Studio 2017](https://www.visualstudio.com/downloads/) a [Visual Studio 2015 Update 3 (nebo vyšší)](http://go.microsoft.com/fwlink/?LinkId=691129) (přímé ke stažení).

RTVS není podporována v současné době v sadě Visual Studio for Mac.

RTVS nenainstaluje, pokud máte pouze prostředí sady Visual Studio, který je součástí produkty například Visual Studio Test Professional a SQL Server Management Studio. Prostředí sady Visual Studio chybí komponenty potřebné pro RTVS.

## <a name="installing-rtvs-in-visual-studio-2017"></a>Instalace RTVS v Visual Studio 2017

1. Spusťte instalační program sady Visual Studio. (Viz [stáhne](https://www.visualstudio.com/downloads/) Pokud ještě nemáte nainstalovanou sadu Visual Studio.) Ve Windows 7, ujistěte se, že instalačním programem vaší aktualizována na verzi Visual Studio 2017 *15.2 sestavení 26430.12* nebo novější.

1. Vyberte **vědecké zpracování dat a analytických aplikací** zatížení:

    ![Vědecké zpracování dat a aplikací pro uchovávání zatížení v VS2017](media/installation-data-science-workload.png)

1. Nastavte další možnosti na pravé straně pod stejným názvem úlohy. Ve výchozím nastavení zahrnuje tato zatížení F # a podporují Python. Pro R, jsou minimální požadavky **podporu jazyka R**, **podporu Runtime pro vývoj R**, a **klienta Microsoft R**.

Je nainstalovaný RTVS: `%ProgramFiles(x86)%\Microsoft Visual Studio\<version>\<edition>Common7\IDE\Extensions\Microsoft\R Tools for Visual Studio` kde `<version>` je obvykle `2017` a `<edition>` je `Community`, `Professional`, nebo `Enterprise`.

## <a name="installing-rtvs-in-visual-studio-2015"></a>Instalace RTVS ve Visual Studiu 2015

S Visual Studiem 2015 budete muset překladač R a nástroje R instalovat samostatně.

### <a name="install-an-r-interpreter"></a>Nainstalujte překladač R

RTVS vyžaduje instalaci 64-bit R verze 3.2.1 nebo vyšší z jedné nebo více z těchto zdrojů:

- [Otevřete Microsoft R](https://mran.microsoft.com/download/)
- [Microsoft R klienta](/machine-learning-server/r-client/what-is-microsoft-r-client)
- [CRAN R.](https://cran.r-project.org/bin/windows/base/)

Microsoft R otevřete i CRAN r. povolit pro více verzí vedle sebe. Microsoft R klienta, ale podporuje jenom jedna verze a vždy používá nejnovější ten, který jste nainstalovali.

### <a name="install-the-r-tools"></a>Nainstalujte nástroje pro R

Stáhnout aktuální RTVS pro Visual Studio 2015 z [https://aka.ms/rtvs-current](https://aka.ms/rtvs-current). RTVS kontroluje vhodnou verzi Visual Studia a vám pomůže nainstalovat překladač R, pokud jste tak ještě neučinili.

> [!Note]
> Samostatný instalační program RTVS funguje pouze v sadě Visual Studio 2015; s Visual Studio 2017 nainstalovat podporu R prostřednictvím [vědecké zpracování dat a analytických aplikací zatížení](#installing-rtvs-in-visual-studio-2017) jak bylo popsáno výše.

RTVS pro Visual Studio 2015 se instaluje v: `%ProgramFiles(x86)%\Microsoft Visual Studio 14\Common7\IDE\Extensions\Microsoft\R Tools for Visual Studio`

## <a name="offline-installation-of-visual-studio-and-rtvs"></a>Offline instalace sady Visual Studio a RTVS

Offline instalace je vhodná pro počítače, které nejsou připojené k Internetu:

1. Postupujte podle pokynů vytvořte offline instalačního programu pro vaši verzi sady Visual Studio:

    - [Visual Studio 2017](../install/create-an-offline-installation-of-visual-studio.md)
    - [Visual Studio 2015](https://msdn.microsoft.com/library/mt706497.aspx)

1. Visual Studio 2015, stáhněte si offline instalační programy RTVS z [https://aka.ms/rtvs-current-zip](https://aka.ms/rtvs-current-zip) a [https://aka.ms/rtvs-remote-zip](https://aka.ms/rtvs-remote-zip).

1. Instalace sady Visual Studio a RTVS z offline instalační programy.

## <a name="see-also"></a>Viz také

- [Začínáme s R](getting-started-with-r.md)
- [Nástroje pro R ukázkové projekty](getting-started-samples.md)
- [Získání nápovědy](getting-started-help.md)
- [Nastavení možností](options-for-r-tools-in-visual-studio.md)
- [Microsoft Machine Learning Server (dříve R Server)](/machine-learning-server/)