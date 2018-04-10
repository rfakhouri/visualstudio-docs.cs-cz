---
title: Mapování závislostí napříč vaším řešením | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
f1_keywords:
- vs.progression.codemap
- vs.progression.standardgraphsdialog
helpviewer_keywords:
- Visual Studio Ultimate, dependency graphs
- code exploration, dependency graphs
- dependency graphs, exporting
- code exploration, relationships
- DGML
- graph documents
- code visualization [Visual Studio ALM]
- graph documents, saving
- dependencies, visualizing
- dependency graphs, saving
- Visual Studio Ultimate, code visualization
- code, visualizing
- dependency graphs, creating
- dependency graphs
- graph documents, exporting
- code exploration, visualizing
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: aea44beeb2a8e6380bd9a568acdece79873e3050
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="map-dependencies-across-your-solutions"></a>Mapování závislostí napříč vaším řešením

Když chcete pochopit závislosti mezi kódu, Vizualizujte je pomocí vytváření map kódu. Díky tomu můžete zjistit, jak vyhovuje kód společně bez přečtení prostřednictvím soubory a řádků kódu.

![Zobrazení závislostí napříč vaším řešením](../modeling/media/codemapsmainintro.png "CodeMapsMainIntro")

**Tady jsou některé videa**:

- [Pochopení kódu závislostmi prostřednictvím vizualizace](https://channel9.msdn.com/Series/Visual-Studio-2012-Premium-and-Ultimate-Overview/Visual-Studio-Ultimate-2012-Understand-your-code-dependencies-through-visualization)

- [Vizualizace dopad změny](https://channel9.msdn.com/Series/Visual-Studio-2012-Premium-and-Ultimate-Overview/Visual-Studio-Ultimate-2012-Visualize-the-impact-of-a-change)

- [Seznámení s komplexní kódu pomocí map kódu](https://channel9.msdn.com/Series/Visual-Studio-2012-Premium-and-Ultimate-Overview/Visual-Studio-Ultimate-2012-Understanding-complex-code-with-Code-Map-ENU)

## <a name="GetStarted"></a> Začínáme s mapy kódu

**Použití map kódu musíte buď**:

-   Visual Studio Enterprise: Vytvoření mapy kódu z editoru kódu, Průzkumníka řešení, zobrazení tříd nebo prohlížeč objektů.  

-   Visual Studio Professional: Otevřete map kódu, provádět omezené úpravy a přejděte kódu.  

> [!WARNING]
>  Před sdílením mapy vytvořené v aplikaci Visual Studio Enterprise s ostatními uživateli, kteří používají Visual Studio Professional, ujistěte se, že všechny položky na mapě (například skryté položky, rozšířená skupiny a propojení mezi skupiny) jsou dostupná.  

 **Můžete namapovat závislosti pro kód v těchto jazycích**:  

-   Visual C# nebo Visual Basic v řešení nebo sestavení (.dll nebo .exe)  

-   Nativní nebo spravovaný kód C nebo C++ v projektech Visual C++, soubory hlaviček (.h nebo `#include`), nebo binárních souborů  

-   X ++ projekty a sestavení vytvořené z modulů .NET pro aplikace Microsoft Dynamics AX  

 **Poznámka:** pro projekty než C# nebo Visual Basic, jsou méně možností pro spuštění Mapa kódu nebo přidání položky do existující mapu kódu. Nelze například klikněte pravým tlačítkem na objekt v textovém editoru projektu C++ a přidat jej do Mapa kódu. Můžete však přetáhněte a vyřadit kódu jednotlivých elementů nebo soubory z Průzkumníku řešení, zobrazení tříd a prohlížeč objektů.  

#### <a name="to-see-the-overall-dependencies-across-your-solution"></a>Chcete-li zobrazit celkový závislosti mezi řešení  

1.  Otevřete **architektura** nabídky.  

2.  Pokud právě otevřené řešení a nebyly dosud integrovaný, nebo pokud došlo ke změně kódu od posledního jste vytvořili, zvolte **Generovat mapu kódu pro řešení**.  

3.  Pokud váš kód nezměnila od poslední vytvořené, vyberte **Generovat mapu kódu pro řešení bez vytvoření** získat vyšší výkon při vytváření mapy.  

4.  [V tématu celkové závislosti](#SeeOverviewSource) pochopit, jak můžete map kódu k zobrazení celkového závislosti mezi řešení.  

#### <a name="to-see-specific-dependencies-within-your-solution"></a>Pokud chcete zobrazit konkrétní závislosti v rámci vašeho řešení  

1.  S vaším řešením načíst, otevřete **Průzkumníku řešení**.  

2.  Vyberte všechny projekty, odkazy na sestavení, složky, soubory, typy nebo členy, které chcete namapovat.  

3.  Na **Průzkumníku řešení** nástrojů vyberte **zobrazit na mapě kódu**![vytvořit nový graf z vybrané uzly tlačítko](../modeling/media/createnewgraphfromselectedbutton.gif "CreateNewGraphFromSelectedButton "). Otevřete místní nabídku a vyberte **zobrazit na mapě kódu**. Můžete také přetáhnout položky ze zobrazení tříd nebo prohlížeč objektů do nové nebo existující mapu kódu.  

4.  [Najdete v části konkrétní závislosti](#SeeSpecificSource) pochopit, jak můžete map kódu k zobrazení konkrétní závislosti v rámci vašeho řešení.  

###  <a name="CreateEmptyMap"></a> Chcete-li přidat nové mapování prázdný kód do řešení  

1.  V **Průzkumníku**, otevřete místní nabídku pro vaše řešení nejvyšší úrovně uzlu. Zvolte **přidat** zvolte **novou položku**.  

2.  V části **nainstalovaná**, zvolte **Obecné**.  

3.  V pravém podokně vyberte **směrované dokumentu grafu** a potom zvolte **přidat**.  

     Nyní máte prázdnou mapu, která se zobrazí ve vašem řešení **položky řešení** složky.  

#### <a name="to-create-a-new-empty-code-map-without-adding-it-to-your-solution"></a>Chcete-li vytvořit nové mapování prázdný kód bez přidání do řešení  

1.  Otevřete **architektura** nabídky a zvolte **nové Mapa kódu**.  

     \- nebo –  

2.  Otevřete **soubor** nabídky a zvolte **nový** zvolte **soubor**.  

3.  V části **nainstalovaná**, zvolte **Obecné**.  

4.  V pravém podokně vyberte **směrované dokumentu grafu** a potom zvolte **otevřete**.  

     Nyní máte prázdné map, který nezobrazí ve složkách vaše řešení.  

##  <a name="SeeOverviewSource"></a> Zobrazit celkové závislosti  

###  <a name="OverviewSource"></a> Mezi řešení najdete v části závislosti  

1.  Na **architektura** nabídce zvolte **Generovat mapu kódu pro řešení**.  

     ![Generování příkazu mapy kódu](../modeling/media/codemapsarchitecturemenu.png "CodeMapsArchitectureMenu")  

     Zobrazí mapu, která zobrazuje sestavení nejvyšší úrovně a agregované propojení mezi nimi. Širší souhrnného propojení, další závislosti reprezentuje.  

2.  Použití **legendy** položky kód (například tříd, metod a vlastností) a typy vztahů (například dědí z tlačítko na panelu nástrojů Mapa kódu zobrazit nebo skrýt seznam ikony typu projektu (například Test, webové a Phone projektu) Implementuje a volání).  

     ![Horní&#45;graf úrovně závislostí sestavení](../modeling/media/dependencygraph_toplevelassemblies.png "DependencyGraph_TopLevelAssemblies")  

     Tento příklad řešení obsahuje složky řešení (**testy** a **součásti**), projektů testů, webové projekty a sestavení. Ve výchozím nastavení zobrazí všechny vztahy členství ve skupině jako *skupiny*, které můžete rozbalit nebo sbalit. **Externals** skupina obsahuje nic mimo řešení, včetně závislostí platformy. Externí sestavení obsahuje pouze položky, které jsou používány. Ve výchozím nastavení jsou na mapě pro lepší přehlednost skrytá základní typy systému.  

3.  Můžete rozbalit mapy, rozbalte položku skupiny, které představují projekty a sestavení. Můžete rozbalit vše, co stisknutím **CTRL + A** vyberte všechny uzly a pak vyberete **skupiny**, **rozbalte** z místní nabídky.  

     ![Rozbalení všech skupin v mapě kódu](../modeling/media/codemapsexpandallgroups.png "CodeMapsExpandAllGroups")  

4.  To však nemusí být užitečné pro velké řešení. Ve skutečnosti pro komplexní řešení, omezení paměti může zabránit vám v rozšíření všechny skupiny. Místo toho pokud chcete zobrazit v jednotlivých uzlu, rozbalte ho. Přesuňte ukazatel myši nad uzel a potom klikněte na dvojitou šipku (šipka) dolů Jakmile se zobrazí.  

     ![Rozšíření uzlu v mapě kódu](../modeling/media/dependencygraph_containment.png "DependencyGraph_Containment")  

     Nebo pomocí klávesnice tak, že vyberete položku pak stisknete klávesu plus (**+**). Chcete-li prozkoumat podrobněji úrovně kódu, proveďte stejný pro obory názvů, typy a členy.  

    > [!TIP]
    >  Pro další podrobnosti o práci s kódem mapuje pomocí myši, klávesnice a dotykového ovládání, naleznete v tématu [Procházet a uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md).  

5.  Pro zjednodušení mapy a zaměřit se na jednotlivé části, zvolte **filtry** na panelu nástrojů Mapa kódu a vyberte pouze typy uzlů a odkazy vás zajímá. Například můžete skrýt všechny složky řešení a sestavení kontejnery.  

     ![Zjednodušení mapy filtrováním kontejnery](../modeling/media/codemapsfilterfoldersassemblies.png "CodeMapsFilterFoldersAssemblies")  

     Skrytí nebo odebráním jednotlivých skupin a položek z mapování, aniž by to ovlivnilo kód základní řešení můžete také zjednodušit mapy.  

6.  Pokud chcete zobrazit vztahy mezi položkami, vyberte je v mapě. Barvy odkazy označují typy relace, jak je znázorněno **legendy** podokně.  

     ![Zobrazení závislostí napříč vaším řešením](../modeling/media/codemapsmainintro.png "CodeMapsMainIntro")  

     V tomto příkladu jsou odkazy na fialové volání, jsou odkazy na desítkovém odkazy a světla modré odkazy jsou přístup k poli. Zelená odkazy mohou být dědičnosti nebo mohou být *agregovat odkazy* indikující, více než jeden typ vztahu (nebo *kategorie*).  

    > [!TIP]
    >  Pokud se zobrazí zelená odkaz, nemusí to znamená, že je právě vztah dědičnosti. Může také být volání metod, ale tyto skryt vztah dědičnosti. Pokud chcete zobrazit konkrétní typy odkazů, pomocí zaškrtávacích políček v **filtry** podokně typy nemusí.  

7.  Chcete-li získat další informace o položku nebo odkaz, přesuňte ukazatel myši nad jeho se zobrazí popisek. Ukazuje to podrobností element kódu nebo kategorie, které představuje odkaz.  

     ![Zobrazit kategorie relace](../modeling/media/codemapsshowlinkcatgories.png "CodeMapsShowLinkCatgories")  

8.  Chcete-li zkontrolujte položky a závislosti reprezentována souhrnného propojení, nejprve vyberte odkaz a pak otevřete jeho místní nabídky. Zvolte **zobrazit přidání odkazů** (nebo **zobrazit přidání odkazů na nové Mapa kódu**). To rozbalí skupiny na obou koncích propojení a zobrazuje pouze položky a závislosti, které se účastní v odkazu.  

9. Chcete-li se zaměřit na konkrétní části mapy, můžete nadále odebrat položky, které nechcete. Například přejdete do zobrazení třídy a člen, jednoduše filtrovat všechny uzly oboru názvů v **filtry** podokně.  

     ![Přecházení na úrovni třídy a člen](../modeling/media/dependencygraph_expandedselectedgroups_2012.png "DependencyGraph_ExpandedSelectedGroups_2012")  

10. Dalším způsobem, abyste se mohli zaměřit na mapě komplexní řešení je generovat nové mapování obsahující vybrané položky z existující mapu. Uložení **CTRL** , že při výběru položky, které chcete se zaměřit na, otevřete místní nabídku a vyberte **nový graf z výběru**.  

     ![Zobrazit vybrané položky na nové mapě kódu](../modeling/media/codemapsshowonnewmap.png "CodeMapsShowOnNewMap")  

11. Obsahující kontext se přenášejí do nové mapování. Skrýt složky řešení a žádné kontejnery, které nechcete zobrazit pomocí **filtry** podokně.  

     ![Filtrovat kontejnery zjednodušit zobrazení](../modeling/media/codemapsexpandnewgroups.png "CodeMapsExpandNewGroups")  

12. Skupiny rozbalte a vyberte položky v mapě zobrazíte vztahy.  

     ![Vyberte položky k zobrazení vztahy](../modeling/media/codemapsviewnewrelationships.png "CodeMapsViewNewRelationships")  

 Viz také:  

-   [Procházení a změna uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md)  

-   [Přizpůsobení map kódu úpravou souborů DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md)  

-   Nalezení potenciálních problémů v kódu pomocí [systémem analyzátor](../modeling/find-potential-problems-using-code-map-analyzers.md).  

###  <a name="OverviewCompiled"></a> Najdete v části závislosti mezi sestavení nebo binárních souborů  

1.  [Vytvořit prázdný kód mapu](#GetStarted), ani otevřít existující kód mapu (soubor .dgml).  

2.  Přetáhněte sestavení nebo binární soubory, které chcete namapovat mimo aplikaci Visual Studio na mapě. Například přetáhněte sestavení nebo binární soubory z Průzkumníka Windows nebo Průzkumníka souborů.  

> [!NOTE]
>  Můžete přetáhnout sestavení nebo binární soubory z Průzkumníka Windows nebo Průzkumníka souborů pouze v případě, že používáte ho a Visual Studio na stejné úrovni oprávnění přístupu k řízení Uživatelských účtů. Například pokud je zapnutý nástroj Řízení uživatelských účtů a používáte Visual Studio jako správce, Průzkumníka Windows nebo soubor Explorer zablokuje přetahování operaci. Chcete-li tento problém obejít, ujistěte se, jak běží se stejnou úrovní oprávnění, nebo vypnutí nástroje Řízení uživatelských účtů.  

##  <a name="SeeSpecificSource"></a> Najdete v části konkrétní závislosti  
 Předpokládejme například, že máte revize kódu provádět v některé soubory s změny čekající na zpracování. Pokud chcete zobrazit závislosti ve tyto změny, můžete vytvořit Mapa kódu z těchto souborů.  

 ![Zobrazit na mapě kódu konkrétní závislosti](../modeling/media/codemapsspecificdependenciesintro.png "CodeMapsSpecificDependenciesIntro")  

### <a name="see-specific-dependencies-in-your-solution"></a>Najdete v části konkrétní závislosti ve vašem řešení  

1.  Otevřete **Průzkumníku řešení**. Vyberte projekty, odkazy na sestavení, složky, soubory, typy a členy, které vás zajímají. K nalezení položek, které mají závislosti na typy nebo členy, otevřete typ nebo člena místní nabídky z **Průzkumníku řešení**. Zvolte typ závislosti a pak vyberte výsledky.  

2.  Mapování položek a jejich členové. Na **Průzkumníku řešení** panelu nástrojů klikněte na tlačítko **zobrazit na mapě kódu**![vytvořit nový graf z vybrané uzly tlačítko](../modeling/media/createnewgraphfromselectedbutton.gif "CreateNewGraphFromSelectedButton").  

     ![Vyberte položky, kterou chcete mapovat](../modeling/media/codemapsselectinsolutionexplorer.png "CodeMapsSelectInSolutionExplorer")  

3.  Mapa zobrazuje vybrané položky v rámci jejich obsahující sestavení.  

     ![Vybrané položky zobrazené jako skupiny na mapě](../modeling/media/codemapsshowitemsfromsolnexplorer.png "CodeMapsShowItemsFromSolnExplorer")  

     Také můžete přetáhnout položky z Průzkumníka řešení, zobrazení tříd nebo prohlížeč objektů na prázdný nebo existující mapu kódu. Chcete-li vytvořit prázdnou mapu, najdete v části [vytvořit mapu prázdný kód](#GetStarted). Chcete-li zahrnout nadřazenou hierarchii pro své položky, stiskněte a podržte **CTRL** klíče při přetahování položek, nebo použít **zahrnují nadřazené položky** tlačítka na panelu nástrojů map kódu k určení výchozí akci.  

    > [!NOTE]
    >  Když přidáváte položky z projektu, který je sdílen napříč více aplikacemi, jako jsou Windows Phone nebo Windows Store, tyto položky se zobrazí na mapě s aktuálně aktivním projektem aplikace. Pokud změníte kontext na jiný projekt aplikace a přidáte další položky ze sdíleného projektu, tyto položky se nyní zobrazí s nově aktivním projektem aplikace. Operace, které provádíte s položkou na mapě, se vztahují pouze na ty položky, které sdílejí stejný kontext.  

4.  Chcete-li prozkoumat položky, rozbalte je. Přesuňte ukazatel myši nad položku a pak klikněte na ikonu dvojité šipky (šipka) dolů, když se objeví.  

     ![Rozšíření uzlu v mapě kódu](../modeling/media/dependencygraph_containment.png "DependencyGraph_Containment")  

     Chcete-li rozšířit všechny položky, vyberte je pomocí **CTRL + A**, otevřete místní nabídku pro mapu a vyberte **skupiny**, **rozbalte**. Však tato možnost není dostupná, pokud se zvětšující všechny skupiny vytvoří nepoužitelná mapy nebo problémy s pamětí.  

5.  Rozbalte položky, které vás zajímají, až na úrovni třídy a člen v případě potřeby i nadále.  

     ![Rozšíření skupiny na úrovni třídy a člen](../modeling/media/codemapsexpandtoclassandmember.png "CodeMapsExpandToClassAndMember")  

     Pokud chcete zobrazit členy, kteří jsou v kódu, ale nezobrazí na mapě, klikněte **znovu načíst podřízené objekty** ikonu ![znovu načíst ikonu podřízené objekty](../modeling/media/dependencygraph_deletednodesicon.png "DependencyGraph_DeletedNodesIcon") v horní části levém horním rohu skupinu.  

6.  Pokud chcete zobrazit další položky související s ohledem na mapě, vyberte jeden a zvolte **zobrazit související** na panelu nástrojů Mapa kódu, pak vyberte typ souvisejících položek, které chcete přidat do mapy. Nebo vyberte jednu nebo více položek, otevřete místní nabídku a pak zvolte **zobrazit...**  možnost pro typ související položky pro přidání do mapy. Příklad:  

     Pro **sestavení**, vyberte:  

    |||  
    |-|-|  
    |**Zobrazit tuto odkazy na sestavení**|Přidejte sestavení, na které odkazuje toto sestavení. Externí sestavení se zobrazí v **Externals** skupiny.|  
    |**Zobrazit to odkazování na sestavení**|Přidejte sestavení do řešení, která odkazují na toto sestavení.|  

     Pro **obor názvů**, zvolte **zobrazit sestavení obsahující**, pokud není viditelná.  

     Pro **třída** nebo **rozhraní**, vyberte:  

    |||  
    |-|-|  
    |**Zobrazit základní typy**|V případě třídy přidejte základní třídu a implementovaná rozhraní.<br /><br /> V rámci rozhraní přidejte základní rozhraní.|  
    |**Zobrazit odvozené typy**|V případě třídy přidejte odvozené třídy.<br /><br /> V rámci rozhraní přidejte odvozené rozhraní a implementaci tříd nebo struktur.|  
    |**Zobrazit typy tento odkazy**|Přidejte všechny třídy a jejich členy, které tato třída používá.|  
    |**Zobrazit typy to odkazování na**|Přidejte všechny třídy a jejich členy, které tuto třídu používají.|  
    |**Zobrazení obsahujícího Namespace**|Přidáte obor názvů nadřazené.|  
    |**Zobrazit obsahující Namespace a sestavení**|Přidejte hierarchii nadřazeného kontejneru.|  
    |**Zobrazit všechny základní typy**|Přidejte rekurzivně hierarchii základní třídy nebo rozhraní.|  
    |**Zobrazit všechny odvozené typy**|V případě třídy přidejte všechny odvozené třídy rekurzivně.<br /><br /> V rámci rozhraní přidejte rekurzivně veškerá odvozená rozhraní a implementaci tříd nebo struktur.|  

     Pro **metoda**, vyberte:  

    |||  
    |-|-|  
    |**Zobrazit metody, které volá**|Přidejte metody, které tato metoda volá.|  
    |**Zobrazit tuto odkazy na pole**|Přidejte pole, na která odkazuje tato metoda.|  
    |**Zobrazit obsahující typ**|Přidejte typ nadřazené.|  
    |**Zobrazit obsahující typ, Namespace a sestavení**|Přidejte hierarchii nadřazeného kontejneru.|  
    |**Zobrazit přepsání metody**|V případě metody, která přepíše jiné metody nebo implementuje metodu rozhraní, přidejte všechny abstraktní nebo virtuální metody základních tříd, které jsou přepsány, a případně metodu rozhraní, které je implementováno.|  

     Pro **pole** nebo **vlastnost**, vyberte:  

    |||  
    |-|-|  
    |**Zobrazit obsahující typ**|Přidejte typ nadřazené.|  
    |**Zobrazit obsahující typ, Namespace a sestavení**|Přidejte hierarchii nadřazeného kontejneru.|  

     ![Zobrazit metody volá tento člen](../modeling/media/codemapsshowrelatedmethods.png "CodeMapsShowRelatedMethods")  

7.  Mapa znázorňuje vztahy. V tomto příkladu volá metody `Find` metoda a jejich umístění v řešení nebo externě.  

     ![Zobrazit na mapě kódu konkrétní závislosti](../modeling/media/codemapsspecificdependenciesintro.png "CodeMapsSpecificDependenciesIntro")  

8.  Pro zjednodušení mapy a zaměřit se na jednotlivé části, zvolte **filtry** na panelu nástrojů Mapa kódu a vyberte pouze typy uzlů a odkazy vás zajímá. Například Vypněte displej řešení složek, sestavení a obory názvů.  

     ![Použijte podokno filtru pro zjednodušení zobrazení](../modeling/media/almcodemapfilterpane.png "ALMCodeMapFilterPane")  

##  <a name="SeeSourceHeader"></a> Najdete v části závislosti mezi C a C++ zdrojové soubory a soubory hlaviček  
 Pokud chcete vytvořit podrobnější mapy pro projekty C++, nastavte možnost Procházet informace kompilátoru (**/FR**) na těchto projekty. Jinak se objeví zpráva s dotazem, zda chcete tuto možnost nastavit. Pokud vyberete **OK**, nastaví tato možnost pouze aktuální mapy. Můžete skrýt zprávu pro všechny novější mapy. Pokud je skrýt tuto zprávu, můžete nastavit znovu zobrazí. Nastavte následující klíč registru na `0` nebo odstranit klíč:  

 **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\14.0\NativeProvider : AutoEnableSbr**  

 Když otevřete řešení, které obsahuje projekty Visual C++, může trvat nějakou dobu, než se aktualizuje databáze technologie IntelliSense. Během této doby, není možné vytvořit map kódu hlavičky (.h nebo `#include`) soubory, dokud nebude dokončeno databázi IntelliSense aktualizace. Na stavovém řádku v dolní části sady Visual Studio můžete sledovat průběh aktualizace. Chcete-li vyřešit problémy nebo zprávy, které se zobrazují, protože jsou zakázaná určitá nastavení IntelliSense, najdete v části [řešení potíží s mapy pro kód C a C++](#Troubleshooting).  

-   Zobrazit závislosti mezi všechny zdrojové soubory a soubory hlaviček ve vašem řešení na **architektura** nabídce zvolte **generovat grafu zahrnout soubory**.  

     ![Graf závislostí pro nativní kód](../modeling/media/dependencygraphgeneral_nativecode.png "DependencyGraphGeneral_NativeCode")  

-   Chcete-li zobrazit závislosti mezi aktuálně otevřených souborů a související zdrojové soubory a soubory hlaviček, otevřete zdrojový soubor nebo soubor hlaviček. Otevřete soubor místní nabídky kdekoli v souboru. Zvolte **Generovat graf zahrnout soubory**.  

     ![První&#45;graf úrovně závislostí pro soubor h](../modeling/media/dependencygraph_native_firstlevel.png "DependencyGraph_Native_FirstLevel")  

###  <a name="Troubleshooting"></a> Řešení potíží s mapy pro kód C a C++  
 Tyto položky nejsou podporovány pro kód C a C++:  

-   Základní typy nezobrazí v maps, které zahrnují nadřazenou hierarchii.  

-   Většina **zobrazit** položky nabídky nejsou k dispozici pro kód C a C++.  

 K těmto problémům může dojít v případě, že vytvoříte map kódu pro kód C a C++:  

|**Problém**|**Možná příčina**|**Řešení**|  
|---------------|------------------------|--------------------|  
|Mapa kódu se nepodařilo vygenerovat.|V řešení nebyly úspěšně sestaveny žádné projekty.|Opravte chyby sestavení, které nastaly a pak znovu vygenerovat mapy.|  
|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] přestane reagovat při pokusu o generování mapy kódu z **architektura** nabídky.|Soubor databáze programů (.pdb) může být poškozen.<br /><br /> Soubor .pdb ukládá informace o ladění, jako je typ, metoda a informace zdrojového souboru.|Znovu sestavte řešení a potom akci opakujte.|  
|Určitá nastavení pro databázi procházení IntelliSense jsou zakázána.|Určitá nastavení IntelliSense může být zakázáno v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] **možnosti** dialogové okno.|Chcete-li tato nastavení povolit, zapněte je.<br /><br /> V tématu [možnosti, textový Editor, C/C++, Upřesnit](../ide/reference/options-text-editor-c-cpp-advanced.md).|  
|Zpráva **neznámé metody** se zobrazí v uzlu metoda.<br /><br /> K tomuto problému dochází, protože nelze vyřešit název metody.|Binární soubor nemusí mít základní tabulku přemístění.|Zapnout **/FIXED:NO** možnost v linkeru.|  
||Soubor databáze programů (.pdb) nemusí být vytvořen.<br /><br /> Soubor .pdb ukládá informace o ladění, jako je typ, metoda a informace zdrojového souboru.|Zapnout **/DEBUG** možnost v linkeru.|  
||V očekávaných umístěních nelze otevřít nebo najít soubor .pdb.|Ujistěte se, že v předpokládaném umístění existuje soubor .pdb.|  
||Informace o ladění byly ze souboru .pdb odstraněny.|Pokud **/PDBSTRIPPED** možnost byl použit v linkeru, místo toho zahrnout soubor .pdb dokončení.|  
||Volající není funkcí a je převodní rutinou v binárním souboru nebo ukazatelem v datové sekci.|Pokud má volající převodu, zkuste použít `_declspec(dllimport)` předejdete převodu.|  

##  <a name="RenderMoreQuickly"></a> Ujistěte se, kód, který mapuje vykreslení rychleji  
 Při generování mapu poprvé, Visual Studio indexuje všechny závislosti, které nalezne. Tento proces může určitou dobu trvat, zejména u velkých řešení, ale umožní zvýšení výkonu později. Pokud se váš kód změní, Visual Studio znovu indexovat pouze aktualizovaný kód. Chcete-li minimalizovat čas potřebný pro mapování na dokončení vykreslování, zvažte následující:  

-   [Mapovat jenom závislosti, které vás zajímají.](#SeeSpecificSource)  

-   Před generováním mapy pro celé řešení snížit rozsah řešení.  

-   Vypnout automatické sestavení řešení s **přeskočit sestavení** tlačítka na panelu nástrojů map kódu.  

-   Vypnout automatické přidání nadřazených položek s **zahrnují nadřazené položky** tlačítka na panelu nástrojů map kódu.  

-   Upravte soubor mapy kódu přímo pro odebrání uzlů a odkazy, které nepotřebujete. Změna mapy neovlivní kódu. V tématu [mapuje přizpůsobit kódu úpravou souborů DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md).  

 ![Přeskočit sestavení a zahrnují nadřazených prvků tlačítek](../modeling/media/codemapsfilterskipbuildicons.png "CodeMapsFilterSkipBuildIcons")  

 I když Visual Studio můžete spustit s 1 GB paměti, doporučujeme, že počítače mají alespoň 2 GB paměti k tomu velká zpoždění, Visual Studio vytvoří index kódu a generuje mapy.  

 Může trvat delší dobu k vytvoření mapy nebo přidání položky do mapy v Průzkumníku řešení, pokud položka projektu **kopírovat do výstupního adresáře** je nastavena na **kopie vždy**. To může způsobit problémy s přírůstkovým sestavením a opakovaným sestavením projektu aplikací Visual Studio. Chcete-li zvýšit výkon, změňte tuto vlastnost, aby **kopírovat, pokud je novější** nebo `PreserveNewest`. V tématu [přírůstkové sestavení](../msbuild/incremental-builds.md).  

 Dokončené mapy zobrazí závislosti pouze pro kód úspěšně vytvořen. Pokud dojde k chybám sestavení pro určité součásti, zobrazí se tyto chyby na mapě. Ujistěte se, že komponentu ve skutečnosti sestavení a před provedením architektury rozhodnutí, která na základě mapy má závislosti na.  

##  <a name="SavingExporting"></a> Sdílet mapy kódu  

### <a name="share-the-map-with-other-visual-studio-users"></a>Mapy sdílet s ostatními uživateli v sadě Visual Studio  
 Použití **souboru** v nabídce mapy.  

 -nebo-  

 Chcete-li uložit mapy v rámci konkrétní projektu, na panelu nástrojů mapy, zvolte **sdílené složky**, **přesunout** \< *CodeMapName*>**.dgml do**a pak zvolte projekt, kam chcete uložit mapy.  

 ![Přesunout do jiného projektu mapu](../modeling/media/codemapsmovemapmenu.png "CodeMapsMoveMapMenu")  

 Visual Studio uloží jako soubor .dgml, které můžete sdílet s ostatními uživateli aplikace Visual Studio Enterprise a Visual Studio Professional mapy.  

> [!NOTE]
>  Před sdílením mapu s ty, kteří používají Visual Studio Professional, nezapomeňte rozbalte všechny skupiny, zobrazit skryté uzly a cross-group odkazy a načíst všechny odstraněné uzly, které chcete zobrazit na mapě ostatním uživatelům. Jinak ostatní uživatelé nebudou moci tyto položky zobrazit.  
>   
>  Při uložení mapu, která je v projektu modelování nebo byl zkopírován z projektu modelování do jiného umístění, může dojít k následující chybě:  
>   
>  "Nelze uložit *fileName* mimo adresář projektu. Propojené položky nejsou podporovány.“  
>   
>  Aplikace Visual Studio zobrazí chybu, ale přesto vytvoří uloženou verzi. Aby nedošlo k chybě, vytvoření mapy mimo projekt modelování. Potom jej můžete uložit do požadovaného umístění. Nebude fungovat, pokud budete chtít soubor pouze zkopírovat do jiného umístění v řešení a potom jej uložit.  

### <a name="export-the-map-as-an-image-so-you-can-copy-it-into-other-applications-such-as-microsoft-word-or-powerpoint"></a>Exportovat mapy jako bitovou kopii, takže byste ho zkopírovat do jiných aplikací, jako je například Microsoft Word nebo PowerPoint  

1.  Na panelu nástrojů Mapa kódu, zvolte **sdílené složky**, **e-mailu jako obrázek** nebo **Kopírovat obraz**.  

2.  Vložte obrázek do jiné aplikace.  

### <a name="export-the-map-as-an-xps-file-so-you-can-see-it-in-xml-or-xaml-viewers-like-internet-explorer"></a>Mapování exportovat jako soubor ve formátu XPS, aby se zobrazily v XML nebo XAML prohlížeče, jako třeba Internet Explorer  

1.  Na panelu nástrojů Mapa kódu, zvolte **sdílené složky**, **e-mailu jako přenosné XPS** nebo **uložit jako přenosné XPS**.  

2.  Kam chcete uložit soubor vyhledejte.  

3.  Název Mapa kódu. Ujistěte se, že **uložit jako typ** pole je nastavena na **soubory XPS (\*XPS)**. Zvolte **Uložit**.  

## <a name="what-else-can-i-do"></a>Co dalšího mohu udělat?  

-   [Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)  

-   [Mapování metod v zásobníku volání při ladění](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)  

-   [Nalezení potenciálních problémů pomocí analyzátorů mapy kódu](../modeling/find-potential-problems-using-code-map-analyzers.md)  

-   [Procházení a změna uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md)  

-   [Přizpůsobení map kódu úpravou souborů DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md)
