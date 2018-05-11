---
title: Včetně balíček NuGet do projektu
description: Tento dokument popisuje postupy zahrnutí balíček NuGet do projektu Xamarin. Provede hledání a stahování balíčku, a také představení funkcí pro integraci IDE.
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 5C800815-0B13-4B27-B017-95FCEF1A0EA2
ms.openlocfilehash: f251080351f1e448d250798c4f9a758114a6e5ab
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
# <a name="including-a-nuget-package-in-your-project"></a>Včetně balíček NuGet do projektu

NuGet je nejoblíbenější Správce balíčků pro .NET – vývoj a je součástí sady Visual Studio pro Mac a Visual Studio v systému Windows. Můžete vyhledat a přidat do vašich projektů Xamarin.iOS a Xamarin.Android pomocí buď IDE balíčky.

Tento dokument vypadá na tom, jak zahrnout balíček NuGet do projektu a předvádí řetězu nástroj, který umožňuje bezproblémový proces.

## <a name="nuget-in-visual-studio-for-mac"></a>NuGet v sadě Visual Studio pro Mac

K předvedení funkčnosti balíčku NuGet jsme budete se nejprve provede procesem vytvoření nové aplikace a přidání balíčku do. Potom probereme IDE funkce, které pomáhají spravovat balíčky.

## <a name="create-a-new-project"></a>Vytvoření nového projektu

Nejprve vytvořte projekt s názvem `HelloNuget` jak je uvedeno dále. Tento příklad ukazuje šabloně jediné zobrazení aplikace iOS, ale žádný typ, podporované projekt by fungovat:

![Vytvořit nový iOS projektu](media/nuget-walkthrough-NewProject.png)

## <a name="adding-a-package"></a>Přidání balíčku

S projektem otevřeným v nástroji Visual Studio pro Mac, klikněte pravým tlačítkem na **balíčky** složky v **řešení Pad** a vyberte **přidat balíčky...** :

![Přidat novou akci kontextu balíček NuGet](media/nuget-walkthrough-PackagesMenu.png)

Spustí se _přidat balíčky..._  okno. Ujistěte se, že zdroj rozevíracího seznamu, je nastavená na `nuget.org`:

![Seznam zdrojů rozevíracího seznamu](media/nuget-walkthrough-Source.png)

Pokud balíček otevře okno ho načte seznam balíčků z výchozí zdroj: nuget.org. Počáteční výsledky vypadat takto:

![Seznam balíčků NuGet](media/nuget-walkthrough-AddPackages1.png)

Pomocí vyhledávacího pole v pravém horním rohu najít konkrétní balíček, například `azure`. Když jste si balíček, který chcete použít, vyberte ho a klikněte na tlačítko **přidat balíček** tlačítko Zahájit instalaci.


[Přidejte balíček NuGet Azure](media/nuget-walkthrough-AddPackages2.png)

Po stažení balíčku přidá se do projektu. Řešení se změní následujícím způsobem:

