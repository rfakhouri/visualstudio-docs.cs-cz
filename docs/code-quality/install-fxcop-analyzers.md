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
ms.openlocfilehash: b5cb0fa5985cbc923713330289d7f83ed1fd954e
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551103"
---
# <a name="install-fxcop-analyzers-in-visual-studio"></a>Instalace analyzátorů FxCop v aplikaci Visual Studio

Společnost Microsoft vytvořila sadu analyzátorů označovaných jako [Microsoft. CodeAnalysis. FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers), které obsahují nejdůležitější pravidla "FxCop" ze starší verze analýzy. Tyto analyzátory kontrolují váš kód pro problémy se zabezpečením, výkonem a návrhem mimo jiné.

Tyto analyzátory FxCop můžete nainstalovat buď jako balíček NuGet, nebo jako rozšíření VSIX pro Visual Studio. Další informace o jednotlivých specialistech a jejich nevýhody najdete v [tématu balíček NuGet vs. Rozšíření](roslyn-analyzers-overview.md#nuget-package-versus-vsix-extension)VSIX.

## <a name="to-install-fxcop-analyzers-as-a-nuget-package"></a>Instalace analyzátorů FxCop jako balíčku NuGet

1. [Určete verzi balíčku analyzátoru, která](#fxcopanalyzers-package-versions) se má nainstalovat, na základě vaší verze sady Visual Studio.

2. Nainstalujte balíček v aplikaci Visual Studio pomocí [konzoly Správce balíčků](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console) nebo [uživatelského rozhraní Správce balíčků](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console).

   > [!NOTE]
   > Stránka nuget.org pro každý balíček analyzátoru zobrazuje příkaz pro vložení do **konzoly Správce balíčků**. Je k dispozici i praktické tlačítko ke zkopírování textu do schránky.
   >
   > ![Stránka NuGet.org zobrazující příkaz konzoly Správce balíčků](media/nuget-package-manager-command.png)

   Jsou nainstalována sestavení analyzátoru a jsou uvedena v **Průzkumník řešení** v části**analyzátory** **odkazů** > .

   ![Uzel analyzátorů v Průzkumník řešení](media/solution-explorer-analyzers-node.png)

### <a name="fxcopanalyzers-package-versions"></a>Verze balíčků FxCopAnalyzers

Pomocí následujících pokynů určete, která verze balíčku FxCop Analyzer má být nainstalována pro vaši verzi sady Visual Studio:

| Verze sady Visual Studio | Verze balíčku analyzátoru FxCop |
| - | - |
| Visual Studio 2019 (všechny verze)<br />Visual Studio 2017 verze 15,8 a novější | [2.9.3](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.9.3) |
| Visual Studio 2017 verze 15,5 až 15,7 | [2.6.3](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.6.3) |
| Visual Studio 2017 verze 15,3 až 15,4 | [2.3.0-beta1](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.3.0-beta1) |
| Visual Studio 2017 verze 15,0 až 15,2 | [2.0.0-beta2](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.0.0-beta2) |
| Visual Studio 2015 Update 2 a 3 | [1.2.0-beta2](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/1.2.0-beta2) |
| Visual Studio 2015 Update 1 | [1.1.0](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/1.1.0) |
| Visual Studio 2015 RTW | [1.0.1](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/1.0.1) |

## <a name="to-install-fxcop-analyzers-as-a-vsix"></a>Instalace analyzátorů FxCop jako VSIX

::: moniker range="vs-2017"

V systému Visual Studio 2017 verze 15,5 a novější můžete nainstalovat rozšíření [Microsoft Code Analysis 2017](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017) , které obsahuje všechny analyzátory FxCop pro spravované projekty.

1. V aplikaci Visual Studio vyberte rozšíření **nástrojů** > **a aktualizace**.

   Otevře se dialogové okno **rozšíření a aktualizace** .

   > [!NOTE]
   > Další možností je stáhnout rozšíření přímo z [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017).

2. V levém podokně rozbalte položku **online** a vyberte možnost **Visual Studio Marketplace**.

3. Do vyhledávacího pole zadejte text "Analýza kódu" a vyhledejte rozšíření **Microsoft Code analysis 2017** .

   ![Rozšíření Microsoft Code Analysis 2017](media/extensions-and-updates-code-analysis.png)

::: moniker-end

::: moniker range=">=vs-2019"

Rozšíření [Microsoft Code Analysis 2019](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2019) obsahuje všechny analyzátory FxCop pro spravované projekty. Instalace tohoto rozšíření:

1. V aplikaci Visual Studio vyberte **rozšíření** > **Spravovat rozšíření**.

   Otevře se dialogové okno **Spravovat rozšíření** .

   > [!NOTE]
   > Další možností je stáhnout rozšíření přímo z [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2019).

2. V levém podokně rozbalte položku **online** a vyberte možnost **Visual Studio Marketplace**.

3. Do vyhledávacího pole zadejte text "Analýza kódu" a vyhledejte rozšíření **Microsoft Code analysis 2019** .

   ![Rozšíření Microsoft Code Analysis 2019](media/manage-extensions-code-analysis.png)

::: moniker-end

4. Vyberte **Stáhnout**.

   Rozšíření se stáhne.

5. Kliknutím na **tlačítko OK** zavřete dialogové okno a poté zavřete všechny instance aplikace Visual Studio a spusťte **instalační program VSIX**.

   Otevře se dialogové okno **instalátor VSIX** .

   ::: moniker range="vs-2017"

   ![Instalační program VSIX pro analýzu kódu Microsoft](media/vsix-installer-code-analysis.png)

   ::: moniker-end

6. Kliknutím na tlačítko **změnit** spusťte instalaci.

   Po jedné nebo dvou minutách se instalace dokončí.

7. Vyberte **Zavřít**a pak znovu otevřít Visual Studio.

::: moniker range="vs-2017"

Chcete-li ověřit, zda je rozšíření nainstalováno, vyberte možnost**rozšíření a aktualizace** **nástroje** > . V dialogovém okně **rozšíření a aktualizace** vyberte nainstalovanou kategorii na levé straně a potom vyhledejte rozšíření podle názvu.

::: moniker-end

::: moniker range=">=vs-2019"

Chcete-li ověřit, zda je rozšíření nainstalováno, vyberte **rozšíření** > **Spravovat rozšíření**. V dialogovém okně **Spravovat rozšíření** vyberte v levé části kategorii **nainstalováno** a pak vyhledejte rozšíření podle názvu.

::: moniker-end

## <a name="see-also"></a>Viz také:

- [Přehled analyzátorů kódu v aplikaci Visual Studio](../code-quality/roslyn-analyzers-overview.md)
- [Použití analyzátorů kódu v aplikaci Visual Studio](../code-quality/use-roslyn-analyzers.md)
- [Migrace ze starší verze z analýz na analyzátory kódu](../code-quality/fxcop-analyzers.yml)
