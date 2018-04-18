---
title: Procházení a změna uspořádání map kódu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.progression.dgmlgraph.layouthelp
- vs.progression.graphdocument
- vs.progression.dgmlgraph.message.notUlt.noexpandgroup
- vs.progression.colorsetpicker
- vs.progression.iconsetpicker
helpviewer_keywords:
- Visual Studio Ultimate, dependency graphs
- code visualization [Visual Studio ALM]
- graph documents, browsing
- Visual Studio ALM, dependency graphs
- code visualization
- Visual Studio ALM, graph documents
- Visual Studio Ultimate, graph documents
- dependency graphs, browsing
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: fb231c5a13bcc4a82eec140d3f2f482ae6c20941
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="browse-and-rearrange-code-maps"></a>Procházení a změna uspořádání map kódu
Změna uspořádání položek na map kódu k snadnější čtení a zvýšit výkon.  
  
 Mapy kódu můžete přizpůsobit, aniž by to ovlivnilo kódu v řešení. To je užitečné, když chcete zaměřit na elementy klíče kódu nebo komunikovat nápady o kód. Například zvýraznění zajímavé oblastí, můžete můžete vybrat elementy kódu na mapě a filtrovat je, změnit styl elementy kódu a odkazy, skrýt nebo odstranit elementy kódu a uspořádat elementy kódu pomocí vlastnosti, kategorie nebo skupiny.  
  
 **Požadavky**  
  
-   Pokud chcete vytvořit map kódu, musí mít Visual Studio Enterprise.  
  
-   Můžete zobrazit map kódu a provádět omezené úpravy map kódu ve Visual Studio Professional.  
  
##  <a name="ManageLargeGraphs"></a> Začínáme práce mapy kódu  
 Vytvoření mapy kódu (viz [mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md) podrobnosti). Pokud nechcete čekat na mapě dokončit generování, klikněte na **zrušit** odkaz kdykoli zastavit proces generování. Podrobnosti o všechny závislosti a odkazy, ale nezobrazí, pokud to uděláte.  
  
 Po vygenerování mapy začít pracovat s tyto tipy pro Kontrola kódu:  
  
