---
title: "Vývoj kódu v sadě Visual Studio bez projekty a řešení | Microsoft Docs"
ms.date: 02/21/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
helpviewer_keywords:
- open folder [Visual Studio]
- anycode [Visual Studio]
- projects and solutions, develop code without
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 08c50a07992a1856ad0d5f45c0200e0b8a232cb7
ms.sourcegitcommit: 3abca1c733af876c8146daa43a62e829833be280
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/23/2018
---
# <a name="develop-code-in-visual-studio-without-projects-or-solutions"></a>Vývoj kódu v sadě Visual Studio bez projekty a řešení

V 2017 Visual Studio můžete do sady Visual Studio bez nutnosti soubor řešení nebo produktu project otevřete kód z téměř jakéhokoli typu na základě adresáře projektu. To znamená, můžete, například klonování úložišti na Githubu, otevřete přímo do sady Visual Studio a začít vývoj, aniž by bylo nutné vytvořit projekt nebo řešení. V případě potřeby můžete zadat vlastní sestavovací úlohy a spusťte parametry prostřednictvím jednoduchého soubory JSON.

Po otevření soubory s kódem v sadě Visual Studio, zobrazí se v Průzkumníku řešení všechny soubory ve složce. Kliknutím na libovolný soubor můžete začít s jeho úpravami. Na pozadí Visual Studio spustí indexování soubory, které chcete povolit technologii IntelliSense, navigace a refaktoringu funkce. Jak upravit, vytvořit, přesuňte nebo odstraňte soubory, Visual Studio automaticky sleduje změny a průběžně aktualizuje její IntelliSense index. Kód zobrazí s zabarvení syntaxe a v mnoha případech zahrnují základní dokončování IntelliSense.

## <a name="open-any-code"></a>Otevřete žádný kód

Kód v sadě Visual Studio můžete otevřít v některém z následujících způsobů:

- Na panelu nabídek Visual Studio zvolte **soubor** > **otevřete** > **složky**a pak přejděte do umístění v kódu.
- V nabídce kontextu (klikněte pravým tlačítkem) do složky obsahující kód zvolte **otevřete v sadě Visual Studio** příkaz.
- Vyberte **otevřít složku** odkaz na Visual Studio – úvodní stránka.
- Pokud se uživatel klávesnice, stiskněte klávesu **Ctrl**+**Shift**+**Alt**+**O** v aplikaci Visual Studio.
- Otevřete kód z klonovaného úložiště GitHub.

### <a name="to-open-code-from-a-cloned-github-repo"></a>Chcete-li spustit kód z klonovaného úložiště GitHub

