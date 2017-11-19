---
redirect_url: /visualstudio/ide/optimize-visual-studio-startup-time/
ms.openlocfilehash: 6ba351d5b395caaddd12021b09f8792cd19b2905
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
Title: "načítání optimalizovat řešení v sadě Visual Studio | Microsoft Docs"ms.custom:" "ms.date: ms.reviewer 31/08/2017:" "ms.suite:" "ms.tgt_pltfrm:" "ms.topic:"článku"helpviewer_keywords: 
  - "spuštění [Visual Studio]"
  - "optimalizace čas spuštění [Visual Studio]"
  - "urychlit počáteční čas [Visual Studio]" ms.assetid: 84989983-84bc-4f81-97a8-2131e3a25138 caps.latest.revision: 4 Autor: ms.author "gewarren": "gewarren" správce: ghogen f1_keywords: 
  - "vs.performancecenter" ms.technology: 
  - "vs-ide Obecné"
---
# <a name="optimize-solution-loading-in-visual-studio"></a>Optimalizace řešení načítání v sadě Visual Studio
Mnoho řešení obsahovat velké množství projekty, které ovlivňují čas potřebný k načtení těchto řešení. Ale v prostředích team vývojáři obvykle fungovat v různých podmnožině těchto projekty a nemusíte načíst všechny jednotlivých projektů.

Visual Studio 2017 podporuje **lightweight řešení zatížení**. Když je povolený režim zatížení (dolní limit) lightweight řešení, načte Visual Studio 2017 malou podmnožinu projekty místo načítání všechny projekty v řešení pro velká. Většina běžně používané funkcí IDE fungovat v režimu dolní limit, a poskytuje možnosti pro sestavit, vyhledávání a ladění na celé řešení. (Hlavní nepodporované funkce v režimu dolní limit je upravit a pokračovat.)  

> [!NOTE]
> Tento obsah platí pro Visual Studio 2017 Update 3

Pro velká řešení s více než 30 projekty dolní limit obvykle načte řešení dvakrát jako rychlé (v průměru). Zatímco většina funkcí IDE fungovat v režimu dolní limit, může vyžadovat některé funkce IDE všechny projekty, které mají být načtena. V těchto případech Visual Studio automaticky načte celé řešení tak, aby můžete použít funkci. V nejhorším případě skončili načítání všechny projekty v lightweight režimu. 

Pokud na projekt, který aktuálně používáte o funkci IDE, načte Visual Studio příslušné projekty pro vás. Například pokud se pokoušíte vytvořit nebo otevřít diagramu tříd pro vyberte projekt, Visual Studio automaticky načte odpovídající projekty. Seznam podrobné funkcí se odkazuje v následujících částech.

Následující části vysvětlují postup při povolování zatížení lightweight řešení a také můžete rozhodnout, zda chcete povolit funkci nápovědy.

## <a name="enable-or-disable-lightweight-solution-load"></a>Povolit nebo zakázat zatížení lightweight řešení

Název řešení v Průzkumníku řešení klikněte pravým tlačítkem a vyberte **povolit zatížení řešení Lightweight**. Až vyberete možnost, musíte zavřete a znovu otevřete řešení, aby aktivovat zatížení lightweight řešení.

> [!NOTE]
> Podobným způsobem použít pro zakázání dolní limit. Zakázat zatížení lightweight řešení, vyberte **zakázat Lightweight načíst řešení**, pak zavřete a znovu otevřete řešení. 

![Průzkumník řešení](../ide/media/VSIDE_LSL_Solution_Setting.png)

## <a name="global_solution_load_settings"></a>Konfigurace globálního nastavení pro zatížení lightweight řešení

Můžete globálně zakázat nebo můžete nakonfigurovat dolní limit pro všechna řešení tak, že zvolíte **nástroje > Možnosti > projekty a řešení**.

![Možnosti nástrojů – dialogové okno](../ide/media/VSIDE_LightweightSolutionLoad.png)

## <a name="how-does-lightweight-solution-load-work-behind-the-scenes"></a>Jak funguje lightweight řešení zatížení na pozadí?

