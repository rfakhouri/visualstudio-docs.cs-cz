---
title: Změnit možnosti spuštění
ms.date: 02/01/2017
ms.topic: conceptual
f1_keywords:
- vs.ToolsOptionsPages.Startup
helpviewer_keywords:
- Start Page [Visual Studio]
- customizing Start Page [Visual Studio]
- Visual Studio Start Page
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c8b31f033b9c04871e57836dd263071d87a24fda
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2019
ms.locfileid: "58070110"
---
# <a name="customize-startup"></a>Upravit spuštění

Spuštění prostředí pro Visual Studio můžete upravit několika různými způsoby, jako je například otevírání řešení nejnovější nebo jenom prázdný vývojové prostředí.

::: moniker range="vs-2017"

Můžete také zobrazit vlastní úvodní stránku, což je stránka XAML Windows Presentation Foundation (WPF) spuštěná v okně nástroje a lze v rámci ní spouštět interní příkazy sady Visual Studio.

::: moniker-end

## <a name="to-change-the-startup-item"></a>Chcete-li změnit položku při spuštění

1. V panelu nabídky zvolte **nástroje** > **možnosti**.

2. Rozbalte **prostředí**a klikněte na tlačítko **spuštění**.

::: moniker range="vs-2017"

3. V **při spuštění** seznamu, vyberte položku, který se zobrazí po spuštění sady Visual Studio.

::: moniker-end

::: moniker range=">=vs-2019"

3. V **při spuštění, otevřete** klikněte na položku co byste chtěli po spuštění sady Visual Studio. Můžete si vybrat z **počáteční okno** (které vám umožní otevřít nového nebo existujícího projektu), **nejnovější řešení**, nebo **prázdné prostředí**.

::: moniker-end

::: moniker range="vs-2017"

## <a name="to-show-a-custom-start-page"></a>Zobrazení vlastní úvodní stránky

Je možné [vytvořit vlastní úvodní stránky](../extensibility/creating-a-custom-start-page.md) pomocí sady Visual Studio SDK, nebo použijte takový, který už někdo jiný vytvořil. Například můžete najít na vlastní úvodní stránky [Visual Studio Marketplace](https://marketplace.visualstudio.com/search?target=VS&category=Tools&vsVersion=&subCategory=Start%20Pages&sortBy=Downloads).

Chcete-li nainstalovat vlastní úvodní stránku, otevřete *VSIX* souboru, nebo zkopírujte a vložte soubory úvodní stránky do *%USERPROFILE%\Documents\Visual Studio 2017\StartPages* složky v počítači.

### <a name="to-select-which-custom-start-page-to-display"></a>Chcete-li vybrat kterou vlastní úvodní stránku zobrazení

1. V panelu nabídky zvolte **nástroje** > **možnosti**.

1. Rozbalte **prostředí**a klikněte na tlačítko **spuštění**.

1. V **přizpůsobit úvodní stránku** , zvolte na stránce, který chcete.

> [!TIP]
> Pokud chyba na vlastní úvodní stránce způsobí, že Visual Studio selhání, můžete otevřít Visual Studio v nouzovém režimu a potom nastavte ho na použití výchozí úvodní stránku. Zobrazit [/safemode (devenv.exe)](../ide/reference/safemode-devenv-exe.md).

## <a name="see-also"></a>Viz také:

- [Přizpůsobení prostředí IDE sady Visual Studio](../ide/personalizing-the-visual-studio-ide.md)

::: moniker-end