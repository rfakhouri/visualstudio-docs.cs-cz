---
title: "Přizpůsobení úvodní stránky pro sadu Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 02/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.startpage
- VS.StartPage.HowDoI
- vs.ToolsOptionsPages.Startup
helpviewer_keywords:
- Start Page [Visual Studio]
- customizing Start Page [Visual Studio]
- Visual Studio Start page
ms.assetid: 925d42eb-ec34-426e-ad81-19db8630e536
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 178c20c9c4c3af8f5252e70ca603cdf8f8335e52
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="customize-the-start-page-for-visual-studio"></a>Přizpůsobení úvodní stránky pro sadu Visual Studio
Úvodní stránky pro sadu Visual Studio můžete přizpůsobit výchozí několika způsoby, například zobrazující **otevřeného projektu** dialogové okno nebo otevírání řešení, která byla načtena naposledy. Můžete také zobrazit vlastní úvodní stránku, což je stránka XAML Windows Presentation Foundation (WPF) spuštěná v okně nástroje a lze v rámci ní spouštět interní příkazy sady Visual Studio.  

## <a name="customize-the-default-start-page"></a>Přizpůsobit výchozí úvodní stránky  

1.  Na řádku nabídek zvolte **nástroje**, **možnosti**.  

2.  Rozbalte položku **prostředí**a potom zvolte **spuštění**.  

3.  V **při spuštění** seznamu, vyberte položku, která pro přizpůsobení, které chcete.  

## <a name="show-a-custom-start-page"></a>Zobrazení vlastní úvodní stránky  

1.  Vlastní úvodní stránku nainstalujte jedním z následujících způsobů:  

    -   Nainstalujte ji z [Galerie sady Visual Studio](http://visualstudiogallery.msdn.microsoft.com/site/search?f%5B0%5D.Type=SearchText&f%5B0%5D.Value=start%20page), stránka v intranetu nebo jiný web.  

        Otevřete soubor VSIX, který obsahuje vlastní úvodní stránky, nebo zkopírujte a vložte úvodní stránky souborů do **% USERPROFILE % Documents\Visual Studio 2017\StartPages** složky v počítači.  

    -   Vytvořte si vlastní úvodní stránku, pokud jste nainstalovali sadu Visual Studio SDK.  

         V tématu [vytváření vlastní úvodní stránku](../extensibility/creating-a-custom-start-page.md).  

2.  Na řádku nabídek zvolte **nástroje**, **možnosti**.  

3.  Rozbalte položku **prostředí**a potom zvolte **spuštění**.  

4.  V **přizpůsobení úvodní stránka** vyberte požadované stránky.  

> [!NOTE]
>  Pokud chyba na vlastní úvodní stránce způsobí chybu sady Visual Studio, můžete sadu Visual Studio spustit v nouzovém režimu a pak ji nastavit tak, aby používala výchozí úvodní stránku. V tématu [/safemode (devenv.exe)](../ide/reference/safemode-devenv-exe.md).  

## <a name="see-also"></a>Viz také  
 [Přizpůsobení sady Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md)   