-   Podívejte se na clustery přirozené závislostí v kódu. Na panelu nástrojů mapy zvolte **rozložení**, **rychlé clustery**![rychlé clustery tlačítka na panelu nástrojů grafu](../modeling/media/quickclustersicon.gif "QuickClustersIcon"). V tématu [Změna rozložení mapy](#Selecting).  
  
     ![Graf závislostí &#45; rychlé clustery rozložení](../modeling/media/dependencygraph_quickclusters.png "DependencyGraph_QuickClusters")  
  
-   Uspořádání mapy do menší oblasti seskupením související uzly. Sbalte těchto skupin, které chcete zobrazit jenom intergroup závislosti, které jsou automaticky. V tématu [skupiny uzly](#OrganizeGroups).  
  
-   Použití filtrů k zjednodušení mapy a zaměřit se na typy uzlů nebo odkazy, které vás zajímají. V tématu [filtrovat uzly a odkazy](#FilterNodes).  
  
-   Maximalizujte výkon velké map. V tématu [mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md) Další informace. Například zapnout **přeskočit sestavení** na panelu nástrojů mapy, sadou Visual Studio nebude znovu sestavit řešení při aktualizaci položky na mapě.  
  
##  <a name="Selecting"></a> Změna rozložení mapy  
  
|**K**|**Proveďte tyto kroky**|  
|------------|-----------------------------|  
|Zařídit celý mapy ve konkrétní směr toku závislostí. To vám může pomoci zjistit architektury vrstev v kódu.|Na panelu nástrojů mapy zvolte **rozložení**a pak:<br /><br /> -   **Shora dolů** ![nejvyšší pro tlačítko grafu dolní](../modeling/media/topbottomgraphbutton.gif "TopBottomGraphButton")<br />-   **Zdola nahoru** ![dolní pro tlačítko nejvyšší grafu](../modeling/media/bottomtopgraphbutton.gif "BottomTopGraphButton")<br />-   **Zleva doprava** ![zbývající ke správné rozložení tlačítko](../modeling/media/leftrightgraphbutton.gif "LeftRightGraphButton")<br />-   **Zprava doleva** ![práva ke grafu levé tlačítko](../modeling/media/rightleftgraphbutton.gif "RightLeftGraphButton")|  
|V tématu přirozené závislostí clustery v kódu s nejvíce závislé uzly v centru clusterů a nejméně závislé uzly v mimo těchto clusterů.|Na panelu nástrojů mapy zvolte **rozložení**a potom **rychlé clustery**![rychlé clustery tlačítka na panelu nástrojů grafu](../modeling/media/quickclustersicon.gif "QuickClustersIcon").|  
|Vyberte jeden nebo více uzlů na mapě.|Klikněte na uzel vyberte. Vyberte nebo zrušte výběr více než jeden uzel, podržte **CTRL** při kliknutí na.<br /><br /> Klávesové: stisknutím **KARTĚ** nebo použijte klávesy se šipkami přesunout desítkovém obdélník do uzlu a stiskněte klávesu **místo** ji vyberte. Stiskněte klávesu **CTRL** + **místo** do více vyberte nebo zrušte výběr uzlů.|  
|Pohyb konkrétním uzlům na mapě.|Přetáhněte uzly jejich přesunutí. Přesunout další uzly a odkazy z cesty, protože přetahování uzlů, stiskněte a podržte **SHIFT** klíč.<br /><br /> Klávesové: uložení **CTRL** a stisknutím klávesy se šipkami.|  
|Změna rozložení uvnitř skupiny nezávisle na ostatních uzlech a skupin na mapě.|Vyberte uzel a otevřete místní nabídky. Zvolte **rozložení** a vyberte stylu rozložení.<br /><br /> - nebo -<br /><br /> Vyberte uzel a rozšířit tak, aby zobrazení podřízených uzlů. Klikněte na název uzlu zobrazit panel nástrojů místní skupiny a otevřete **Změna stylu rozložení skupiny**![graf závislostí &#45; skupiny nástrojů &#45; rozložení](../modeling/media/dependencygraph_grouptoolbar.gif "DependencyGraph_ GroupToolbar") seznamu. Vyberte jednu z rozložení stromu **rychlé clustery**, nebo **zobrazení seznamu** (který uspořádá skupiny obsah do seznamu).<br /><br /> V tématu [skupiny uzly](#OrganizeGroups) další podrobnosti.|  
|Vrátit zpět akci v mapě.|Stiskněte klávesu **CTRL** + **Z** nebo pomocí sady Visual Studio **vrátit zpět** příkaz.|  
  
##  <a name="Explore"></a> Procházet mapy  
  
|**K**|**Proveďte tyto kroky**|  
|------------|-----------------------------|  
|Kontrola mapy.|Přetáhněte mapy libovolným směrem. pomocí myši.<br /><br /> - nebo -<br /><br /> Uložení **SHIFT** a otočení kolečka myši k vodorovnému posouvání. Uložení **SHIFT** + **CTRL** a otočení kolečka myši k vodorovnému posouvání.|  
|Zvětšení nebo zmenšení mapy.|Otočte kolečko myši.<br /><br /> - nebo -<br /><br /> Použití **zvětšení** rozevíracího seznamu na panelu nástrojů map kódu.<br /><br /> - nebo -<br /><br /> Používání klávesových zkratek. Chcete-li zvětšit, stiskněte klávesu **kombinaci kláves CTRL + SHIFT +.** (tečky). Chcete-li oddálení, stiskněte **kombinaci kláves CTRL + SHIFT +,** (čárkou).|  
|Přiblížení určitou oblast pomocí myši.|Pravým tlačítkem myši podržte při kreslení obdélníků kolem této oblasti, které vás zajímají.|  
|Změní velikost a přizpůsobit mapy ve její okno.|Zvolte **zvětšení přizpůsobit** z **zvětšení** seznamu na panelu nástrojů map kódu.<br /><br /> - nebo -<br /><br /> Klikněte na tlačítko **přiblížení podle** ikonu ![přiblížení ikonu na panelu nástrojů mapy](../modeling/media/almcodemapzoomicon.png "ALMCodeMapZoomIcon") na panelu nástrojů map kódu. Klávesové: stisknutím **CTRL + 0** (nula).|  
|Najít uzel na mapě jeho název. **Tip:** to funguje pouze pro položky na mapě. K nalezení položek ve vašem řešení ale není na mapě, kde je najít v **Průzkumníku**a pak je přetáhněte do mapy. (Přetáhněte váš výběr, nebo na panelu nástrojů Průzkumníku řešení klikněte na tlačítko **zobrazit na mapě kódu**).|1.  Zvolte **najít** ikonu ![najít ikonu na panelu nástrojů mapy](../modeling/media/almcodemapfindicon.png "ALMCodeMapFindIcon") na panelu nástrojů Mapa kódu (klávesnice: stiskněte klávesu **kombinaci kláves CTRL + F**) k zobrazení do vyhledávacího pole v pravém horním rohu mapy.<br />2.  Zadejte název položky a stiskněte klávesu **vrátit** nebo klikněte na ikonu "Lupa". První položka, která odpovídá vašemu vyhledávání zobrazí jako vybraný na mapě.<br />3.  Chcete-li přizpůsobit hledání, otevřete rozevírací seznam a vyberte možnost hledání. Možnosti jsou **najít další**, **najít předchozí**, a **Vybrat vše**. Klikněte na odpovídající tlačítko vedle textového pole hledání.<br />     ![Vyřaďte možnosti vyhledávání&#45;dolů seznamu](../modeling/media/almcodemapssearchdropdown.png "ALMCodeMapsSearchDropDown")<br />     Můžete taky použít klávesnici: stiskněte **F3** a vyberte další odpovídající uzel nebo **SHIFT + F3** vybrat v předchozím odpovídající uzlu.<br />4.  Vyberte některou z možností, které určují způsob zpracování hledaných termínů kliknutím na ikony níže textového pole hledání.<br />     ![Shoda možnosti vyhledávání](../modeling/media/almcodemapssearchmatchicons.png "ALMCodeMapsSearchMatchIcons")<br />     Možnosti jsou zleva doprava, případ citlivé odpovídající, Hledat jenom celá slova, použijte syntaxi regulárního výrazu rozhraní .NET, automaticky skupiny rozbalit a zobrazit odpovídá závorkách položkám. **Důležité:** do vyhledávacího pole můžete použít k vyhledání shody v sbalené skupiny pouze v případě, že byly dříve rozbalený těchto skupin. Můžete najít tyto shody a rozšířit své nadřazené skupiny automaticky, vyberte tuto možnost v části do vyhledávacího pole.|  
|Vyberte všechny uzly nezaškrtnuté.|Otevřete místní nabídku zvolených uzlů. Zvolte **vyberte**, **Invertovat výběr**.|  
|Vyberte další uzly, které odkazují vybraných.|Otevřete místní nabídku zvolených uzlů. Zvolte **vyberte** a jednu z těchto:<br /><br /> -Další uzly, které přímý odkaz na vybraný uzel, vyberte **příchozí závislosti**.<br />-Další uzly, které jsou propojené přímo z vybraného uzlu, vyberte **odchozí závislosti**.<br />-Další uzly, které jsou propojené přímo do a z vybraného uzlu, vyberte **i**.<br />– Chcete-li vybrat všechny uzly, které odkazují na a z vybraného uzlu, zvolte **připojené Subgraph**.<br />– Chcete-li vybrat všechny podřízené objekty vybraného uzlu, zvolte **podřízené objekty**.|  
  
##  <a name="FilterNodes"></a> Uzly filtrů a odkazy  
  
|**K**|**Proveďte tyto kroky**|  
|------------|-----------------------------|  
|Umožňuje zobrazit nebo skrýt podokno filtry.|Vyberte **filtry** tlačítka na panelu nástrojů map kódu. V podokně filtry se zobrazí jako záložkách stránka v okně Průzkumníku řešení ve výchozím nastavení.|  
|Filtrujte typy uzlů, které jsou zobrazeny na mapě.|Nastavit nebo zrušte zaškrtnutí políček v **elementy kódu** seznamu v podokně filtry.|  
|Filtrujte typy odkazů, které se zobrazí na mapě.|Nastavit nebo zrušte zaškrtnutí políček v **vztahy** seznamu v podokně filtry.|  
|Zobrazit nebo skrýt testovacího projektu uzly na mapě.|Nastavení nebo vymazání **testovací prostředky** zaškrtnout políčko **různé** seznamu v podokně filtry.|  
  
 Ikony v panelu legendy mapy projeví nastavení, které provedete v seznamu. Zobrazit nebo skrýt panel legendy, klikněte **legendy** tlačítka na panelu nástrojů map kódu.  
  
##  <a name="Inspect"></a> Zkontrolujte uzly a odkazy  
 Mapy kódu ukazují tyto druhy odkazy:  
  
-   Jednotlivé odkaz představuje jednu relaci mezi dvěma uzly.  
  
-   Propojení mezi skupiny představuje vztah mezi dva uzly v různých skupinách.  
  
-   Souhrnného propojení představuje všechny vztahy, které bodu ve stejném směru mezi dvěma skupinami.  
  
> [!TIP]
>  Ve výchozím nastavení zobrazuje mapy skupinu křížové odkazy pouze pro vybrané uzly. Chcete-li změnit toto chování k zobrazení nebo skrytí agregované odkazů mezi skupinami, klikněte na tlačítko **rozložení** kódu mapování panelu nástrojů a zvolte **Upřesnit**, pak **zobrazit všechna propojení mezi skupiny** nebo **Skrýt všechny skupiny křížové odkazy**. V tématu [skrytí nebo zobrazení uzlů a odkazy](#HidingShowing) další podrobnosti.  
  
|**K**|**Proveďte tyto kroky**|  
|------------|-----------------------------|  
|Zobrazit další informace o uzel nebo odkaz.|Přesuňte ukazatel myši nad uzlu nebo odkaz, dokud se nezobrazí tip.<br /><br /> Popisek pro agregovaná odkaz uvádí jednotlivé závislosti, které představuje.<br /><br /> - nebo -<br /><br /> Otevřete místní nabídku pro uzel nebo odkaz. Zvolte **upravit**, **vlastnosti**.|  
|Zobrazit nebo skrýt obsah skupiny.|– Chcete-li rozbalit skupinu, otevřete místní nabídku pro uzel a zvolte **skupiny**, **rozbalte**.<br />     - nebo -<br />     Dokud se nezobrazí tlačítko s dvojitou šipkou (šipka) dolů, přesuňte ukazatel myši nad uzlu. Kliknutím na toto tlačítko rozbalte skupinu. Klávesové: Chcete-li rozbalit nebo sbalit vybrané skupině, stiskněte **PLUS** klíč (**+**) nebo **MINUS** klíč (**-**).<br />– Chcete-li sbalit skupinu, otevřete místní nabídku pro uzel a zvolte **skupiny**, **sbalit**.<br />     - nebo -<br />     Přesuňte ukazatel myši nad skupinu, dokud se nezobrazí tlačítko s dvojitou šipkou (šipka) nahoru. Kliknutím na toto tlačítko Sbalit skupiny.<br />– Chcete-li rozbalit všechny skupiny, stiskněte klávesu **CTRL** + **A** vyberte všechny uzly. Otevřete místní nabídku pro mapu a zvolte **skupiny**, **rozbalte**. **Poznámka:** tento příkaz není k dispozici, pokud rozšíření všechny skupiny generuje nepoužitelná mapy nebo problémy s pamětí. Doporučuje se jenom na úroveň podrobností, která se zajímáte o rozbalte položku mapy.<br />– Chcete-li sbalit všechny skupiny, otevřete místní nabídku pro uzel nebo pro mapu. Zvolte **skupiny**, **Sbalit vše**.|  
|Viz definice kód pro obor názvů, typ nebo člen.|Otevřete místní nabídku pro uzel a zvolte **přejít k definici**.<br /><br /> -nebo-<br /><br /> Dvakrát klikněte na uzel. Rozšířené skupiny dvakrát klikněte na záhlaví ve skupině.<br /><br /> -nebo-<br /><br /> Vyberte uzel a stiskněte klávesu **F12**.<br /><br /> Příklad:<br /><br /> -Pro obor názvů obsahující jednu třídu otevření souboru kódu pro třídu zobrazíte definici této třídy. V ostatních případech **Najít výsledky Symbol** v okně se zobrazí seznam souborů, kód. **Poznámka:** při provedení této úlohy v oboru názvů jazyka Visual Basic, nelze otevřít soubor kód za obor názvů. Tento problém nastane i při provádění této úlohy ve skupině vybraných uzlech, které zahrnují oboru názvů jazyka Visual Basic. Chcete-li tento problém obejít, přejděte do souboru kódu za obor názvů ručně nebo vynechejte uzlu pro obor názvů z vašeho výběru.<br />-Pro třídu nebo konkrétní třídu otevření souboru kódu pro tuto třídu zobrazíte definici třídy.<br />-Pro metodu zobrazíte definici metody otevření souboru kódu pro nadřazené třídy.|  
|Zkontrolujte závislosti a položky, které jsou součástí souhrnného propojení.|Vyberte odkazy zajímají a otevřete místní nabídku pro váš výběr. Zvolte **zobrazit přidání odkazů** nebo **zobrazit přidání odkazů na nové Mapa kódu**.<br /><br /> Visual Studio rozbalí skupiny na obou koncích spojení a zobrazí pouze položky a závislosti, které se účastní odkazu. **Poznámka:** když byste zkontrolovat závislosti mezi položky ve skupinách, částečné, může se zobrazit toto chování: <ul><li>Odkazy na položky, které nejsou součástí vaší prozkoumání zmizí z mapy, i když stále existují tyto odkazy.</li><li>Předpokládejme zkontrolujte odkaz na částečné skupinu a poté zkontrolujte jiný odkaz na stejnou položku. Během druhé prozkoumání cílová skupina částečné zobrazuje pouze položky z prvního zkoumání. Odkazy a cíl položek, které nebylo účastnit vaše první kontrola ale účastnit vaše druhý kontrola nezobrazí.</li></ul> Zobrazit chybí položek ze skupiny, vyberte **znovu načíst podřízené objekty**![znovu načíst ikonu podřízené objekty](../modeling/media/dependencygraph_deletednodesicon.png "DependencyGraph_DeletedNodesIcon") (což znamená, že ne všechny členy skupina zobrazí na mapě). Můžete také zkusit vaše akce vrátí zpět (klávesové: stiskněte **CTRL + Z**) a zkontrolujte závislosti na nové mapování.|  
|Zkontrolujte závislosti mezi několika uzly v různých skupinách.|Rozbalte skupiny, aby se zobrazily všechny jeho podřízené objekty. Vyberte všechny uzly, které vás, včetně jejich podřízené zajímají. Mapa zobrazuje cross-group propojení mezi vybrané uzly.<br /><br /> Chcete-li vybrat všechny uzly ve skupině, stiskněte a podržte **SHIFT** a levé tlačítko při kreslení obdélníku kolem této skupiny. Chcete-li vybrat všechny uzly na mapě, stiskněte **CTRL**+**A**. **Tip:** zobrazit skupinu křížové odkazy na všechny časy, zvolte **rozložení** na panelu nástrojů mapy **Upřesnit**, **zobrazit všechna propojení mezi skupiny**.|  
|Zobrazit položky, které odkazuje na uzel nebo odkaz.|Otevřete místní nabídku pro uzel a zvolte **najít všechny odkazy**. **Poznámka:** platí pouze tehdy, když `Reference` atribut je nastaven pro uzel nebo odkaz v souboru .dgml mapy. Chcete-li přidat odkazy na položky z uzlů nebo odkazy, přečtěte si téma [mapuje přizpůsobit kódu úpravou souborů DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md).|  
  
##  <a name="HidingShowing"></a> Skrytí nebo zobrazení uzlů a odkazy  
 Skrytí uzlů umožňuje vynechat tyto uzly při použití algoritmů rozložení. Ve výchozím nastavení jsou propojení mezi skupinami skryta. Propojení mezi skupinami jsou jednotlivá propojení, která spojují uzly mezi skupinami. Pokud jsou sbaleny skupin, mapy agreguje všechny skupiny křížové odkazy do jednoho propojení mezi skupinami. Pokud skupinu rozbalíte a vyberete v ní uzly, zobrazí se propojení mezi skupinami, která znázorňují závislosti v této skupině.  
  
> [!CAUTION]
>  Před sdílením mapu, která byla vytvořena v Visual Studio Enterprise s těmi, kteří používají Visual Studio Professional, ujistěte se, že jste Odkrýt všechny uzly nebo skupinu křížové odkazy, které chcete vidět. V opačném případě uživatelé nebudou moci tyto položky zobrazit.  
  
### <a name="to-hide-or-show-nodes"></a>Skrytí nebo zobrazení uzlů  
  
|**K**|**Proveďte tyto kroky**|  
|------------|-----------------------------|  
|Skryjte vybrané uzly.|1.  Vyberte uzly, které chcete skrýt.<br />2.  Otevřete místní nabídku pro vybrané uzly nebo mapy. Zvolte **vyberte**, **skrýt vybrané**.|  
|Skryjte nezaškrtnuté uzly.|1.  Vyberte uzly, které chcete zůstanou viditelné.<br />2.  Otevřete místní nabídku pro vybrané uzly nebo mapy. Zvolte **vyberte**, **skrýt zrušit**.|  
|Zobrazit skryté uzly.|– Chcete-li zobrazit všechny skryté uzlů v rámci skupiny, nejdřív zkontrolujte, zda že je rozšířena skupině. Otevřete místní nabídku a vyberte **vyberte**, **odkrýt podřízené objekty**.<br />     - nebo -<br />     Klikněte na tlačítko **zobrazení podřízených prvků**![odkrýt ikonu podřízené objekty](../modeling/media/dependencygraph_filtericon_hiddennodes.gif "DependencyGraph_FilterIcon_HiddenNodes") ikonu v levém horním rohu (to je viditelná jenom v případě skupiny Existují skrytá podřízené uzly).<br />– Chcete-li zobrazit všechny skryté uzly, otevřete místní nabídku pro mapy nebo uzel a zvolte **vyberte**, **Odkrýt všechny**.|  
  
### <a name="to-hide-or-show-links"></a>Skrytí nebo zobrazení odkazy  
  
|**K**|**Na panelu nástrojů mapy vybrat rozložení, rozšířené a potom vyberte**|  
|------------|----------------------------------------------------------------------|  
|Zobrazit skupinu křížové odkazy na všechny časy.|**Zobrazit všechny skupiny křížové odkazy**. Tím budou skryta souhrnná propojení mezi skupinami.|  
|Skryjte propojení mezi skupiny za všech okolností.|**Skrýt všechny skupiny křížové odkazy**|  
|Zobrazit pouze skupiny křížové odkazy na vybrané uzly.|**Zobrazit skupinu křížové odkazy na vybrané uzly**|  
|Skryjte všechny odkazy.|**Skrýt všechny odkazy**. Chcete-li znovu zobrazit odkazy, zvolte jednu z výše uvedených možností.|  
  
##  <a name="OrganizeGroups"></a> Skupina uzlů  
  
|**K**|**Proveďte tyto kroky**|  
|------------|-----------------------------|  
|Zobrazit uzly kontejneru jako skupina uzlů nebo uzlů listu.|Chcete-li zobrazit uzly kontejneru jako uzlů listu: vyberte uzly, otevřete místní nabídku pro váš výběr a zvolte **skupiny**, **převést do listu**.<br /><br /> Zobrazit uzly kontejneru jako uzly skupiny: vyberte uzly, otevřete místní nabídku pro váš výběr a zvolte **skupiny**, **převést do skupiny**.|  
|Změna rozložení uvnitř skupiny.|Vyberte skupinu, otevřete místní nabídky, zvolte **rozložení**a vyberte stylu rozložení chcete.<br /><br /> - nebo -<br /><br /> 1.  Vyberte skupinu a ujistěte se, že je rozšířena.<br />2.  Znovu klikněte na záhlaví skupiny a zobrazí panel nástrojů skupiny.<br />     ![Graf závislostí &#45; skupiny nástrojů](../modeling/media/dependencygraph_group.png "DependencyGraph_Group")<br />3.  Otevřete **Změna stylu rozložení skupiny** seznamu ![graf závislostí &#45; skupiny nástrojů &#45; rozložení](../modeling/media/dependencygraph_grouptoolbar.gif "DependencyGraph_GroupToolbar") a zvolte rozložení požadovaný styl.<br /><br /> **Zobrazení seznamu** Přeuspořádá členy skupiny do seznamu. **Graf výchozí** rozložení skupiny obnoví na výchozí rozložení mapy. Další možnosti najdete v tématu [Změna rozložení mapy](#Selecting).|  
|Přidáte uzel do skupiny.|Přetáhněte uzel do skupiny.<br /><br /> Při tažení uzlu, Visual Studio zobrazí zobrazení, že přesouváte uzlu indikátoru.<br /><br /> Uzly lze přetáhnout také mimo skupinu.|  
|Přidáte uzel do jiné skupiny uzlu.|Přetáhněte uzel na cílový uzel. Všechny cílový uzel můžete převést do skupiny tak, že přidáte uzly k němu.|  
|Seskupte vybrané uzly.|1.  Vyberte uzly, které chcete seskupit. Se zobrazí automaticky otevírané okno panelu nástrojů nad poslední uzel, kterou vyberete.<br />     ![Panel nástrojů grafu závislostí](../modeling/media/depedencygraph_toolbar.png "DepedencyGraph_Toolbar")<br />2.  Na panelu nástrojů vyberte ikonu čtvrtý **skupiny na vybraných uzlech** (Pokud je uzel rozbalit bude mít pět místo čtyři ikon). Zadejte název nové skupiny a stiskněte klávesu **vrátit**.<br />     - nebo -<br />     Vyberte uzly, které chcete seskupit a otevřete místní nabídku pro váš výběr. Zvolte **skupiny**, **Přidat nadřazené skupiny**, zadejte název nové skupiny a stiskněte klávesu **vrátit**.<br /><br /> Můžete přejmenovat skupinu. Otevřete místní nabídku pro skupinu a vyberte **upravit**, **vlastnosti** a otevřete okno Vlastnosti Visual Studio. V **popisek** vlastnost, přejmenujte skupinu podle potřeby.|  
|Odeberte skupiny.|Vyberte skupinu nebo skupiny, které mají být odstraněny. Otevřete místní nabídku pro váš výběr a zvolte **skupiny**, **odstranit skupinu**.|  
|Odeberte uzly ze své nadřazené skupiny.|Vyberte uzly, které mají být odebrány. Otevřete místní nabídku pro váš výběr a zvolte **skupiny**, **odebrat z nadřazené**. Odebere se uzly až do jejich nadřazený nebo na mimo skupinu případě, že mají žádná skupina nadřazený.<br /><br /> - nebo -<br /><br /> Vyberte uzly a přetáhněte je mimo skupinu.|  
  
##  <a name="AddRemoveNodesLinks"></a> Přidat, odebrat nebo přejmenovat uzly, odkazy a komentáře  
 Více nebo méně položek můžete zobrazit na mapě, aby bylo možné přejít na nižší úroveň, nebo pro zjednodušení mapy. Můžete také přejmenovat položky a přidání komentářů k položkám.  
  
> [!CAUTION]
>  Před sdílením mapu, která byla vytvořena pomocí Visual Studio Enterprise s těmi, kteří používají Visual Professional, zajistěte, aby všechny elementy kódu, které chcete vidět jsou viditelné na mapě. Tito uživatelé, jinak nebudou načíst elementy odstraněné kódu.  
  
### <a name="add-a-node-for-a-code-element"></a>Přidat uzel pro element kódu  
  
|**K**|**Proveďte tyto kroky**|  
|------------|-----------------------------|  
|Přidáte nový uzel obecné na aktuální umístění ukazatele myši.|1.  Přesuňte ukazatel myši na místo na mapě kam chcete umístit nového elementu kód a stiskněte klávesu **vložit**.<br />     - nebo -<br />     Otevřete místní nabídku pro mapu a zvolte **upravit**, **přidat**, **obecné uzlu**.<br />2.  Zadejte název nového uzlu a stiskněte klávesu **vrátit**.|  
|Přidejte konkrétní typ uzlu element kód na aktuální umístění ukazatele myši.|1.  Přesuňte ukazatel myši na místo na mapě kam chcete vložit nový element kódu a otevřete místní nabídku pro mapu.<br />2.  Zvolte **upravit**, **přidat**a vyberte typ uzlu chcete.<br />3.  Zadejte název nového uzlu a stiskněte klávesu **vrátit**.|  
|Přidejte do skupiny generických nebo určitý typ uzlu element kódu.|1.  Vyberte uzel, skupiny a otevřete místní nabídky.<br />2.  Zvolte **upravit**, **přidat**a vyberte typ uzlu chcete.<br />3.  Zadejte název nového uzlu a stiskněte klávesu **vrátit**.|  
|Přidat nový uzel stejného typu a odkazované z existujícího uzlu.|1.  Vyberte tento element kódu. Nad ním se zobrazí automaticky otevírané okno panelu nástrojů.<br />     ![Panel nástrojů grafu závislostí](../modeling/media/depedencygraph_toolbar.png "DepedencyGraph_Toolbar")<br />2.  Na panelu nástrojů vyberte ikonu druhý **vytvořit uzel stejnou kategorii jako tento uzel a přidat nový odkaz k němu**.<br />3.  Vyberte místo na mapě put nového elementu kódu a klikněte na něj.<br />4.  Zadejte název nového uzlu a stiskněte klávesu **vrátit**.|  
|Přidáte nový uzel obecné propojeném z existujícího kódu element, který má právě fokus.|1.  Pomocí klávesnice, stiskněte klávesu **kartě** dokud elementu kód, který chcete propojit z má právě fokus (desítkovém obdélníku).<br />2.  Stiskněte klávesu **Alt**+**vložit**.<br />3.  Zadejte název nového uzlu a stiskněte klávesu **vrátit**.|  
|Přidáte nový uzel Obecné, který odkazuje na element stávající kód, který má právě fokus.|1.  Pomocí klávesnice, stiskněte klávesu **kartě** dokud elementu kód, který chcete propojit má právě fokus (desítkovém obdélníku).<br />2.  Stiskněte klávesu **Alt**+**Shift**+**vložit**.<br />3.  Zadejte název nového uzlu a stiskněte klávesu **vrátit**.|  
  
|**Chcete-li přidat elementy kódu pro**|**Proveďte tyto kroky**|  
|----------------------------------|-----------------------------|  
|Elementy kódu v řešení.|1.  Najít element kódu v **Průzkumníku řešení**. Použití **Průzkumníku řešení** vyhledávacího pole nebo vyhledejte řešení. **Tip:** najít elementy kódu, které mají závislosti na typu nebo členem, otevřete místní nabídku pro typ nebo člen v **Průzkumníku řešení**. Vyberte vztah, který vás zajímá. **Průzkumník řešení** zobrazuje pouze elementy kódu se zadanou závislostmi.<br />2.  Přetáhněte elementy kódu, které vás zajímají na povrch mapy. Můžete také přetažením elementy kódu ze zobrazení tříd nebo prohlížeč objektů.<br />     - nebo -<br />     V **Průzkumníku**, vyberte elementy kódu, které chcete namapovat. Potom na **Průzkumníku řešení** nástrojů, klikněte na tlačítko **zobrazit na mapě kódu**.<br /><br /> Ve výchozím nastavení je nadřazená hierarchie kontejneru pro nové prvky kódu zobrazit na mapě. Použití **zahrnují nadřazené položky** tlačítka na panelu nástrojů Mapa kódu toto chování změnit. Při vypnuté, pouze kód elementu samotného se přidá do mapy. Aby toto chování pro jedním přetažení a vyřadit akce, když stisknete a podržíte **CTRL** klíče a přetáhněte elementy kódu na mapě.<br /><br /> Visual Studio přidá elementy kódu pro elementy nejvyšší úrovně kódu ve výběru. Pokud chcete zobrazit, pokud element kódu obsahuje další elementy kódu, přesuňte ukazatel myši nad tento element kódu tak, aby se zobrazí na dvojitou šipku (šipka) dolů. Vyberte na dvojitou šipku rozbalte element kódu. Chcete-li rozšířit všechny elementy kódu, stiskněte **CTRL**+**A** vybrat všechny elementy, otevřete místní nabídku pro mapu a vyberte **skupiny**, **rozbalte** . Tento příkaz není k dispozici, pokud rozšíření všechny skupiny by vytvořit nepoužitelná mapy nebo způsobit nedostatek paměti.|  
|Elementy kódu související s elementy kódu na mapě.|Klikněte **zobrazit související** tlačítka na panelu nástrojů Mapa kódu a vyberte typ související položky, které vás zajímají.<br /><br /> - nebo -<br /><br /> Otevřete místní nabídku pro tento element kódu. Vyberte jednu z **zobrazit...**  položky nabídky v závislosti na typ relace, které vás zajímají. Například může zobrazit položky, které odkazuje na aktuální položky, položky, které odkazují na aktuální položky, základní a odvozené typy pro třídy, metoda volající a obsahující třídy, obory názvů a sestavení.<br /><br /> Další podrobnosti najdete v tématu [v tomto tématu](../modeling/map-dependencies-across-your-solutions.md).|  
|Kompilované sestavení .NET (.dll nebo .exe) nebo binárních souborů.|Přetáhněte sestavení nebo binární soubory mimo aplikaci Visual Studio na mapu.<br /><br /> Můžete přetáhnout z Průzkumníka Windows nebo Průzkumníka souborů pouze v případě, že používáte ho a Visual Studio na stejné úrovni oprávnění přístupu k řízení Uživatelských účtů. Například pokud je zapnutý nástroj Řízení uživatelských účtů a používáte Visual Studio jako správce, Průzkumníka Windows nebo soubor Explorer zablokuje přetahování operaci.|  
  
###  <a name="AddNodes"></a>   
##### <a name="add-a-link-between-existing-code-elements"></a>Přidat odkaz mezi stávající elementy kódu  
  
1.  Vyberte požadovaný prvek zdrojového kódu. Panel nástrojů se zobrazí nad tento element kódu.  
  
     ![Panel nástrojů grafu závislostí](../modeling/media/depedencygraph_toolbar.png "DepedencyGraph_Toolbar")  
  
2.  Na panelu nástrojů vyberte ikonu první **vytvořit nové propojení z tohoto uzlu, které ever uzlu, který kliknete na další**.  
  
3.  Vyberte cílový element code. Mezi elementy dvě kódu se zobrazí odkaz.  
  
 \- nebo –  
  
1.  Vyberte elementu zdrojového kódu na mapě.  
  
2.  Pokud máte nainstalovaný myši, přesuňte ukazatel myši mimo hranice mapy.  
  
3.  Otevřete tento element kódu místní nabídky a zvolte **upravit**, **přidat**, **obecný odkaz**.  
  
4.  Na kartě a vyberte cílový element code odkazu.  
  
5.  Stiskněte klávesu **vrátit**.  
  
###  <a name="AddComments"></a>   
##### <a name="add-a-comment-to-an-existing-node-on-the-map"></a>Přidejte komentář k stávající uzel na mapě  
  
1.  Vyberte tento element kódu. Zobrazí se nad ním.  
  
     ![Panel nástrojů grafu závislostí](../modeling/media/depedencygraph_toolbar.png "DepedencyGraph_Toolbar")  
  
2.  Na panelu nástrojů vyberte ikonu třetí **vytvořit nový uzel komentář se zobrazí nový odkaz na vybraný uzel**.  
  
     \- nebo –  
  
     Otevřete místní nabídku pro tento element kódu a vyberte **upravit**, **nový komentář**.  
  
3.  Zadejte komentáře. Chcete-li typ na nový řádek, stiskněte **SHIFT** + **vrátit**.  
  
##### <a name="add-a-comment-to-the-map-itself"></a>Přidejte komentář k samotné mapy  
  
1.  Otevřete místní nabídku pro mapu a zvolte **upravit**, **nový komentář**.  
  
2.  Zadejte komentáře. Chcete-li typ na nový řádek, stiskněte **SHIFT** + **vrátit**.  
  
###  <a name="RenameNodes"></a>   
##### <a name="rename-a-code-element-or-link"></a>Přejmenování elementu kódu nebo odkaz  
  
1.  Vyberte tento element kódu nebo odkaz, který chcete přejmenovat.  
  
2.  Stiskněte klávesu **F2**, nebo otevřete místní nabídku a vyberte **upravit**, **přejmenovat**.  
  
3.  Jakmile se zobrazí pole pro úpravy v mapě, přejmenování elementu kódu nebo odkaz.  
  
     \- nebo –  
  
4.  Otevřete místní nabídku a vyberte **upravit**, **vlastnosti**.  
  
5.  Upravit **popisek** vlastnost v okně vlastností Visual Studio.  
  
##### <a name="remove-a-code-element-or-link-from-the-map"></a>Odebrat element kódu nebo odkaz z mapy  
  
1.  Vybrat element kódu nebo odkaz a stiskněte klávesu **odstranit** klíč.  
  
     \- nebo –  
  
     Otevřete místní nabídku pro odkaz na element kódu a vyberte **upravit**, **odebrat**.  
  
2.  Součástí skupiny, pokud je element nebo odkaz **znovu načíst podřízené objekty** tlačítko ![znovu načíst ikonu podřízené objekty](../modeling/media/dependencygraph_deletednodesicon.png "DependencyGraph_DeletedNodesIcon") se zobrazí uvnitř skupiny. Klepněte sem a načíst chybějící elementy a odkazy.  
  
-   Elementy kódu a odkazy můžete odebrat z mapy bez ovlivnění kódu. Pokud je odstraníte, jejich definice se odeberou ze souboru DGML (.dgml).  
  
-   Mapování vytvořená úpravou DGML, přidáním elementy nedefinované kódu nebo pomocí některé starší verze sady Visual Studio, tato funkce nepodporují.  
  
##### <a name="flag-a-code-element-for-follow-up"></a>Příznak element kódu pro následnou akci  
  
1.  Vyberte element kódu nebo odkazu, který chcete příznak pro následné akce.  
  
2.  Otevřete místní nabídku a vyberte **upravit**, **nastavit příznak pro zpracování**.  
  
-   Ve výchozím nastavení získá tento element kódu červené pozadí. Vezměte v úvahu [přidání komentář](#AddComments) k němu odpovídající následné informace.  
  
-   Změnit barvu pozadí elementu nebo zrušte příznak následné výběrem **upravit**, **ostatní barvy příznak**.  
  
##  <a name="ChangeStyleCodeOrLink"></a> Umožňuje změnit styl element kódu nebo odkaz  
 Ikony na elementy kódu a barvy elementy kódu a odkazy pomocí předdefinovaných ikony a barvy, můžete změnit. Můžete například zvolit barvu, která má zvýrazněte elementy kódu a odkazy, které mají určité kategorie nebo vlastnost. To vám umožní identifikovat a zaměřit na konkrétní oblasti mapy. Můžete zadat vlastní ikony a barvy úpravou souboru .dgml mapy; v tématu [mapuje přizpůsobit kódu úpravou souborů DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md).  
  
#### <a name="to-apply-a-predefined-color-or-icon-to-code-elements-or-links-with-a-certain-category-or-property"></a>Aplikovat předdefinované nebo ikony na elementy kódu nebo propojení s určité kategorie nebo vlastnost  
  
1.  Na panelu nástrojů mapy zvolte **legendy**.  
  
2.  V **legendy** pole najdete v tématu, pokud kód element kategorie nebo vlastnost se již nachází v seznamu.  
  
3.  Pokud seznam neobsahuje kategorie nebo vlastnost, zvolte **+** v **legendy** pole, a potom vyberte **vlastnost uzlu**, **uzlu kategorie** , **Vlastnost propojení**, nebo **odkaz kategorie**. Potom vyberte vlastnost nebo kategorii. Kategorie nebo vlastnosti se teď zobrazí v **legendy** pole.  
  
    > [!NOTE]
    >  Vytvořit a přiřadit kategorie nebo vlastnost na element kódu, můžete upravit soubor .dgml mapy; v tématu [mapuje přizpůsobit kódu úpravou souborů DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md).  
  
4.  V **legendy** pole, klikněte na ikonu vedle kategorie nebo vlastnosti, které jste přidali nebo chcete změnit.  
  
5.  Pro výběr stylu, který chcete změnit, použijte následující tabulku:  
  
    |**Chcete-li změnit**|**Zvolte**|  
    |-----------------------|----------------|  
    |Barvu pozadí|**Pozadí**|  
    |Barva obrysu|**Tahu**|  
    |Barva textu (zobrazoval výsledky se zobrazí písmenem "f")|**Popředí**|  
    |Ikona|**Ikony**|  
  
     **Nastavit volby barev** nebo **výběr nastavit ikonu** zobrazí se dialogové okno vybrat barvu nebo ikonu.  
  
6.  V **nastavit volby barev** nebo **výběr nastavit ikonu** dialogové okno, proveďte jednu z následujících akcí:  
  
    |**Chcete-li použít**|**Proveďte tyto kroky**|  
    |--------------------|-----------------------------|  
    |Sadu barev nebo ikony|Otevřete **vyberte barvu** (nebo **ikonu**) **nastavit** seznamu. Vyberte sadu barev nebo ikon.|  
    |Konkrétní nebo ikony|Otevřete seznam hodnot kategorií nebo vlastností. Vyberte barvu nebo ikonu.|  
  
    > [!NOTE]
    >  Změna uspořádání, odstraňovat nebo dočasně zakázat styly v **legendy** pole. V tématu [textového pole legendy](#ModifyLegend).  
  
##  <a name="ModifyLegend"></a> Textové pole legendy  
 Změna uspořádání, odstraňovat nebo dočasně zakázat styly v **legendy** pole:  
  
1.  Otevřete pro styl v místní nabídce **legendy** pole.  
  
2.  Proveďte některou z následujících úloh:  
  
    |**K**|**Zvolte**|  
    |------------|----------------|  
    |Deaktivovat element kódu|**Zakázat**|  
    |Odstranit element kódu|**Odstranit**|  
    |Přesunutí stylu nahoru|**Přesunout nahoru**|  
    |Tento element kódu přesunout dolů|**Přesunout dolů**|  
  
##  <a name="CopyLegend"></a> Styly kopírovat z jednoho do jiného  
  
1.  Zajistěte, aby **legendy** pole se zobrazí na mapě zdroje. Pokud není viditelná, na panelu nástrojů mapy, klikněte na tlačítko **legendy**.  
  
2.  Otevřete místní nabídku pro **legendy** pole. Zvolte **zkopírujte legendy**.  
  
3.  Vložte legendu do cílové mapy.  
  
##  <a name="MergeMaps"></a> Sloučení mapy kódu  
 Zkopírováním a vložením elementy kódu mezi maps můžete sloučit mapy. Pokud se shodují se identifikátory element kódu, funkce elementy kódu vkládání jako operace sloučení. Chcete-li tato úloha jednodušší, uveďte všechna sestavení nebo binární soubory, které chcete vizualizovat ve stejné složce, aby úplnou cestu každé sestavení nebo binární je stejný pro každý mapu, která chcete sloučit.  
  
 Alternativně můžete přetáhněte tyto sestavení nebo binární soubory na stejné mapy, z této složky.  
  
## <a name="see-also"></a>Viz také  
 [Mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md)   
 [Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)   
 [Nalezení potenciálních problémů pomocí analyzátorů mapy kódu](../modeling/find-potential-problems-using-code-map-analyzers.md)   
 [Přizpůsobení map kódu úpravou souborů DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md)   
 [Referenční dokumentace jazyka přímého značení grafů (DGML)](../modeling/directed-graph-markup-language-dgml-reference.md)
