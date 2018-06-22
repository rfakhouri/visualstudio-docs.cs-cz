---
title: Prohlídka sady Visual Studio IDE
ms.date: 11/15/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 86b8d9f5e577395234dc4d7bb8de30283b0df8af
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36280508"
---
# <a name="quickstart-first-look-at-the-visual-studio-ide"></a>Rychlý úvod: První pohled na Visual Studio IDE

V této 5 až 10 minut Úvod do integrované vývojové prostředí (IDE) sady Visual Studio provedeme prohlídka některých systému windows, nabídky a další funkce uživatelského rozhraní.

Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) stránky instalaci zdarma.

## <a name="start-page"></a>Úvodní stránka

První věc, zobrazí se po spuštění sady Visual Studio je pravděpodobně **– úvodní stránka**. **– Úvodní stránka** slouží jako "centrum", které vám pomohou najít příkazy a soubory, které potřebujete rychlejší projektu. **Poslední** objeví projekty a složky, které jste nedávno pracovali. V části **nový projekt**, můžete kliknutím na odkaz zobrazíte **nový projekt** dialogové okno, nebo v části **otevřete**, můžete otevřít existujícího projektu nebo složky kódu. Na pravé straně je informační kanál nejnovější informace pro vývojáře.

![VS úvodní stránku](media/quickstart-IDE-start-page.png)

Pokud zavřete **– úvodní stránka** a chcete se znovu, můžete ho znovu otevřít z **souboru** nabídky.

![nabídka Soubor](media/quickstart-IDE-file-menu-large.png)

Chcete-li pokračovat, prohlížení rozhraní IDE, vytvoříme nový projekt.

1. Na **– úvodní stránka**, do vyhledávacího pole v části **nový projekt**, zadejte `console` pro filtrování seznamu typy projektů. Vyberte buď C# nebo VB **konzoly aplikace (rozhraní .NET Framework)**. (Případně, pokud jste jazyka C++, Javascript nebo jiných vývojáře jazyka, klidně k vytvoření projektu v jednom z těchto jazyků. Uživatelské rozhraní, které jsme budete vidí je podobné pro všechny jazyky.)

1. V **nový projekt** dialogové okno, přijměte výchozí název projektu a zvolte **OK**.

   Vytvoření projektu a vytvoří soubor s názvem *Program.cs* nebo *soubor Program.vb* se otevře v **Editor** okno. **Editor** zobrazuje obsah souborů a je, kde můžete to udělat většinu kódování práce v sadě Visual Studio.

## <a name="solution-explorer"></a>Průzkumník řešení

**Průzkumník řešení** zobrazuje grafické reprezentace hierarchii souborů a složek ve vaší složky kódu, projekt nebo řešení. Můžete procházet hierarchii a přejděte k souboru v **Průzkumníku řešení**.

![Průzkumník řešení](media/quickstart-IDE-solution-explorer.png)

## <a name="menus"></a>Nabídky

Panel nabídek v horní části IDE skupiny příkazy do kategorií. Například **projektu** nabídka obsahuje příkazy související s k práci v projektu. Na **nástroje** nabídce integrovaného vývojového prostředí můžete upravit zvolením **možnosti**, nebo přidávat funkce do instalace výběrem **funkcí a nástrojů pro získání**.

![Panel nabídek](media/quickstart-IDE-menu-bar.png)

Umožňuje otevřít **seznam chyb** okno a vybrat **zobrazení** nabídce a potom **seznam chyb**.

## <a name="error-list"></a>Seznam chyb

**Seznam chyb** zobrazí chyby, upozornění a zprávy týkající se aktuální stav vašeho kódu. Kdyby existovalo všechny chyby (například překlepem syntaxe) v souboru nebo kdekoli v projektu, by byly uvedeny zde.

![Seznam chyb](media/quickstart-IDE-error-list.png)

## <a name="output-window"></a>Výstup – okno

**Výstup** zobrazí okno výstup zpráv ze sestavení a Správa zdrojového kódu.

Vytvořme projektu zobrazíte některé protokolování výstupu. Z **sestavení** nabídce zvolte **sestavit řešení**. **Výstup** okno automaticky získá fokus a zobrazí zprávu úspěšném sestavení.

![Okno Výstup](media/quickstart-IDE-output.png)

## <a name="quick-launch"></a>Snadné spuštění

**Snadné spuštění** pole je rychlý a snadný způsob, jak pretty mnohem nic v prostředí IDE. Můžete zadat nějaký text související s co chcete udělat, a se vám zobrazí seznam možností, které se vztahují na text. Řekněme například, že chceme zvýšit podrobností výstupu sestavení. Chcete-li zobrazit další informace o protokolování, že je to, co přesně sestavení:

1. Zadejte `verbosity` do **Snadné spuštění** pole a potom vyberte **projekty a řešení--> sestavení a spuštění** pod **možnosti** kategorie.

   ![Snadné spuštění pole](media/quickstart-IDE-quick-launch.png)

   **Možnosti** otevře dialogové okno s **sestavit a spustit** stránka Možnosti.

1. V části **výstup sestavení projektu MSBuild podrobností**, zvolte **normální**a potom klikněte na **OK**.

1. Nyní jsme budete sestavte projekt znovu kliknutím pravým tlačítkem na **ConsoleApp1** projektu v **Průzkumníku řešení**a výběr **znovu sestavit** v místní nabídce.

   Tentokrát **výstup** v okně se zobrazí podrobnější protokolování z procesu sestavení, včetně souborů, které byly zkopírovány where.

## <a name="send-feedback-menu"></a>Odeslat zpětnou vazbu nabídky

Musí se vyskytnou potíže při používáte Visual Studio, nebo pokud máte návrhy na zlepšení produktu, můžete použít **odeslat zpětnou vazbu** nabídce v horní části IDE, vedle položky **Snadné spuštění**pole.

![Odeslat zpětnou vazbu nabídky](media/quickstart-IDE-send-feedback.png)

## <a name="next-steps"></a>Další kroky

Jsme si prohlédli uvedeno několik funkcí prostředí Visual Studio IDE se seznámit s uživatelské rozhraní. Prozkoumat další:

- Přejděte **obecné elementy uživatelského rozhraní** části dokumentace VS, které jde do podrobněji windows, jako [seznam chyb](../ide/reference/error-list-window.md), [výstup – okno](../ide/reference/output-window.md), [ Vlastnosti – okno](../ide/reference/properties-window.md), a [dialogové okno Možnosti](../ide/reference/options-dialog-box-visual-studio.md)

- Podrobnější prohlídku rozhraní IDE a i dabble v ladění, v [přehled Visual Studio IDE](../ide/visual-studio-ide.md)

## <a name="see-also"></a>Viz také:

- [Rychlý úvod: Přizpůsobení integrovaného vývojového prostředí](../ide/personalizing-the-visual-studio-ide.md)
- [Rychlý úvod: Kódování v editoru](../ide/quickstart-editor.md)
- [Rychlý úvod: Projekty a řešení](../ide/quickstart-projects-solutions.md)