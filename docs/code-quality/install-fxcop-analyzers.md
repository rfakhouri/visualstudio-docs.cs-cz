---
title: Instalace analyzátorů FxCop
ms.date: 08/03/2018
ms.topic: conceptual
helpviewer_keywords:
- fxcop analyzers
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 9e2fc29723f66fce0fda72a9af1fe40888bd2ce3
ms.sourcegitcommit: 51dad3e11d7580567673e0d426ab3b0a17584319
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/10/2019
ms.locfileid: "66820637"
---
# <a name="install-fxcop-analyzers-in-visual-studio"></a>Nainstalujte analyzátory FxCop v sadě Visual Studio

Microsoft vytvořil sadu analyzátory, volá [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers), který obsahuje nejdůležitější "FxCop" pravidla ze statické analýzy kódu, převést na analyzátory Roslyn. Tyto analyzátory zkontrolovat kód pro zabezpečení, výkonu a problémy návrhu, mimo jiné.

Tyto analyzátory FxCop můžete nainstalovat jako balíček NuGet nebo jako rozšíření VSIX do sady Visual Studio. Další informace o výhody a nevýhody jednotlivých najdete v tématu [vs balíčku NuGet. Rozšíření VSIX](roslyn-analyzers-overview.md#nuget-package-versus-vsix-extension).

## <a name="to-install-fxcop-analyzers-as-a-nuget-package"></a>Chcete-li nainstalovat analyzátory FxCop jako balíček NuGet

1. [Určit verzi balíčku, která analyzer](#fxcopanalyzers-package-versions) k instalaci, podle vaší verze sady Visual Studio.

2. Nainstalujte balíček v sadě Visual Studio, buď pomocí [Konzola správce balíčků](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console) nebo [uživatelské rozhraní Správce balíčků](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console).

   > [!NOTE]
   > Na stránce nuget.org pro každý balíček Analyzátor se dozvíte, příkaz a vložte do **Konzola správce balíčků**. Je i užitečný tlačítko ke zkopírování textu do schránky.
   >
   > ![NuGet.org stránky zobrazující příkaz konzoly Správce balíčků](media/nuget-package-manager-command.png)

   Sestavení analyzátoru jsou nainstalovány a jsou uvedeny v **Průzkumníka řešení** pod **odkazy** > **analyzátory**.

   ![Analyzátory uzlu v Průzkumníkovi řešení](media/solution-explorer-analyzers-node.png)

### <a name="fxcopanalyzers-package-versions"></a>Verze balíčku FxCopAnalyzers

Určení verze balíčku analyzátory FxCop instalace pro vaši verzi sady Visual Studio pomocí následujících pokynů:

| Verze sady Visual Studio | Verze balíčku analyzátor FxCop |
| - | - |
| Visual Studio 2019 (všechny verze)<br />Visual Studio 2017 verze 15,8 a novější | [2.9.3](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.9.3) |
| Visual Studio 2017 verze 15.5 na verzi 15.7 | [2.6.3](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.6.3) |
| Visual Studio 2017 verze 15.3 k 15.4 | [2.3.0-beta1](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.3.0-beta1) |
| Visual Studio 2017 verze 15.0: 15.2 | [2.0.0-beta2](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.0.0-beta2) |
| Visual Studio 2015 update 2 a 3 | [1.2.0-beta2](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/1.2.0-beta2) |
| Visual Studio 2015 Update 1 | [1.1.0](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/1.1.0) |
| Visual Studio 2015 RTW | [1.0.1](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/1.0.1) |

## <a name="to-install-fxcop-analyzers-as-a-vsix"></a>Chcete-li nainstalovat analyzátory FxCop jako rozšíření VSIX

::: moniker range="vs-2017"

V sadě Visual Studio 2017 verze 15.5 nebo novější, můžete nainstalovat [Microsoft Code Analysis 2017](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017) rozšíření, které obsahuje všechny analyzátory FxCop pro spravované projekty.

1. V sadě Visual Studio, vyberte **nástroje** > **rozšíření a aktualizace**.

   **Rozšíření a aktualizace** zobrazí se dialogové okno.

   > [!NOTE]
   > Můžete také stáhnout přímo z rozšíření [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017).

2. Rozbalte **Online** v levém podokně a pak vyberte **Visual Studio Marketplace**.

3. Do vyhledávacího pole zadejte "analýza kódu" a vyhledejte **Microsoft Code Analysis 2017** rozšíření.

   ![Rozšíření Microsoft Code Analysis 2017](media/extensions-and-updates-code-analysis.png)

::: moniker-end

::: moniker range=">=vs-2019"

[Microsoft Code Analysis 2019](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2019) rozšíření obsahuje všechny analyzátory FxCop pro spravované projekty. Chcete-li toto rozšíření nainstalovat:

1. V sadě Visual Studio, vyberte **rozšíření** > **spravovat rozšíření**.

   **Spravovat rozšíření** zobrazí se dialogové okno.

   > [!NOTE]
   > Můžete také stáhnout přímo z rozšíření [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2019).

2. Rozbalte **Online** v levém podokně a pak vyberte **Visual Studio Marketplace**.

3. Do vyhledávacího pole zadejte "analýza kódu" a vyhledejte **Microsoft Code Analysis 2019** rozšíření.

   ![Rozšíření Microsoft 2019 analýzy kódu](media/manage-extensions-code-analysis.png)

::: moniker-end

4. Vyberte **Stáhnout**.

   Rozšíření je stažen.

5. Vyberte **OK** dialogové okno zavřete a pak zavřete všechny instance sady Visual Studio ke spuštění **instalátor VSIX**.

   **Instalátor VSIX** zobrazí se dialogové okno.

   ::: moniker range="vs-2017"

   ![Instalátor VSIX pro analýzu kódu Microsoft](media/vsix-installer-code-analysis.png)

   ::: moniker-end

6. Vyberte **změnit** spusťte instalaci.

   Po jedné až dvou minutách dokončení instalace.

7. Vyberte **Zavřít**, potom znovu otevřete Visual Studio.

::: moniker range="vs-2017"

Pokud chcete zkontrolovat, zda je rozšíření nainstalované, vyberte **nástroje** > **rozšíření a aktualizace**. V **rozšíření a aktualizace** dialogové okno, vyberte **nainstalováno** kategorie na levé straně a poté vyhledejte rozšíření podle názvu.

::: moniker-end

::: moniker range=">=vs-2019"

Pokud chcete zkontrolovat, zda je rozšíření nainstalované, vyberte **rozšíření** > **spravovat rozšíření**. V **spravovat rozšíření** dialogové okno, vyberte **nainstalováno** kategorie na levé straně a poté vyhledejte rozšíření podle názvu.

::: moniker-end

## <a name="see-also"></a>Viz také:

- [Přehled analyzátory Roslyn v sadě Visual Studio](../code-quality/roslyn-analyzers-overview.md)
- [Používání analyzátorů Roslyn v sadě Visual Studio](../code-quality/use-roslyn-analyzers.md)
- [Migrace z FxCop do analyzátory Roslyn](../code-quality/fxcop-analyzers.yml)
