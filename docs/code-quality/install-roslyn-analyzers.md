---
title: Nainstalujte Roslyn analyzátorů v sadě Visual Studio
ms.date: 03/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: fb2f681de16a53c97954c8c37b8dd28b163998ee
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31927530"
---
# <a name="install-net-compiler-platform-analyzers"></a>Nainstalujte analyzátorů kompilátoru platformy .NET

Visual Studio 2017 obsahuje sadu základní kompilátoru platformu .NET (*Roslyn*) analyzátorů. Tyto analyzátorů jsou vždy zapnuty. Můžete nainstalovat další analyzátorů jako balíčky NuGet, nebo jako rozšíření sady Visual Studio v *VSIX* soubory.

## <a name="to-install-nuget-package-analyzers"></a>Chcete-li nainstalovat analyzátorů balíček NuGet

1. [Určit, která verze balíčku analyzátor](https://github.com/dotnet/roslyn-analyzers#recommended-version-of-analyzer-packages) k instalaci, podle vaší verze sady Visual Studio.

1. Nainstalujte balíček v sadě Visual Studio, buď pomocí [Konzola správce balíčků](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console) nebo [uživatelského rozhraní Správce balíčků](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console).

   > [!NOTE]
   > Na stránce nuget.org pro každý balíček Analyzátor se zobrazují příkaz pro vložení do **Konzola správce balíčků**. Je i užitečný tlačítko chcete zkopírovat text do schránky.
   >
   > ![NuGet.org stránky zobrazující příkaz konzoly Správce balíčků](media/nuget-package-manager-command.png)

   Analyzátor sestavení jsou nainstalované a zobrazují v **Průzkumníku řešení** pod **odkazy** > **analyzátorů**.

   ![Uzel analyzátorů v Průzkumníku řešení](media/solution-explorer-analyzers-node.png)

## <a name="to-install-vsix-analyzers"></a>Chcete-li nainstalovat analyzátorů VSIX

1. V sadě Visual Studio, vyberte **nástroje** > **rozšíření a aktualizace**.

   **Rozšíření a aktualizace** otevře se dialogové okno.

   > [!NOTE]
   > Případně, stáhněte si rozšíření přímo z [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017).

1. Rozbalte položku **Online** v levém podokně a potom vyberte **Visual Studio Marketplace**.

1. Do vyhledávacího pole zadejte "code analysis" a podívejte se **Microsoft Code Analysis 2017** rozšíření.

   ![Rozšíření Microsoft analýza kódu](media/extensions-and-updates-code-analysis.png)

1. Vyberte **Stáhnout**.

   Rozšíření se stáhne.

1. Vyberte **OK** dialogové okno zavřete a pak zavřete všechny instance sady Visual Studio spustíte **instalační program VSIX**.

   **Instalační program VSIX** otevře se dialogové okno.

   ![Instalační program VSIX pro analýzu kódu Microsoft](media/vsix-installer-code-analysis.png)

1. Vyberte **upravit** spusťte instalaci.

1. Po minutu nebo dvě po dokončení instalace. Vyberte **Zavřít**.

1. Znovu otevřete Visual Studio.

Pokud chcete zkontrolovat, zda je rozšíření nainstalované, vyberte **nástroje** > **rozšíření a aktualizace**. V **rozšíření a aktualizace** dialogové okno, vyberte **nainstalovaná** kategorie na levé straně a poté vyhledejte rozšíření podle názvu.

## <a name="next-steps"></a>Další kroky

- [Použití Roslyn analyzátorů v sadě Visual Studio](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>Viz také

- [Přehled Roslyn analyzátorů v sadě Visual Studio](../code-quality/roslyn-analyzers-overview.md)