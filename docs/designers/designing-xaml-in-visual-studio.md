---
title: "Navrhování XAML v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 07/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 288e2415-9fcf-408e-bc35-9848315e14fd
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 03ef7e9e7402ba03e132eb4c80c37a21d556c09c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="designing-xaml-in-visual-studio"></a>Navrhování XAML v sadě Visual Studio

Visual Studio a nástroj Blend for Visual Studio poskytují visual nástroje pro vytváření zapojení uživatelská rozhraní a bohatý mediální činnost s XAML pro různé typy aplikací. Oba nástroje sdílejí společnou sadu funkcí, včetně visual editoru XAML, ale Blend for Visual Studio poskytuje nástroje, další návrhu pro pokročilejší úlohy, jako je například animace a chování.  
  
Proces návrhu aplikace závisí na nástroj, který zvolíte a svou cílovou platformu. Toto téma přítomen porovnává nástrojů návrhu XAML v sadě Visual Studio a nástroj Blend for Visual Studio. Další podrobné návody pro použití nástroje najdete v následujících tématech:

- [Vytvoření uživatelského rozhraní pomocí návrháře XAML v sadě Visual Studio](creating-a-ui-by-using-xaml-designer-in-visual-studio.md)
- [Vytvoření uživatelského rozhraní pomocí nástroje Blend for Visual Studio](creating-a-ui-by-using-blend-for-visual-studio.md)
- [Vytvoření moderních aplikací klasické pracovní plochy s Windows Presentation Foundation](create-modern-desktop-applications-with-windows-presentation-foundation.md)

## <a name="choosing-the-right-tool"></a>Výběr správného nástroje  
 Vaši volbu nástrojů návrhu je do značné míry závisí na vaší sady znalostí. Pokud jste více orientovaný kódu, můžete napsat kód XAML v sadě Visual Studio k provádění úloh i pokročilé návrhu. Pokud jste více orientovaný návrhu, Blend for Visual Studio umožňuje provádět pokročilé úlohy bez nutnosti psaní kódu.  
  
 Můžete přepnout přepínat mezi sadou Visual Studio a Blend for Visual Studio a můžete mít i stejné projekt, otevřete v obou ve stejnou dobu. Změny provedené v soubory XAML v jedné IDE lze použít prostřednictvím automatické opětovné načtení po přepnutí do dalších prostředí IDE. Můžete řídit chování znovu načíst pomocí možnosti v **nástroje**, **možnosti** dialogovém okně buď IDE.  
  
### <a name="shared-capabilities"></a>Sdílené možnosti  
 Pro nejzákladnější úkoly rozhraní IDE pro sadu Visual Studio a nástroj Blend for Visual Studio sdílet stejnou sadu windows a funkce, s některé jemně lišit. Některé mezi nejdůležitější funkce patří:  
  
-   **Konzistentní uživatelské rozhraní:** můžete navrhnout vaše aplikace v rámci známé kontextu uživatelského rozhraní sady Visual Studio, takže je přepínání mezi integrovaného vývojového prostředí více příjemný a produktivní prostředí. Blendu pro Visual Studio používá Visual Studio tmavý motiv, který umožňuje zaměřit se na obsah, který navrhujete vylepšením kontrast mezi obsahem a uživatelské rozhraní. V tématu [vytvoření uživatelského rozhraní pomocí návrháře XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).  
  
     ![Blend for Visual Studio IDE](../designers/media/blendide.png "BlendIDE")  
  
-   **XAML IntelliSense:** jak integrovaného vývojového prostředí podporovat všechny běžné funkce, které očekáváte od včetně dokončování příkazů, podporu pro běžné operace editoru, jako při psaní komentářů a formátování kódu a navigace k prostředkům, IntelliSense vazba a kód.  
  
-   **Základní možnosti ladění:** teď můžete ladit v programu Blend, včetně nastavení zarážek v kódu k ladění běžící aplikaci. Pokud chcete zachovat konzistentního ladění prostředí pomocí sady Visual Studio, Blend for Visual Studio obsahuje většinu ladění windows a panelů nástrojů Visual Studio. Rozšířené možnosti ladění, například Diagnostika a analýza kódu jsou dostupné jenom v sadě Visual Studio. V tématu [ladění v sadě Visual Studio](../debugger/debugging-in-visual-studio.md).  
  
-   **Soubor znovu načíst zkušeností:** vaše soubory XAML v buď Blend for Visual Studio nebo Visual Studio můžete upravit, a mít upravených souborů znovu načtěte automaticky jak přepínat mezi nimi. Chcete-li minimalizovat přerušení pracovního postupu, můžete teď můžete nastavit váš soubor předvolby opětovného načtení v dialogovém okně znovu načíst soubor.  
  
     ![Soubor znovu načíst prostředí](../designers/media/blendfilereload.png "BlendFileReload")  
  
