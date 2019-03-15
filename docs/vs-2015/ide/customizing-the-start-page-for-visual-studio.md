---
title: Přizpůsobení úvodní stránky | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.startpage
- VS.StartPage.HowDoI
- vs.ToolsOptionsPages.Startup
helpviewer_keywords:
- Start Page [Visual Studio]
- customizing Start Page [Visual Studio]
- Visual Studio Start page
ms.assetid: 925d42eb-ec34-426e-ad81-19db8630e536
caps.latest.revision: 48
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f043e3cfbc6d81306abfb68276f2e32cce63ed45
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57869028"
---
# <a name="customizing-the-start-page-for-visual-studio"></a>Přizpůsobení úvodní stránky pro sadu Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete přizpůsobit úvodní stránku pro Visual Studio několika výchozími způsoby, například zobrazením **otevřít projekt** dialogové okno nebo otevřením řešení, který byl načten jako poslední. Můžete také zobrazit vlastní úvodní stránku, což je stránka XAML Windows Presentation Foundation (WPF) spuštěná v okně nástroje a lze v rámci ní spouštět interní příkazy sady Visual Studio.

## <a name="customizing-the-default-start-page"></a>Přizpůsobení výchozí úvodní stránky

1.  V panelu nabídky zvolte **nástroje**, **možnosti**.

2.  Rozbalte **prostředí**a klikněte na tlačítko **spuštění**.

3.  V **při spuštění** seznamu, zvolte položku pro přizpůsobení, které chcete.

## <a name="show-a-custom-start-page"></a>Zobrazení vlastní úvodní stránky

1.  Vlastní úvodní stránku nainstalujte jedním z následujících způsobů:

    -   Nainstalujte ji z [Visual Studio Marketplace](https://marketplace.visualstudio.com/), jiného webu nebo stránku na místním intranetu.

        > [!NOTE]
        >  Pokud se vám líbí stránka, která je určena pro starší verzi sady Visual Studio, můžete stránku upgradovat pomocí sady Visual Studio SDK. Zobrazit [jak: Vlastní úvodní stránku sady Visual Studio upgradovat](../misc/how-to-upgrade-a-visual-studio-custom-start-page.md).

         Otevřete soubor .vsix, který obsahuje vlastní úvodní stránku, nebo zkopírujte a vložte soubory úvodní stránky do **% USERPROFILE % Documents\Visual Studio 2015\StartPages** složky na vašem počítači.

    -   Vytvořte si vlastní úvodní stránku, pokud jste nainstalovali sadu Visual Studio SDK.

         Zobrazit [vytvářet své vlastní úvodní stránku](../misc/creating-your-own-start-page.md).

2.  V panelu nabídky zvolte **nástroje**, **možnosti**.

3.  Rozbalte **prostředí**a klikněte na tlačítko **spuštění**.

4.  V **přizpůsobit úvodní stránku** , zvolte na stránce, který chcete.

> [!NOTE]
>  Pokud chyba na vlastní úvodní stránce způsobí chybu sady Visual Studio, můžete sadu Visual Studio spustit v nouzovém režimu a pak ji nastavit tak, aby používala výchozí úvodní stránku. Zobrazit [/safemode (devenv.exe)](../ide/reference/safemode-devenv-exe.md).

## <a name="see-also"></a>Viz také
 [Přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3) [vytvářet své vlastní úvodní stránky](../misc/creating-your-own-start-page.md)