* **Odkazy** uzlu bude obsahovat seznam všech sestavení, které jsou součástí balíčku NuGet.
* **Balíčky** uzlu zobrazí každý balíček NuGet, který jste si stáhli. Můžete aktualizovat nebo odebrat balíček z tohoto seznamu.
* A **packages.config** soubor bude přidán do projektu. Tento soubor XML se používá pomocí rozhraní IDE pro sledování jaké verze balíčku se odkazuje v tomto projektu. Tento soubor by neměl být ručně upravovat, ale byste měli mít ve správě verzí. Všimněte si, že soubor project.json jde použít místo souboru packages.config. Soubor project.json je nový formát souboru balíčku zavedené 3 NuGet, který podporuje přenositelné obnovení. Podrobnější informace o souboru project.json najdete v [NuGet dokumentaci](http://docs.microsoft.com/NuGet/Schema/Project-Json). Soubor project.json je nutné přidat ručně a projekt se zavře a znovu otevřít před souboru project.json se používá v sadě Visual Studio for Mac.

## <a name="using-nuget-packages"></a>Pomocí balíčků NuGet

Jakmile se přidal balíček NuGet a aktualizovat odkazy na projekt můžete ovládat rozhraní API stejně jako u jakékoli odkaz na projekt.

Zajistěte, aby přidal jakékoli požadované `using` direktivy do horní části souboru:

```csharp
using Newtownsoft.json;
```

Většina NuGet poskytují další informace, jako je například stránka odkaz README nebo produktu Project na zdrojové Nuget. Odkaz k tomuto obvykle naleznete v balíčku blurb na stránce Přidat balíčky:

[Propojení projektu stránky zobrazení](media/nuget-walkthrough-project-page.png)

<a name="Package_Updates" class="injected"></a>

## <a name="package-updates"></a>Aktualizace balíčků

Aktualizace balíčků můžete provést buď všechny najednou, kliknutím pravým tlačítkem na **balíčky** uzlu, nebo v jednotlivých součástí.

Klikněte pravým tlačítkem na **balíčky** pro přístup k místní nabídky:

![Balíčky nabídky](media/nuget-walkthrough-PackagesMenu.png)

*   **Přidání balíčků** -otevře se okno pro přidání další balíčky do projektu.
*   **Aktualizace** – kontroluje zdrojového serveru pro každý balíček a stáhne všechny novější verze.
*   **Obnovit** -stáhne všechny chybějící balíčky (bez aktualizace existující balíčky na novější verze).

Aktualizace a možností obnovení jsou také k dispozici na úrovni řešení a mít vliv na všechny projekty v řešení. 

Klikněte pravým tlačítkem můžete také na jednotlivé balíčky pro přístup z kontextové nabídky:

![Balíčky nabídky](media/nuget-walkthrough-PackageMenu.png)

*   **Číslo verze** -číslo verze se zakázanou položku nabídky – je poskytována jenom informativní charakter.
*   **Aktualizace** – kontroluje zdrojového serveru a soubory ke stažení na novější verzi (pokud existuje).
*   **Odebrat** – odebere balíček z tohoto projektu a odebere relevantní sestavení z odkazů projektu.


## <a name="adding-package-sources"></a>Přidání zdroje balíčků

Balíčky, které jsou k dispozici pro instalaci se původně načítají z nuget.org. Ale můžete přidat jiných umístění balíčku pro Visual Studio for Mac. To může být užitečné pro testování vlastní balíčky NuGet ve vývoji a použít privátní server NuGet uvnitř vaší společnosti nebo organizace.

V sadě Visual Studio pro Mac, přejděte na **Visual Studio > Předvolby... > NuGet > zdroje** můžete zobrazit a upravit seznam zdrojů balíčků. Všimněte si, že zdroje může být vzdálený server (zadaný pomocí adresy URL) nebo do místního adresáře. 

![Zdroje balíčků](media/nuget-walkthrough-PackageSource.png)

Klikněte na tlačítko **přidat** nastavit nový zdroj. Zadejte popisný název a adresu URL (nebo cestu k souboru) ke zdroji balíčku. Pokud je zdroj zabezpečenému webovému serveru, zadejte uživatelské jméno a heslo, i, v opačném případě ponechte prázdné tyto položky:

![Přidat zdroje balíčku](media/nuget-walkthrough-PackageSource2.png)

Různých zdrojů lze vybrat, pak při hledání balíčky:

![Přidat zdroje balíčku](media/nuget-walkthrough-PackageSource3.png)

## <a name="version-control"></a>Správa verzí

Popisuje dokumentace NuGet [bez potvrzení balíčky do správy zdrojového kódu pomocí nástroje NuGet](https://docs.microsoft.com/nuget/consume-packages/packages-and-source-control). Pokud nechcete uložit binární soubory a nepoužívané informace do správy zdrojového kódu, můžete nakonfigurovat sady Visual Studio pro Mac, aby automaticky obnovit balíčky ze serveru. To znamená, že když vývojáři načte projektu od správy zdrojového kódu poprvé, sady Visual Studio pro Mac se automaticky stáhněte a nainstalujte požadované balíčky.

![Automatické obnovení balíčků](media/nuget-walkthrough-AutoRestore.png)

Dokumentaci k systému konkrétní zdroj ovládacího prvku podrobnosti o tom, jak vyloučit `packages` adresář ze zobrazení.

