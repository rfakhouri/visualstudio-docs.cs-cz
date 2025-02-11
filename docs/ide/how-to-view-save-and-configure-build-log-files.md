---
title: 'Postupy: Zobrazit, Uložit a nakonfigurovat soubory protokolu sestavení | Microsoft Docs'
ms.date: 08/28/2019
ms.technology: vs-ide-compile
ms.topic: conceptual
ms.assetid: 75d38b76-26d6-4f43-bbe7-cbacd7cc81e7
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1fe1932930c869e3d4d3d74eb641da068e1cffec
ms.sourcegitcommit: 3cda0d58c5cf1985122b8977b33a171c7359f324
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/29/2019
ms.locfileid: "70154814"
---
# <a name="how-to-view-save-and-configure-build-log-files"></a>Postupy: Zobrazování, ukládání a konfigurace souborů protokolu sestavení

Po sestavení projektu v integrovaném vývojovém prostředí sady Visual Studio můžete zobrazit informace o tomto sestavení v okně **výstup** . Pomocí těchto informací můžete například řešit potíže při selhání sestavení. 

- Pro C++ projekty lze také zobrazit stejné informace v souboru *. txt* , který je vytvořen a uložen automaticky. 

- Pro projekty spravovaného kódu můžete kliknout na okno výstup sestavení a stisknout **kombinaci kláves CTRL +** +**S**. Visual Studio vás vyzve k zadání umístění pro uložení informací z okna **výstup** do souboru *. txt* . 

Rozhraní IDE lze také použít k určení, jaké druhy informací chcete zobrazit o jednotlivých sestaveních.

Pokud sestavíte jakýkoli typ projektu pomocí nástroje MSBuild, můžete vytvořit soubor *. txt* k uložení informací o sestavení. Další informace najdete v tématu [získání protokolů sestavení](../msbuild/obtaining-build-logs-with-msbuild.md).

## <a name="to-view-the-build-log-file-for-a-c-project"></a>Zobrazení souboru protokolu sestavení pro C++ projekt

1. V **Průzkumníku Windows** nebo **Průzkumníkovi souborů**otevřete následující soubor:  *\\. ..\Visual Studio \<verze\>\Projects\\<\>ProjectName <\\ ProjectName\>\debug.\\<ProjectName\>. txt*

## <a name="to-create-a-build-log-file-for-a-managed-code-project"></a>Vytvoření souboru protokolu sestavení pro projekt spravovaného kódu

1. Na řádku nabídek klikněte na **sestavit** > sestavení**řešení**.

2. V okně **výstup** klikněte někam do textu.

3. Stiskněte klávesy **CTRL**+**S**.

   Visual Studio vás vyzve k zadání umístění pro uložení výstupu sestavení.

Můžete také vygenerovat protokoly spuštěním nástroje MSBuild přímo z příkazového řádku pomocí `-fileLogger` možnosti příkazového řádku (`-fl`). Viz [získání protokolů sestavení pomocí nástroje MSBuild](../msbuild/obtaining-build-logs-with-msbuild.md).

## <a name="to-change-the-amount-of-information-included-in-the-build-log"></a>Změna množství informací obsažených v protokolu sestavení

1. V panelu nabídky zvolte **nástroje** > **možnosti**.

2. Na stránce **projekty a řešení** vyberte stránku **sestavení a spuštění** .

3. V seznamu **podrobností výstupu sestavení projektu nástroje MSBuild** zvolte jednu z následujících hodnot a pak klikněte na tlačítko **OK** .

    |Úroveň podrobností|Popis|
    | - |-----------------|
    |**Quiet**|Zobrazí souhrn pouze pro sestavení.|
    |**Poskytuje**|Zobrazí souhrn sestavení a chyb, upozornění a zpráv, které jsou zařazeny do kategorie s vysokou důležitostí.|
    |**Běžnou**|Zobrazí souhrn sestavení; chyby, varování a zprávy, které jsou zařazeny do kategorie jako vysoce důležité; a hlavní kroky sestavení. Tuto úroveň podrobností budete používat častěji.|
    |**Podrobnosti**|Zobrazí souhrn sestavení; chyby, varování a zprávy, které jsou zařazeny do kategorie jako vysoce důležité; všechny kroky sestavení; zprávy, které jsou zařazeny do kategorií normálním významem.|
    |**Diagnostický**|Zobrazí všechna data, která jsou k dispozici pro sestavení. Tuto úroveň podrobností můžete použít k usnadnění ladění problémů s vlastními skripty sestavení a dalšími problémy s sestavením.|

     Další informace najdete v [dialogovém okně Možnosti, projekty a řešení, sestavení a spuštění](../ide/reference/options-dialog-box-projects-and-solutions-build-and-run.md) a <xref:Microsoft.Build.Framework.LoggerVerbosity>.

    > [!IMPORTANT]
    > Projekt musíte znovu sestavit, aby se změny projevily v okně **výstup** (všechny projekty) a v  *\<souboru ProjectName >. txt* (C++ pouze projekty).

## <a name="use-binary-logs-to-make-it-easier-to-browse-large-log-files"></a>Použití binárních protokolů pro snazší procházení velkých souborů protokolu

Binární protokoly jsou volitelnou funkcí pro projekty .NET, které vám umožní získat bohatší možnosti procházení protokolů, které by mohly usnadnit hledání informací ve velkých protokolech. Chcete-li použít binární protokoly, nainstalujte [Systémové nástroje projektu](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.ProjectSystemTools). Další informace najdete v tématu [https://msbuildlog.com](https://msbuildlog.com) a v [binárním protokolu](https://github.com/microsoft/msbuild/blob/master/documentation/wiki/Binary-Log.md) .

## <a name="see-also"></a>Viz také:

- [Sestavování a čištění projektů a řešení v aplikaci Visual Studio](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)
- [Kompilace a sestavení](../ide/compiling-and-building-in-visual-studio.md)