Následující příklad ukazuje, jak klonovat úložiště GitHub a pak otevřete jeho kód v sadě Visual Studio. Pomocí tohoto postupu, musí mít účet GitHub a Git pro Windows v systému nainstalována. V tématu [zaregistrujete nový účet GitHub](https://help.github.com/articles/signing-up-for-a-new-github-account/) a [Git pro Windows](https://git-for-windows.github.io/) Další informace.

1. Přejděte na úložišti, které chcete klonovat na Githubu.

1. Vyberte **klonovat nebo stáhnout** tlačítko a potom zvolte **kopírovat do schránky** tlačítko v rozevírací nabídce zkopírovat zabezpečená adresa URL pro úložiště GitHub.

   ![Tlačítko klonování Githubu](./media/VSIDE_Code_Clone.png)

1. Ve Visual Studiu zvolte **Team Explorer** otevřete Průzkumník týmových projektů. Pokud se nezobrazí na kartě, ho otevřete v **zobrazení** > **Team Explorer**.

1. V nástroji Team Explorer pod **místní úložiště Git** zvolte **klon** příkaz a vložte adresu URL stránky Githubu do textového pole.

   ![Klonování projektu](./media/VSIDE_Code_Clone2.png)

1. Vyberte **klon** tlačítko klonovat soubory projektu do místního úložiště Git. V závislosti na velikosti úložiště tento proces může trvat několik minut.

1. Po úložišti má klonování k vašemu systému, v nástroji Team Explorer klikněte **otevřete** příkazu v nabídce kontextu (klikněte pravým tlačítkem) nově naklonovaný úložišti.

   ![Klonovaný úložišti](./media/VSIDE_Code_Clone3.png)

1. Vyberte **zobrazit zobrazení složky** příkaz k prohlížení souborů v Průzkumníku řešení

   ![Nastaví zobrazení složky](./media/VSIDE_Code_Clone3_show.png)

   Teď můžete procházet složky a soubory v klonovaném úložišti a zobrazení a hledání kód v sadě Visual Studio editoru kódu kompletní s zabarvení syntaxe a další funkce.

|         |         |
|---------|---------|
|  ![film ikonu fotoaparátu pro video](../install/media/video-icon.png "přehrát video")|    [Přehrát video,](https://mva.microsoft.com/en-us/training-courses/getting-started-with-visual-studio-2017-17798?l=lp3TOKD6D_6711787171) o tom, jak klonovat a otevřete kód z úložiště GitHub v sadě Visual Studio. |

## <a name="run-and-debug-your-code"></a>Spuštění a ladění kódu

Můžete ladit kód v sadě Visual Studio bez projekt nebo řešení! K ladění některé jazyky, možná budete muset zadat platný *spuštění souboru* v základu kódu, jako je skript, spustitelný soubor nebo projektu. Pole se seznamem rozevíracího seznamu vedle položky **spustit** tlačítka na panelu nástrojů zobrazí seznam všech položek spuštění, které zjistí Visual Studio, a také položky konkrétně určíte. Visual Studio tento kód spustí nejprve při ladění kódu.

Konfigurace váš kód pro spuštění v sadě Visual Studio se liší v závislosti na tom, jaký druh kód je a jaké jsou nástroje pro sestavení.

### <a name="codebases-that-use-msbuild"></a>Základy kódu využívající MSBuild

Na základě MSBuild základy kódu může mít víc konfigurací sestavení, které se zobrazují v **spustit** tlačítka rozevíracího seznamu. Vyberte soubor, který chcete použít jako položku při spuštění a potom vyberte **spustit** tlačítko Začněte ladění.

> [!NOTE]
> Pro základy kódu C# a Visual Basic, musíte mít **vývoj aplikací .NET** zatížení nainstalována. Pro základy kódu C++, musíte mít **vývoj aplikací s jazykem C++** zatížení nainstalována.

### <a name="codebases-that-use-custom-build-tools"></a>Základy kódu této použití vlastní sestavovací nástroje

Pokud vaše codebase používá vlastní nástroje pro sestavení, pak se musí zjistit sady Visual Studio jak sestavit kódu pomocí *úlohy sestavení* které jsou definovány v *.json* souboru. Další informace najdete v tématu [přizpůsobení sestavení a ladění úloh](../ide/customize-build-and-debug-tasks-in-visual-studio.md).

### <a name="codebases-that-contain-python-or-javascript-code"></a>Základy kódu, který obsahovat kód, Python nebo JavaScript

Pokud vaše základu kódu obsahuje kód, Python nebo JavaScript, nemusíte konfigurovat *.json* soubory, ale je nutné nainstalovat odpovídající úlohy. Je také potřeba nakonfigurovat spouštěcího skriptu:

1. Nainstalujte [Node.js vývoj](https://www.visualstudio.com/vs/node-js/) nebo [vývoj Python](https://www.visualstudio.com/vs/python/) zatížení výběrem **nástroje** > **funkcí a nástrojů pro získání...** , nebo zavírání sady Visual Studio a spuštěním instalační program Visual Studio.

   ![Vývoj zatížení Node.js a Python](media/python_nodejs_workloads.png)

1. V **Průzkumníku řešení**, v nabídce klikněte pravým tlačítkem nebo kontextu soubor JavaScript nebo Python, vyberte **nastavit jako položku při spuštění** příkaz.

1. Vyberte **spustit** tlačítko Začněte ladění.

### <a name="codebases-that-contain-c-code"></a>Základy kódu, které obsahují C++ – kód

Informace o otevření C++ – kód bez řešení a projektů v sadě Visual Studio najdete v tématu [projekty otevřít složku pro jazyk C++](/cpp/ide/non-msbuild-projects).

### <a name="codebases-that-contain-a-visual-studio-project"></a>Základy kódu obsahující projekt sady Visual Studio

Pokud váš kód složka obsahuje projekt sady Visual Studio, můžete určit projektu jako položku při spuštění.

![Projekt sady jako položku při spuštění](media/customize-set-project-as-startup-item.png)

**Spustit** tlačítka text se změní, aby odrážela, že je projekt položku při spuštění.

![Projekt na tlačítko Start](media/customize-start-button-project.png)

## <a name="see-also"></a>Viz také

- [Přizpůsobení sestavení a ladění úloh](../ide/customize-build-and-debug-tasks-in-visual-studio.md)
- [Otevřete složku projektů jazyka C++](/cpp/ide/non-msbuild-projects)
- [CMake projektů v jazyce C++](/cpp/ide/cmake-tools-for-visual-cpp)
- [Psaní kódu v editoru kódu a text.](../ide/writing-code-in-the-code-and-text-editor.md)