Při načítání řešení, Visual Studio pamatuje projekty, které dříve otevřena a načte pouze ty projekty. Všechny ostatní projekty jsou viditelné v Průzkumníku řešení ale není načteno. Jakmile rozbalit projektu nebo klikněte pravým tlačítkem na projekt, Visual Studio automaticky načte daného projektu. Automatické načítání projekty obvykle trvá méně než sekundu ale může trvat delší dobu, některé projekty. Však umožňuje sadě Visual Studio IDE funkcí, jako je vyhledávání, ladění, vytváření a Správa zdrojového kódu, které lze spustit ve celé řešení. Například můžete hledat v rámci celého řešení Přestože jenom pár projekty jsou načtena v lightweight režimu. 

Při rozšiřování více projektů sady Visual Studio pamatuje seznam rozšířené projektů. Když znovu otevřete řešení, Visual Studio automaticky načte projekty, které jste dříve rozbalený.

## <a name="visual-studio-prompts-developers-likely-to-see-significant-performance-gains"></a>Visual Studio vyzve vývojáři pravděpodobně zobrazí výrazné zvýšení výkonu

Ze sady Visual Studio telemetrie velkých řešení s více než 30 projekty výrazně těžit z dolní limit režimu. V důsledku toho jsme výzvu vývojářům velkých řešení můžete vyzkoušet na dolní limit režimu. Většina vývojářů, kteří zkuste dolní limit pro první koncový čas díky v pravidelných intervalech. 

## <a name="visual-studio-makes-recommendations-to-turn-on-lightweight-solution-load-based-on-heuristics"></a>Sada Visual Studio provádí doporučení zapnutí zatížení lightweight řešení podle heuristiky

Ve výchozím nastavení Visual Studio zapne dolní limit pro uživatele, kteří se s největší pravděpodobností, abyste mohli využívat. Pokud máte více řešení, Visual Studio nabízí režim dolní limit pro řešení, které budou pravděpodobně zobrazíte výrazné zvýšení výkonu. Pokud vyberete možnost lightweight režimu **rozhodnout nechat Visual Studio** (výchozí možnost), Visual Studio může otevřete řešení v lightweight režimu založeném na heuristiky. Panel zpráv určuje, zda řešení v lightweight režimu. Když se zobrazí na panelu zpráv, máte možnost Další informace, nebo aktualizovat nastavení.

![Automaticky otevíraném okně](../ide/media/VSIDE_LSL_Popup.png)

## <a name="ide-features-fully-supported-in-lightweight-mode"></a>Funkce IDE plně podporované v režimu lightweight

|Funkce|Podporované v režimu Lightweight?|
|-|-|-|
|IntelliSense|Ano|
|Hledat|Ano|
|Ladění|Ano|
|Sestavení|Ano|
|Kód navigace (Přechod na definici a najít všechny odkazy)|Ano|
|Kód přehledu|Ano|
|Statické analýza kódu|Ano|
|Nasazení a publikování|Ano|
|Přidávání a odebírání odkazů|Ano|
|Cílení na více|Ano|
|IntelliTrace|Ano|
|Testování částí za provozu|Ano|
|IntelliTest|Ano|
|Napodobeniny Microsoft|Ano|
|Upravit a pokračovat|Nepodporováno|
|Testování částí|Vyžaduje načítání projektů testů, za nímž následuje sestavení řešení|

## <a name="scenarios-in-which-lightweight-solution-loads-the-appropriate-projects-to-complete-the-operation"></a>Scénáře, ve kterých lightweight řešení načte odpovídající projekty k dokončení operace

Pokud nepracujete na projekt v řešení, není v režimu lightweight načíst projekt. Pro některé funkce jsou automaticky načíst další projekty pro podporu tohoto scénáře funkce. (Plánujeme zajistit minimalizovat tento seznam scénářů. ) Pro tyto scénáře sady Visual Studio buď načte projekty sám sebe nebo vás vyzve k načtení projekty podle potřeby.

|Kategorie|Problém|
|-|-|-|
|Testování částí|Projekty, které nejsou aktuálně načtené se nezobrazí v seznamu projektů testů pro Průvodce "Vytvoření IntelliTest" i "Vytvoření jednotkové testování". </br>Je nutné zavést projekty, pro které chcete vytvořit testy (můžete rozbalit uzel projektu načíst projekt).|
|Diagramy tříd|Pokud vytvoříte nebo otevřete diagramu tříd projektu, Visual Studio automaticky načte projektů, které jsou přímé závislosti tohoto projektu. </br>Pokud není celé řešení načten, jsme vypnout ověření zastaralé artefaktů odkazuje diagram ověření závislostí.|

## <a name="scenarios-in-which-lightweight-solution-loads-the-entire-solution"></a>Scénáře, ve kterých lightweight řešení načte celé řešení 

