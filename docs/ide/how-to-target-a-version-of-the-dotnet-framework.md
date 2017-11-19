---
title: "Postupy: cílení na verzi rozhraní .NET Framework | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- targeting .NET Framework version [Visual Studio]
- versions [Visual Studio], targeting .NET Framework version
ms.assetid: dea62d25-3d1b-492e-a6cc-b5154489800a
caps.latest.revision: "50"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 67145a9aaaf4c01b02bc1cc6db89e375639b4fcd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-target-a-version-of-the-net-framework"></a>Postupy: Cílení na verzi rozhraní .NET Framework
Tento dokument popisuje, jak při vytvoření projektu cílit na určitou verzi rozhraní .NET Framework a jak změnit cílenou verzi v existujícím projektu v jazyce Visual Basic, Visual C# nebo Visual F#.  
  
> [!IMPORTANT]
>  Informace o tom, jak změnit na cílovou verzi pro projekty C++ najdete v tématu [postupy: Změna cílové architektury a sady nástrojů](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).  
  
 **V tomto tématu**  
  
-   [Cílení na verzi, po vytvoření projektu](../ide/how-to-target-a-version-of-the-dotnet-framework.md#bkmk_new)  
  
-   [Změna verze cíle](../ide/how-to-target-a-version-of-the-dotnet-framework.md#bkmk_existing)  
  
##  <a name="bkmk_new"></a>Cílení na verzi, po vytvoření projektu  
 Šablony, které můžete použít při vytváření projektu, jsou určeny verzí rozhraní .NET Framework, na kterou cílíte.  
  
> [!NOTE]
>  V edicích sady Visual Studio Express, musíte vytvořit projekt nejprve, a pak můžete změnit cíl, jako [změna verze cíle](../ide/how-to-target-a-version-of-the-dotnet-framework.md#bkmk_existing) popisuje dále v tomto tématu.  
  
#### <a name="to-target-a-version-when-you-create-a-project"></a>Cílení na určitou verzi při vytváření projektu  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
2.  V seznamu v horní části **nový projekt** dialogovém okně vyberte verzi rozhraní .NET Framework, pokud chcete k cíli.  
  
    > [!NOTE]
    >  Se sadou Visual Studio se obvykle instaluje jen jedna verze rozhraní .NET Framework. Pokud chcete cílit na jinou verzi, je nejprve třeba zkontrolovat, zda je nainstalovaná. V tématu [cílení na více verzí sady Visual Studio přehled](../ide/visual-studio-multi-targeting-overview.md).  
  
3.  V seznamu nainstalovaných šablon, vyberte typ projektu, který chcete vytvořit, název projektu a potom zvolte **OK** tlačítko.  
  
     V seznamu šablon jsou uvedeny pouze projekty, které jsou podporovány vámi vybranou verzí rozhraní .NET Framework.  
  
##  <a name="bkmk_existing"></a>Změna verze cíle  
 Pomocí tohoto postupu můžete změnit cílové verze rozhraní .NET Framework v projektu jazyka Visual Basic, Visual C# nebo Visual F #.  
  
#### <a name="to-change-the-targeted-version"></a>Změna cílené verze  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro projekt, který chcete změnit a potom vyberte **vlastnosti**.  
  
     ![Visual Studio řešení Explorer vlastnosti](../ide/media/vs_slnexplorer_properties.png "vs_slnExplorer_Properties")  
  
    > [!IMPORTANT]
    >  Informace o tom, jak změnit na cílovou verzi pro projekty C++ najdete v tématu [postupy: Změna cílové architektury a sady nástrojů](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).  
  
2.  V levém sloupci okna vlastností, vyberte **aplikace** kartě.  
  
     ![Visual Studio aplikace vlastnosti aplikace karta](../ide/media/vs_slnexplorer_properties_applicationtab.png "vs_slnExplorer_Properties_ApplicationTab")  
  
    > [!NOTE]
    >  Po vytvoření aplikace pro UPW, nelze změnit cílovou verzi systému Windows nebo rozhraní .NET Framework.  
  
3.  V **cílové rozhraní** vyberte verzi, která chcete.  
  
4.  V dialogovém okně ověření zvolte **Ano** tlačítko.  
  
     Projekt se uvolní. Až se znovu načte, bude cílit na verzi rozhraní .NET Framework, kterou jste vybrali.  
  
    > [!NOTE]
    >  Pokud váš kód obsahuje odkazy na jinou verzi rozhraní .NET Framework, než na kterou cílíte, mohou se při kompilaci či spuštění kódu zobrazit chybové zprávy. Chcete-li tyto chyby vyřešit, je třeba upravit odkazy. V tématu [řešení potíží s cílením rozhraní .NET Framework](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md).  
  
## <a name="see-also"></a>Viz také  
 [Cílení na více verzí sady Visual Studio – přehled](../ide/visual-studio-multi-targeting-overview.md)   
 [Rozhraní .NET framework cílení na více pro webové projekty ASP.NET](http://msdn.microsoft.com/Library/8b8145a9-62f6-4fc4-8a83-47b0487cbe76)   
 [Řešení potíží s cílením rozhraní .NET Framework](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)   
 [Stránka aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md)   
 [Stránka aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)   
 [Konfigurace projektů](http://msdn.microsoft.com/Library/a1489abb-6294-4f8f-b71f-2cb126393526)   
 [Postupy: Změna cílové architektury a sady nástrojů](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)