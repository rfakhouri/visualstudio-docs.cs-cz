---
title: Cílení na určitou verzi rozhraní .NET
ms.date: 03/21/2019
ms.topic: conceptual
helpviewer_keywords:
- targeting .NET [Visual Studio]
- .NET version [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 2c316610fc007e3e8642567c01a5172feb461bda
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66747125"
---
# <a name="how-to-target-a-version-of-net"></a>Postupy: Cílení na určitou verzi rozhraní .NET

Tento článek popisuje, jak cílit na konkrétní verzi rozhraní .NET Framework při vytváření projektu rozhraní .NET Framework. Také popisuje, jak změnit cílenou verzi v jazyce Visual Basic se existující C#, nebo F# projektu.

> [!IMPORTANT]
> Informace o tom, jak změnit cílovou verzi pro projekty C++, naleznete v tématu [jak: Upravit na cílové rozhraní framework a sadu nástrojů platformy](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset).

## <a name="target-a-version-when-you-create-a-project"></a>Cílení na určitou verzi při vytváření projektu

Při vytváření projektu rozhraní .NET Framework, k dispozici verze rozhraní .NET Framework závisí na jaké verze jsou nainstalovány a v šabloně zvoleného projektu.

1. V panelu nabídky zvolte **souboru** > **nový** > **projektu**.

1. Zvolte šablonu rozhraní .NET Framework pro typ projektu, který chcete vytvořit.

1. Z **Framework** rozevírací seznam v dolní části dialogového okna zvolte verzi rozhraní .NET Framework, který má váš projekt zaměřit.

   Tento seznam rozhraní obsahuje pouze verze, které se vztahují na šablonu, kterou jste zvolili.

   > [!NOTE]
   > Některé typy projektů, jako je .NET Core, nezobrazují **Framework** rozevíracího seznamu.

   ::: moniker range="vs-2017"

   ![Rozhraní Framework rozevírací seznam v dialogovém okně Nový projekt sady Visual Studio 2017](media/vside-newproject-framework.png)

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   ![Selektor Framework v VS 2019](media/vs-2019/configure-new-project-framework.png)

   ::: moniker-end

1. Pokračujte [vytvořit projekt](create-new-project.md).

## <a name="change-the-targeted-version"></a>Změnit cílovou verzi

Můžete změnit cílovou verzi rozhraní .NET v jazyce Visual Basic C#, nebo F# projekt pomocí tohoto postupu.

1. V **Průzkumníka řešení**, otevřete místní nabídku pro projekt, který chcete změnit a klikněte na tlačítko **vlastnosti**.

    ![Vlastnosti Průzkumníku řešení sady Visual Studio](../ide/media/vs_slnexplorer_properties.png)

1. V levém sloupci **vlastnosti** okna, vyberte **aplikace** kartu.

    ![Visual Studio aplikaci vlastnosti karty](../ide/media/vs_slnexplorer_properties_applicationtab.png)

    > [!NOTE]
    > Po vytvoření aplikace pro UPW, nelze změnit cílenou verzi systému Windows nebo .NET.

1. V **Cílová architektura** , zvolte verzi, která chcete.

1. V dialogovém okně ověřování, který se zobrazí, zvolte **Ano** tlačítko.

    Projekt se uvolní. Až se znovu načte, zaměřuje verzi rozhraní .NET, kterou jste vybrali.

    > [!NOTE]
    > Pokud váš kód obsahuje odkazy na jinou verzi rozhraní .NET než ten, který jste určili, mohou se zobrazit chybové zprávy při kompilaci či spuštění kódu. Chcete-li tyto chyby vyřešit, je třeba upravit odkazy. Zobrazit [.NET řešení potíží s cílením](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md).

## <a name="see-also"></a>Viz také:

- [Přehled cílení na rozhraní Framework](../ide/visual-studio-multi-targeting-overview.md)
- [Řešení potíží s cílením na rozhraní .NET Framework](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)
- [Stránka aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md)
- [Stránka aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)
- [Postupy: Upravit na cílové rozhraní framework a sadu nástrojů platformy (C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)