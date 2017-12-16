---
redirect_url: /visualstudio/ide/visual-studio-ide
ms.openlocfilehash: 5f1fa39d6e6cde1664a8aaa34aed7cba726b1d56
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/15/2017
---
# <a name="get-started-with-visual-studio"></a>Začínáme s Visual Studio
Visual Studio je výkonný nástroj pro vývoj aplikací. Pokud jste tak ještě neučinili, pokračujte a stáhněte a nainstalujte [Visual Studio](https://www.visualstudio.com/vs/). Podívejte se video [Začínáme s Visual Studio – nastavení vaší IDE](https://www.youtube.com/watch?v=xLCedknQkN0&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=1) Další informace o stažení sady Visual Studio a její konfiguraci, způsob, jakým chcete.

## <a name="visual-studio-tour"></a>Prohlídka Visual Studio
Visual Studio má skupina nástroje systému windows, nabídek a panelů nástrojů souhrnně označuje jako integrované vývojové prostředí nebo IDE. Visual Studio IDE pomůže vám s tím vývojářských úloh. Zde je stručný přehled IDE položek, které budete pravděpodobně používat nejčastěji.

### <a name="code-editor"></a>Editor kódu
Jeden nejvíce zatížen nástroj Windows v sadě Visual Studio, to je kde zápisu, zobrazení a procházet váš kód.

![Editor kódu](../ide/media/VSIDE_CodeWindow.png)

Při zadávání kódu editoru kódu vám pomůže rychleji a snadno zápisu a najít kódu nabízí funkce, jako je například dokončování příkazů, zabarvení syntaxe, režimu mapy a další. Další informace najdete v tématu video [Začínáme s Visual Studio – úpravy a pohyb kódu](https://www.youtube.com/watch?v=4glwwioCVjA&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=5)

Některé typy řešení může zahrnovat windows, nazvaný *forms*, jako jsou formuláře Windows Presentation Foundation (WPF), Windows forms, forms rozšiřitelné aplikace Markup Language (XAML) a další. V takových případech se také zobrazí vizuálního návrháře v tomto prostor, který umožňuje přetažení ovládací prvky, jako jsou tlačítka a seznamy do formuláře, který uživatelé komunikovat s při jejich spuštění aplikace.

### <a name="solution-explorer"></a>Průzkumník řešení
Volá se okno nástroje **Průzkumníku řešení** uvádí všechny soubory s kódem. Průzkumník řešení pomáhá organizovat kód seskupením jeho soubory do řešení a projekty. Je volána projektu tučným písmem *spouštěný projekt*. Je první kód, který je spuštěn při spuštění řešení. Můžete změnit počáteční projekt. Podívejte se video [Začínáme s Visual Studio – stavební bloky rozhraní IDE](https://www.youtube.com/watch?v=JHc3_gsCmZg&index=2&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK) Další informace.

![Průzkumník řešení sbalené uzly](../ide/media/VSIDE_SolutionExplorer2_callouts.png)

 Kromě řešení a projekty Průzkumník řešení seznam všech souborů do každého projektu po rozbalení uzlu projektu. Každý projekt obsahuje jeden nebo více souborů, jako jsou soubory zdrojového kódu a soubory prostředků, například obrázky nebo knihovny.

![Průzkumník řešení](../ide/media/VSIDE_SolutionExplorer3.png)

Zobrazit vlastnosti pro řešení, projekty a soubory, vyberte **vlastnosti** příkaz v místní nabídce, nebo zvolte **zobrazení, vlastnosti – okno** v nabídce.

![Vlastnosti – okno](../ide/media/VSIDE_SolutionExplorer4.png)

Nemáte k vytvoření řešení nebo projektu, ale, abyste mohli začít kódování. Můžete jednoduše přejít přímo na a soubory otevřené kódu v sadě Visual Studio, jako jsou například soubory klonovat z úložiště Git a jejich úpravy hned spustit. Soubory se zobrazí v Průzkumníku řešení a get zabarvení syntaxe, základní dokončování a další, stejně jako tradiční řešení. V tématu [vývoj kódu v sadě Visual Studio bez projekty a řešení](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) Další informace.

### <a name="toolbar-and-menus"></a>Panel nástrojů a nabídek
Chcete-li spustit projekt, vytvářejí nová řešení, ukládat soubory, a informace, použijte příkazy nástrojů a nabídky sady Visual Studio. Například když váš kód je připraven ke spuštění pro ladění, můžete **spustit** tlačítka na panelu nástrojů, nebo můžete zvolit **ladit, spustit ladění** v nabídce. Chcete-li vytvořit nové řešení, zvolte **nový projekt** tlačítko, nebo zvolte **soubor nové, projektu** v nabídce a tak dále.

![Panel nástrojů Visual Studio](../ide/media/VSIDE_SolutionExplorer5_callouts.png)

Všimněte si, že ikon na panelu nástrojů a příkazy nabídky můžete změnit v závislosti na kontextu, což znamená aktuálně vybranou položku. Téměř všechny příkazy je přístupná prostřednictvím příkazy klávesnice, a také pomocí myši.

### <a name="team-explorer"></a>Team Explorer
**Team Explorer** umožňuje připojení k nástroje pro řízení zdrojového například [Git](https://git-scm.com/) a [Team Foundation verze ovládacího prvku (TFVC)](https://www.visualstudio.com/en-us/docs/tfvc/overview) uložit místně kód nebo sdílet s ostatními na hostovaný Služba. Můžete ji použít i ke sledování a další úkoly.

Viz videím [Začínáme s Visual Studio – stavební bloky rozhraní IDE](https://www.youtube.com/watch?v=JHc3_gsCmZg&index=2&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK) a [Začínáme s Visual Studio – otevření projektu od správy zdrojového kódu](https://www.youtube.com/watch?v=pc9vX_4RGV4&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=3) Další informace.

![Team Explorer](../ide/media/TeamExplorer.png)

### <a name="output-window"></a>Výstup – okno
**Výstup** je okno, kde Visual Studio odešle jeho oznámení, jako je ladění a chybové zprávy, upozornění kompilátoru, publikování stavové zprávy a další. Každý typ zprávy má svou vlastní kartě.

![Výstup – okno](../ide/media/VSIDE_OutputWindow.png)

Další informace o tom, jak používat ve výstupním okně pro ladění, najdete v části [The výstup – okno při ladění pomocí sady Visual Studio](https://blogs.msdn.microsoft.com/visualstudioalm/2015/02/09/the-output-window-while-debugging-with-visual-studio/).

## <a name="first-steps"></a>První kroky
- **Získat velký obrázek** – Pokud chcete získat přehled o řadu hlavní funkce v sadě Visual Studio, prohlídka! V tématu [prohlídka funkce Visual Studio IDE](../ide/visual-studio-ide.md).
- **Instalační program** – Další informace o stažení a instalaci sady Visual Studio naleznete v tématu [nainstalovat Visual Studio 2017](../install/install-visual-studio.md).
- **Základy** – Pokud chcete získat další informace o tom, jak Visual Studio funguje, najdete v části [získat spuštění vývoj pomocí sady Visual Studio](../ide/get-started-developing-with-visual-studio.md).
- **Nastavení** – Pokud chcete získat informace o přizpůsobení Visual Studio, aby vyhovovala požadavkům rádi pracujete. V tématu [přizpůsobení sady Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).
- **Kurzy** – Další informace o tom, jak vyvíjet kódu v sadě Visual Studio, absolvovat kurz, jako například [Začínáme s Visual C# a Visual Basic](../ide/getting-started-with-visual-csharp-and-visual-basic.md) nebo [Začínáme s C++ v sadě Visual Studio](../ide/getting-started-with-cpp-in-visual-studio.md).
- **Videa** – Pokud chcete získat další informace o dalších funkcích a aspekty sady Visual Studio, podívejte se na videa na [Microsoft Visual Studio kanál](https://www.youtube.com/user/VisualStudio/videos) na serveru, Visual Studio videa na YouTube [Channel 9](https://channel9.msdn.com/Tags/visual+studio), nebo na [Microsoft Virtual Academy](https://mva.microsoft.com/product-training/visual-studio-courses#!jobf=Developer).

## <a name="access-cloud-based-resources"></a>Přístup k prostředkům cloudu
Pokud chcete použít cloudové prostředky v aplikaci nebo hra, můžete to udělat tak, že začleníte [služby Azure](https://azure.microsoft.com/en-us/services/). Získáte sadu Azure SDK pro .NET tak, že instalace **Azure development** zatížení pomocí nového instalačního programu Visual Studio. Balíčky, které se instalují, jsou na stejné funkční úrovni jako verze 2.9.5 této sady SDK. Pro tuto verzi sady Visual Studio a všechny budoucí verze bude sada Azure SDK pro .NET dostupná jenom prostřednictvím instalačního programu sady Visual Studio.

Po instalaci pracovního vytížení Azure development, bude k dispozici v sadě Visual Studio, volá se nové okno nástroje **Průzkumník cloudu**. Průzkumník cloudu vám umožňuje procházet a spravovat Azure prostředky a prostředky z Visual Studia. Pokud konkrétní operace vyžaduje, aby na portálu Azure, Průzkumník cloudu poskytuje odkazy, které vás zavedou na místě v portálu Azure, které budete muset přejít.

![Průzkumník cloudu](../ide/media/VSIDE_CloudExplorer.png)

Další informace o používání nástroje Průzkumník cloudu najdete v tématu [Správa Azure prostředků pomocí Průzkumníka cloudu](https://azure.microsoft.com/en-us/documentation/articles/vs-azure-tools-resources-managing-with-cloud-explorer/).
Instalace pracovního vytížení Azure development vám také [Visual Studio Tools for Azure](https://www.visualstudio.com/vs/azure-tools/) i jiné související nástroje.

## <a name="tips-and-tricks"></a>Tipy a triky
Zkratky a užitečné tipy a triky na tom, jak získat další mimo Visual Studio naleznete v následujících tématech.
- [Začínáme s Visual Studio – tipy a triky](https://www.youtube.com/watch?v=vmXqGwn1Glk&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=4)
- [Tipy pro vyšší produktivitu v sadě Visual Studio](../ide/productivity-tips-for-visual-studio.md)
- [Rady a tipy k sadě Visual Studio](https://channel9.msdn.com/events/TechEd/2013/DEV-B353)
- [Rady a tipy k ladění jazyka C++](https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/C-Plus-Plus-Debugging-Tips-and-Tricks)
- [Visual Studio nejvíce užitečné (a využívané) tipy [blog Scott Hanselman]](https://www.hanselman.com/blog/VisualStudiosMostUsefulAndUnderusedTips.aspx)
- [Začínáme s Visual Studio – rozšíření instalaci sady Visual Studio](https://www.youtube.com/watch?v=MWLLQaknRZY&list=PLReL099Y5nRfw6VNvzMkv0sabT2crbSpK&index=7)
