---
title: Instalace vlastní úvodní stránku nebo změňte položku při spuštění v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 02/01/2017
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.ToolsOptionsPages.Startup
helpviewer_keywords:
- Start Page [Visual Studio]
- customizing Start Page [Visual Studio]
- Visual Studio Start Page
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9863fdfbfb73e49d0539ba1060f1e1c56888599c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="customize-the-start-page-for-visual-studio"></a>Přizpůsobení úvodní stránky pro sadu Visual Studio

Možnosti spuštění sady Visual Studio můžete přizpůsobit několika různými způsoby, například zobrazující **otevřeného projektu** dialogové okno nebo otevírání řešení, která byla načtena naposledy. Můžete také zobrazit vlastní úvodní stránku, což je stránka XAML Windows Presentation Foundation (WPF) spuštěná v okně nástroje a lze v rámci ní spouštět interní příkazy sady Visual Studio.

## <a name="to-change-the-startup-item"></a>Chcete-li změnit položku při spuštění

1. Na řádku nabídek zvolte **nástroje** > **možnosti**.

1. Rozbalte položku **prostředí**a potom zvolte **spuštění**.

1. V **při spuštění** seznamu, vyberte položku, který se zobrazí po spuštění sady Visual Studio.

## <a name="to-show-a-custom-start-page"></a>Chcete-li zobrazit vlastní úvodní stránku

Můžete [vytvořit stránku vlastní spuštění](../extensibility/creating-a-custom-start-page.md) pomocí sady Visual Studio SDK, nebo použijte jeden, který někdo jiný již vytvořen. Například můžete najít vlastní spuštění stránky na [Visual Studio Marketplace](https://marketplace.visualstudio.com/search?target=VS&category=Tools&vsVersion=&subCategory=Start%20Pages&sortBy=Downloads).

Chcete-li nainstalovat vlastní úvodní stránky, otevřete *VSIX* souboru, nebo zkopírujte a vložte spouštěcí stránky soubory do *%USERPROFILE%\Documents\Visual Studio 2017\StartPages* složky v počítači.

### <a name="to-select-which-custom-start-page-to-display"></a>Chcete-li vybrat které vlastní úvodní stránku zobrazení

1. Na řádku nabídek zvolte **nástroje** > **možnosti**.

1. Rozbalte položku **prostředí**a potom zvolte **spuštění**.

1. V **přizpůsobení úvodní stránka** vyberte požadované stránky.

> [!NOTE]
> Pokud chyba na vlastní úvodní stránce způsobí chybu sady Visual Studio, můžete sadu Visual Studio spustit v nouzovém režimu a pak ji nastavit tak, aby používala výchozí úvodní stránku. V tématu [/safemode (devenv.exe)](../ide/reference/safemode-devenv-exe.md).

## <a name="see-also"></a>Viz také

[Přizpůsobení sady Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md)