-   **Synchronizovat rozložení a nastavení:** vlastní rozložení umožňují uložit a použít nástroj přizpůsobení rozložení oken. Visual Studio se synchronizují tyto úpravy a předvolby pro Visual Studio a Blend for Visual Studio mezi počítači, když se přihlásíte pomocí stejného účtu Microsoft. V tématu [přizpůsobení sady Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
-   **Běžné Průzkumníku řešení:** Průzkumníku řešení vám poskytne uspořádaný náhled vašich projektů a jejich soubory, jakož i připravené pro přístup k příkazům s nimi spojených. Pomocí Průzkumníka řešení je snazší práce s projekty velká organizace. V tématu [řešení a projekty](../ide/solutions-and-projects-in-visual-studio.md).  
  
-   **Průzkumník týmových projektů:** s Průzkumník týmových projektů můžete spravovat projekty s úložiště GIT nebo TFS určitých kritérií. V tématu [fungovat v Team Exploreru](http://msdn.microsoft.com/Library/fd7a5cf7-7916-4fa0-b5e6-5a83cf377a02).  
  
-   **NuGet:** můžete spravovat balíčky NuGet v sadě Visual Studio a Blend for Visual Studio. NuGet je Správce balíčků pro rozhraní .NET Framework, který zjednodušuje instalaci a odebrání balíčků z řešení.  
  
## <a name="advanced-capabilities-in-blend-for-visual-studio"></a>Rozšířené možnosti v programu Blend for Visual Studio  
 Zvyšuje produktivitu, zvažte použití Blend for Visual Studio pro následující úlohy. Jedná se o oblastech, kde Blend for Visual Studio nabízí další rychlost a funkce než návrháři Visual Studio nebo kód samostatně.  
  
|Chcete-li|Visual Studio|Blend for Visual Studio|Další informace|  
|--------|-------------------|-----------------------------|----------------------|  
|**Vytvoření animace**|Neexistuje žádný nástroj návrhu pro animace; musíte je vytvořit prostřednictvím kódu programu. To vyžaduje pochopení animace a časování systému v WPF a rozsáhlé znalosti kódování.|Vytvořte animací vizuálně a jejich náhled zobrazit v programu Blend for Visual Studio. Toto je rychlejší a přesnější, než vytváření animace v kódu. Můžete přidat aktivačních událostí ke zpracování interakce s uživatelem, a můžete přepnout kódu k přidání obslužné rutiny událostí a další funkce.|[Animace objektů](../designers/animate-objects-in-xaml-designer.md)|  
|**Zapnout tvary a text do cesty pro snazší manipulace**|Není podporováno.|Tvary (například obdélníky a tři tečky) můžete provést jemně nebo výrazné změny jejich převedením na cesty, které poskytují lepší úpravy řízení.  Můžete změnit tvar nebo kombinovat cesty a vytvořit složené cesty z více tvarů.<br /><br /> Můžete také převést text bloky cesty, které se s nimi manipulovat jako obrázky vektoru.|[Kreslení tvarů a cest](../designers/draw-shapes-and-paths.md)|  
|**Přidání interaktivity k vaší návrhů uživatelského rozhraní**|Vyžaduje kódu C#, Visual Basic nebo C++.|Přetáhnout myší chování na ovládací prvky pro přidání interaktivity do vaší statické návrhů. Chování jsou fragmenty kódu připravené k použití, které zapouzdřují funkce, jako je přetažením přiblížení a změny visual stavu. Je stále početnější sadu chování, které můžete vybrat z, a můžete vytvořit vlastní.<br /><br /> Následně můžete přizpůsobit každý chování změnou jeho vlastnosti v programu Blend for Visual Studio nebo přidání obslužných rutin událostí v kódu.|[Vložení ovládacích prvků a změna jejich chování](../designers/insert-controls-and-modify-their-behavior-in-xaml-designer.md)|  
|**Použití Adobe kresby**|Není podporováno.|Importovat Adobe FXG, PhotoShop nebo Illustrator kresby a implementovat rozhraní v programu Blend for Visual Studio.|[Vložení obrázků, videí a zvukových klipů](../designers/insert-images-videos-and-audio-clips-in-xaml-designer.md)|  
|**Upravit ovládací prvky, šablony a styly**|Vyžaduje kódování a znalosti o WPF styly a šablony.|Zapněte všechny bitové kopie do ovládacího prvku.<br /><br /> Použijte šablonu nástroje pro úpravy provést změny ovládací prvky, styly a šablony pomocí několika kliknutí myší.<br /><br /> Například můžete použít nástroj Blend for Visual Studio styl prostředky k implementaci běžných ovládacích prvků WPF (například tlačítka, seznamy, posuvníky, nabídek, atd.) a změnit jejich barvu, styl nebo základní šablony přímo v programu Blend for Visual Studio. Můžete pak přepnout kód pro všechny změny podle potřeby.|[Úpravy stylu objektů](../designers/modify-the-style-of-objects-in-blend.md)|  
|**Uživatelské rozhraní se připojit k datům**|Můžete vytvořit zdroj dat z prostředků, jako je například databáze systému SQL Server, WCF nebo webové služby, objekty nebo seznamy služby SharePoint a svázat zdroj dat pro vaše ovládací prvky uživatelského rozhraní.<br /><br /> Pro prostředí interaktivní návrhu musí ručně vytvořit návrhu data.|Vytvoření ukázkových dat snadno pro při vytváření prototypu a testování. Přepínač tak, aby dynamická data, jakmile budete připraveni.<br /><br /> Blendu pro Visual Studio generování dat možnosti nejsou vyřízeny (můžete přidat názvy, čísla, adresy URL, fotografie snadno za chodu) a mohou ušetřit mnoho času.<br /><br /> Pro dynamická data můžete vázat vaše ovládací prvky uživatelského rozhraní do souboru XML nebo jakýkoli zdroj dat CLR.|[Zobrazení dat](../designers/display-data-in-blend.md)|  
  
 Další informace o pokročilé návrhu XAML najdete v tématu. [Vytvoření uživatelského rozhraní pomocí nástroje Blend for Visual Studio](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)