Pro některé funkce sady Visual Studio automaticky načte celého řešení, aby podporovala scénář. Tato akce zajistí vždy získáte plnou funkčnost. Některé operace TFS může například vyžadovat celé řešení načíst. Pokud chcete poskytnout úplné funkce, načte Visual Studio celé řešení.

|Kategorie|Scénář|
|-|-|-|
|Příkaz TFS SCC na uzel řešení|Pokud příkaz SCC se aktivuje na uzlu řešení (v Průzkumníku řešení), Visual Studio automaticky načte celé řešení před dokončením příkazu.|
|Načítání projektu|Pokud vaše řešení obsahuje projekty .NET Core a sdílených projektů, Visual Studio vždy automaticky načte tyto projekty během procesu načítání prvotního řešení sám sebe. Tyto projekty aktuálně nepodporují lightweight režimu.|
|Řešení nástroje configuration manager|Pokud použijete řešení configuration manager nebo sestavení batch, Visual Studio automaticky načte celé řešení k poskytování úplné prostředí.|
|Správce balíčků NuGet|Pokud otevřete uživatelské rozhraní Správce balíčků NuGet nebo konzoly Správce balíčků NuGet sady Visual Studio automaticky načte celé řešení k poskytování úplné prostředí.|

## <a name="known-issues"></a>Známé problémy

Je několik scénářů, které nemusí fungovat v režimu dolní limit a vyžadují načítání další projekty nebo celé řešení. Aktivně pracujeme na řešení těchto případech. 

|Kategorie|Problém|Alternativní řešení|
|-|-|-|-|
|IntelliSense|Po změně konfigurace (například změna sestavení pro vydání pro ladění a naopak) se neaktualizují IntelliSense. Dopad závisí na kódu rozdíly kvůli změně konfigurace.|Znovu načte řešení po změně konfigurace.|
|Refaktoring omezení pro projekty C# / VB.|Kód opravy, které změnit soubory projektu může selhat bezobslužně poprvé.|Načíst projekty, pokud potřebujete provést opravy kódu soubory těchto projektů. Prosté režimu neprovede opravy projekty, které nebyly načteny.|
|Test zjištění jednotky|Testy, které jsou zjištěny na odložené projekty se nespustí při načtení projektu ručně.|Znovu sestavte projekt, který má opakované zjišťování testů a znovu spusťte vybrané testy.|
|Testování (LUT) za provozu částí|V režimu dolní limit může se zobrazit že LUT není aktivovaná. Ji není aktivováno, protože LUT vyžaduje jednu z projektů testování načíst.|Načtěte všechny testovacího projektu aktivujte za provozu jednotku testování pro řešení.|
|Hledání Průzkumník řešení|1.    Hledání Průzkumníka řešení v režimu dolní limit není hledání v souborech, a nebyly nalezeny žádné výsledky postupu (tedy pouze soubory jsou uvedené v části stromu, ale není tříd, metod vyhledávání atd.).</br>2.    Všechny soubory, které patří do projektu se zobrazí jako plochý seznam místo zobrazení stromu. Soubory patří do složky projektu, ukážeme relativní cestu k souboru, nikoli jen název souboru v zobrazení vyhledávání.</br>V zobrazení vyhledávání neexistují žádné kontextové nabídky pro položky souboru.|Načtěte v režimu dolní limit získat tradiční Průzkumníku řešení vyhledávání celé řešení.</br>Můžete také použít Visual Studio IDE vyhledávání.|
|Prohlížeč objektů pro projekty C++|Prohlížeč objektů zobrazuje odkazy na sestavení/WinMD pro pouze načíst projekty.|Načíst projekty, pro které chcete zobrazit informace v prohlížeči objektů.|

> [!Note]
> Díky našich partnerů oblíbených rozšíření včetně Resharper také fungují dobře u zatížení lightweight řešení.

Snažíme se nadšení o inovace za účelem optimalizace výkonu času zatížení řešení pro vývojáře. Vzhledem k tomu, že toto je nová funkce, jsou jsme aktivně prohlížení názorů zákazníků a řešení známých problémů. Těšíme se na vaše názory. E-mailem Visual Studio řešení zatížení optimalizace týmu nalslsupport@microsoft.com

## <a name="see-also"></a>Viz také
[Rady a tipy pro zvýšení výkonu sady Visual Studio](../ide/visual-studio-performance-tips-and-tricks.md)  