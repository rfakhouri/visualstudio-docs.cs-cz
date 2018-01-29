---
title: "Postupy: cílení na verzi rozhraní .NET Framework | Microsoft Docs"
ms.custom: 
ms.date: 12/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- targeting .NET Framework version [Visual Studio]
- versions [Visual Studio], targeting .NET Framework version
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: da2e236c39cce72670a47212aedabb87afa4d217
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="how-to-target-a-version-of-the-net-framework"></a>Postupy: Cílení na verzi rozhraní .NET Framework

Tento dokument popisuje, jak cílení na verzi rozhraní .NET Framework, když vytvoříte projekt a jak změnit cílovou verzi v existující jazyka Visual Basic, C# nebo Visual F # projektu.

> [!IMPORTANT]
> Informace o tom, jak změnit na cílovou verzi pro projekty C++ najdete v tématu [postupy: Změna cílové architektury a sady nástrojů](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).

## <a name="targeting-a-version-when-you-create-a-project"></a>Cílení na určitou verzi při vytváření projektu

Šablony, které můžete použít při vytváření projektu, jsou určeny verzí rozhraní .NET Framework, na kterou cílíte.

### <a name="to-target-a-version-when-you-create-a-project"></a>Cílení na určitou verzi při vytváření projektu

1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.

2.  V seznamu v horní části **nový projekt** dialogovém okně vyberte verzi rozhraní .NET Framework, pokud chcete k cíli.

3.  V seznamu nainstalovaných šablon, vyberte typ projektu, který chcete vytvořit, název projektu a potom zvolte **OK** tlačítko.

    V seznamu šablon jsou uvedeny pouze projekty, které jsou podporovány vámi vybranou verzí rozhraní .NET Framework.

## <a name="changing-the-target-version"></a>Změna cílové verze

Pomocí tohoto postupu můžete změnit cílové verze rozhraní .NET Framework v projektu jazyka Visual Basic, C# nebo Visual F #.

Informace o tom, jak změnit na cílovou verzi pro projekty C++ najdete v tématu [postupy: Změna cílové architektury a sady nástrojů](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).

### <a name="to-change-the-targeted-version"></a>Změna cílené verze

1.  V **Průzkumníku řešení**, otevřete místní nabídku pro projekt, který chcete změnit a potom vyberte **vlastnosti**.

    ![Visual Studio Solution Explorer Properties](../ide/media/vs_slnexplorer_properties.png "vs_slnExplorer_Properties")

2. V levém sloupci okna vlastností, vyberte **aplikace** kartě.

    ![Visual Studio App Properties Application tab](../ide/media/vs_slnexplorer_properties_applicationtab.png "vs_slnExplorer_Properties_ApplicationTab")

    > [!NOTE]
    > Po vytvoření aplikace pro UPW, nelze změnit cílovou verzi systému Windows nebo rozhraní .NET Framework.

3.  V **cílové rozhraní** vyberte verzi, která chcete.

4.  V dialogovém okně ověření zvolte **Ano** tlačítko.

    Projekt se uvolní. Až se znovu načte, bude cílit na verzi rozhraní .NET Framework, kterou jste vybrali.

    > [!NOTE]
    > Pokud váš kód obsahuje odkazy na jinou verzi rozhraní .NET Framework, než na kterou cílíte, mohou se při kompilaci či spuštění kódu zobrazit chybové zprávy. Chcete-li tyto chyby vyřešit, je třeba upravit odkazy. V tématu [řešení potíží s cílením rozhraní .NET Framework](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md).

## <a name="see-also"></a>Viz také

[Přehled cílení na více verzí sady Visual Studio](../ide/visual-studio-multi-targeting-overview.md)  
[Řešení potíží s cílením na rozhraní .NET Framework](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)  
[Stránka Aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md)  
[Stránka Aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)  
[Postupy: Změna cílové architektury a sady nástrojů (C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)