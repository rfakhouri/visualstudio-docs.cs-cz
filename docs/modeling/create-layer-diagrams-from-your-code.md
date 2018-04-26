---
title: Vytváření diagramů závislost z vašeho kódu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- architecture, dependency diagrams
- dependency diagrams
- diagrams - modeling, layer
- constraints, architectural
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 3a34d52bb4b9af535d1b11843967ac5b9619a153
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="create-dependency-diagrams-from-your-code"></a>Vytváření diagramů závislost z vašeho kódu

K vizualizaci Architektura vysoké úrovně, logické systému softwaru, vytvořit *diagram závislostí* v sadě Visual Studio. Abyste měli jistotu, že váš kód zůstává konzistentní s Tento návrh, ověření kódu s diagram závislostí. Můžete vytvořit diagramy závislostí pro projekty Visual C# a Visual Basic. Tuto funkci podporovat kterou verzí sady Visual Studio najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

![Vytvoření diagramu závislostí](../modeling/media/layerdiagramvisualizecode.png "LayerDiagramVisualizeCode")

Diagram závislostí umožňuje uspořádat do logických, abstraktní skupin nazývaných položky řešení sady Visual Studio *vrstvy*. Pomocí vrstev můžete popsat hlavní úlohy, které provádějí tyto artefakty, nebo hlavní komponenty systému. Každá vrstva může obsahovat další vrstvy, které popisují podrobnější úlohy. Můžete také určit určené nebo existující *závislosti* mezi vrstvami. Tyto závislosti, které jsou reprezentovány šipkami, zobrazují, které vrstvy mohou použít nebo právě používají funkce představované ostatními vrstvami. Chcete-li si udržet architektonickou kontrolu nad kódem, zobrazte zamýšlené závislosti v diagramu a potom ověřte kód proti diagramu.

[Video: Ověření svoje závislosti architektury v reálném čase](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)

##  <a name="CreateDiagram"></a> Vytvoření diagramu závislostí

Než vytvoříte diagram závislostí, ujistěte se, že vaše řešení s projektem modelování.

> [!IMPORTANT]
> Nepřidávejte, přetáhněte nebo zkopírujte existujícího diagramu závislost z projektem modelování, do jiného projektu modelování nebo na jiné místo v řešení. Tím budou zachovány odkazy z původního diagramu i v případě, že změníte diagram. Rovněž to způsobí, že ověřování vrstev nebude fungovat správně. Důsledkem mohou být i další problémy, jako jsou například chybějící prvky nebo jiné chyby při pokusu o otevření diagramu.
>
> Místo toho přidejte nový diagram závislost na projekt modelování. Zkopírujte prvky ze zdrojového diagramu do nového diagramu. Uložte projekt modelování a nový diagram závislostí.

#### <a name="to-add-a-new-dependency-diagram-to-a-modeling-project"></a>Chcete-li přidat nový diagram závislost na projekt modelování

1.  Na **architektura** nabídce zvolte **nový Diagram závislostí**.

2.  V části **šablony**, zvolte **diagram závislostí**.

3.  Pojmenujte diagram.

4.  V **přidat do projektu modelování**, vyhledejte a vyberte existující projekt modelování ve vašem řešení.

     -nebo-

     Zvolte **vytvořte nový projekt modelování** přidat nový projekt modelování do řešení.

    > [!NOTE]
    >  Diagram závislostí musí existovat v projektu modelování. Můžete jej však propojit s položkami kdekoli v řešení.

5.  Ujistěte se, že uložte projekt modelování a diagram závislostí.

## <a name="drag-and-drop-or-copy-and-paste-from-a-code-map"></a>Přetáhněte a vyřadit, nebo zkopírujte a vložte z Mapa kódu

1. Generovat mapu kódu pro řešení pomocí **architektura** nabídky.

2. Zvažte použití filtru Map kódu k odebrání složek řešení a "Test aktiva", pokud chcete vynutit závislostí v kód produktu.

3. Na generovaných Map kódu odeberte uzlu "Externí" nebo rozbalit a zobrazit externí sestavení, a to v závislosti na tom, jestli chcete vynutit závislosti obor názvů a odstranit bez potřeby sestavení z Mapa kódu.

4. Vytvořit nový Diagram závislostí pro řešení pomocí **architektura** nabídky

5. Vyberte všechny uzly na mapě kódu (použijte _Ctrl_ + _A_, nebo použijte výběr pružné vzdálené stisknutím _Shift_ klíče před klikněte na tlačítko, přetáhněte a verzi.

6. Přetahování, nebo kopírování a vložení, vybrané elementy do nového diagramu závislostí ověření.

7. Ukazuje to architektuře aktuální aplikace. Rozhodnete, co chcete architektura být a odpovídajícím způsobem upravit diagram závislostí.

![Diagram závislostí generovaných Map kódu](media/dependency-validation-01.png)

##  <a name="CreateLayers"></a> Vytvoření vrstev z artefaktů
 Vrstvy můžete vytvářet z položek řešení sady Visual Studio, jako jsou projekty, soubory kódu, obory názvů, třídy a metody. Tím se automaticky vytvoří spojení mezi vrstvami a položkami, čímž dojde k jejich zahrnutí do procesu ověření vrstev.

 Vrstvy můžete spojovat i s položkami, které ověřování nepodporují, jako například dokumenty aplikace Word nebo prezentace aplikace PowerPoint, takže vrstvu můžete přidružit ke specifikacím nebo plánům. Vrstvy můžete také spojovat se soubory v projektech, které jsou sdíleny napříč více aplikacemi, ale proces ověření nebude zahrnovat ty vrstvy, které se zobrazí s obecnými názvy, například „Vrstva 1“ a „Vrstva 2“.

 Pokud chcete zobrazit, pokud propojené položky podporuje ověřování, otevřete **vrstvy Průzkumníka** a prozkoumat **podporuje ověřování** vlastnosti položky. V tématu [Správa odkazy na artefakty](#Managing).

|**K**|**Postupujte podle těchto kroků**|
|------------|----------------------------|
|Vytvoření vrstvy pro jeden artefakt|<ol><li>Přetáhněte ji do diagramu závislost z těchto zdrojů:<br /><br /> <ul><li>**Průzkumník řešení**<br /><br />         Přetáhnout můžete například soubory nebo projekty.</li><li>Mapy kódu<br /><br />         V tématu [mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md) a [mapuje použití kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md).</li><li>**Třídy zobrazení** nebo **objektu prohlížeče**</li></ul><br />     Vrstva se zobrazí v diagramu a je propojena s artefaktem.</li><li>Přejmenujte vrstvu tak, aby odrážela odpovědnosti přidruženého kódu nebo artefaktů.</li></ol> **Důležité:** přetahování binární soubory do diagramu závislosti automaticky nepřidá jejich odkazy na projekt modelování. Binární soubory, které chcete ověřit, je třeba ručně přidat do projektu modelování. **Chcete-li přidat binární soubory do projektu modelování** <ol><li>V **Průzkumníku řešení**, otevřete místní nabídku pro modelování projekt a zvolte **přidat existující položku**.</li><li>V **přidat existující položku** dialogové okno, přejděte do binární soubory, vyberte je a pak zvolte **OK**.     Binární soubory se zobrazí v projektu modelování.</li><li>V **Průzkumníku řešení**, vyberte binární soubor, který jste přidali a stiskněte klávesu **F4** otevřete **vlastnosti** okno.</li><li>Na každý binární soubor, nastavte **akce sestavení** vlastnost **ověřením**.</li></ol>|
|Vytvoření jedné vrstvy pro všechny vybrané artefakty|Přetáhněte všechny artefakty diagramu závislostí ve stejnou dobu.<br /><br /> Vrstva se zobrazí v diagramu a je propojena se všemi artefakty.|
|Vytvoření vrstvy pro každý vybraný artefakt|Stisknutím a podržením **SHIFT** klíče a všechny artefakty přetáhněte do diagramu závislostí ve stejnou dobu. **Poznámka:** Pokud použijete **SHIFT** klíči vyberte položky, uvolněte klávesu po výběru artefakty. Stiskněte a podržte ji znovu, když přetahujete artefakty do diagramu. <br /><br /> Vrstva pro každý artefakt se zobrazí v diagramu a je propojena se všemi artefakty.|
|Přidání artefaktu do vrstvy|Přetáhněte artefakt do vrstvy.|
|Vytvoření nové nepropojené vrstvy|V **sada nástrojů**, rozbalte **Diagram závislostí** části a poté přetáhněte **vrstvy** diagramu závislostí.<br /><br /> Chcete-li přidat více vrstev, dvakrát na nástroj klikněte. Po dokončení klikněte **ukazatel** nástroj nebo klikněte na tlačítko **ESC** klíč.<br /><br /> - nebo -<br /><br /> Otevřete místní nabídku pro diagram závislostí, zvolte **přidat**a potom zvolte **vrstvy**.|
|Vytvoření vnořených vrstev|Přetáhněte existující vrstvu na jinou vrstvu.<br /><br /> - nebo -<br /><br /> Otevřete místní nabídku pro vrstvu, zvolte **přidat**a potom zvolte **vrstvy**.|
|Vytvoření nové vrstvy, která obsahuje dvě nebo více existujících vrstev|Vyberte vrstvy, otevřete místní nabídku pro váš výběr a potom zvolte **skupiny**.|
|Změna barvy vrstvy|Nastavte její **barva** vlastnost na požadovanou barvu.|
|Zadání toho, aby artefakty spojené s vrstvou nesměly patřit zadanému oboru názvů|Zadejte obory názvů na vrstvě **zakázáno obory názvů** vlastnost. Použijte středník (**;**) pro samostatné obory názvů.|
|Zadání toho, aby artefakty spojené s vrstvou nemohly záviset na zadaných oborech názvů|Zadejte obory názvů na vrstvě **zakázáno závislosti Namespace** vlastnost. Použijte středník (**;**) pro samostatné obory názvů.|
|Zadání toho, aby artefakty spojené s vrstvou musely patřit jednomu ze zadaných oborů názvů|Zadejte obor názvů na vrstvě **požadované obory názvů** vlastnost. Použijte středník (**;**) pro samostatné obory názvů.|

 Číslo ve vrstvě udává počet artefaktů, které jsou spojeny s vrstvou. Při čtení tohoto čísla však pamatujte na následující skutečnosti:

-   Pokud vrstva odkazuje na artefakt, který obsahuje jiné artefakty, ale vrstva není propojena přímo s jiným artefaktem, pak číslo obsahuje pouze propojené artefakty. Jiné artefakty jsou však zahrnuty do analýzy během ověřování vrstvy.

     Pokud je vrstva například spojena s jedním oborem názvů, pak počet propojených artefaktů je 1, přestože obor názvů obsahuje třídy. Pokud vrstva obsahuje rovněž propojení s jednotlivými třídami v oboru názvů, bude počet zahrnovat propojené třídy.

-   Pokud například vrstva obsahuje jiné vrstvy, které jsou spojeny s artefakty, pak je vrstva kontejneru také propojena s těmito artefakty, i když číslo vrstvy kontejneru tyto artefakty neobsahuje.

##  <a name="Managing"></a> Správa odkazů mezi vrstvy a artefaktů

1.  Diagram závislostí, otevřete místní nabídku pro vrstvy a zvolte **zobrazení odkazy**.

     **Vrstvy Průzkumníka** artefaktů odkazy pro vybrané vrstvy.

2.  Ke správě těchto propojení použijte následující úlohy:

|**K**|**V Průzkumníku vrstvy**|
|------------|---------------------------|
|Odstranění propojení mezi vrstvou a artefaktem|Otevřete místní nabídku pro odkaz artefaktů a zvolte **odstranit**.|
|Přesunutí propojení z jedné vrstvy do druhé|Přetáhněte do diagramu propojení artefaktu s existující vrstvou.<br /><br /> - nebo -<br /><br /> 1.  Otevřete místní nabídku pro odkaz artefaktů a zvolte **Vyjmout**.<br />2.  Diagram závislostí, otevřete místní nabídku pro vrstvy a zvolte **vložení**.|
|Kopírování propojení z jedné vrstvy do druhé|1.  Otevřete místní nabídku pro odkaz artefaktů a zvolte **kopie**.<br />2.  Diagram závislostí, otevřete místní nabídku pro vrstvy a zvolte **vložení**.|
|Vytvoření nové vrstvy z existujícího propojení artefaktu|Přetáhněte propojení artefaktu do prázdné oblasti na diagramu.|
|Ověřte, zda propojené artefaktů podporuje ověřování pro diagram závislostí.|Podívejte se na **podporuje ověřování** sloupec pro odkaz artefaktů.|

##  <a name="Discovering"></a> Provádět zpětnou analýzu stávající závislosti
 Závislost existuje všude, kde artefakt, který je spojen s jednou vrstvou, odkazuje na artefakt, který je přidružen k jiné vrstvě. Třída v jedné vrstvě například deklaruje proměnnou, která má třídu v jiné vrstvě. Je možné provádět zpětnou analýzu existujících závislostí pro artefakty, které jsou propojeny s vrstvami v diagramu.

> [!NOTE]
>  Pro určité druhy artefaktů nelze provádět zpětnou analýzu žádných závislostí. Zpětnou analýzou například nebudou získány žádné závislosti z vrstvy nebo do ní, když je propojena s textovým souborem. Pokud chcete zobrazit, jaké artefakty mít závislosti, můžete provádět zpětnou analýzu, otevřete místní nabídku pro jednu nebo více vrstev a zvolte **zobrazení odkazy**. V **vrstvy Explorer**, zkontrolujte **podporuje ověřování** sloupce. Závislosti nebude zpětnou analýzou pro artefakty, pro které tomto sloupci se zobrazuje **False**.

-   Vyberte jednu nebo více vrstev, otevřete místní nabídku pro vybranou vrstvu a pak zvolte **generovat závislosti**.

 Obvykle se zobrazí nějaké závislosti, které by neměly existovat. Tyto závislosti lze upravit, aby odpovídaly zamýšlenému návrhu.

##  <a name="EditDependencies"></a> Upravit vrstvy a závislosti zobrazíte určený návrhu
 Popis změny, které máte v úmyslu provést systému nebo zamýšlené architekturu, upravte diagram závislost:

|**K**|**Proveďte tyto kroky**|
|------------|-----------------------------|
|Změna nebo omezení směru závislosti|Nastavte její **směr** vlastnost.|
|Vytvoření nových závislostí|Použití **závislostí** a **obousměrného závislostí** nástroje.<br /><br /> Chcete-li nakreslit více závislostí, klikněte na nástroj dvakrát. Po dokončení klikněte **ukazatel** nástroj nebo klikněte na tlačítko **ESC** klíč.|
|Zadání toho, aby artefakty spojené s vrstvou nemohly záviset na zadaných oborech názvů|Zadejte obory názvů na vrstvě **zakázáno závislosti Namespace** vlastnost. Použijte středník (**;**) pro samostatné obory názvů.|
|Zadání toho, aby artefakty spojené s vrstvou nesměly patřit zadanému oboru názvů|Zadejte obory názvů na vrstvě **zakázáno obory názvů** vlastnost. Použijte středník (**;**) pro samostatné obory názvů.|
|Zadání toho, aby artefakty spojené s vrstvou musely patřit jednomu ze zadaných oborů názvů|Zadejte obor názvů na vrstvě **požadované obory názvů** vlastnost. Použijte středník (**;**) pro samostatné obory názvů.|

##  <a name="EditLayout"></a> Změnit způsob elementy diagram.
 Velikost, tvar, barvu a polohu vrstev nebo barvu závislostí můžete změnit úpravou jejich vlastností.

##  <a name="Codemaps"></a> Zjistit vzory a závislosti na mapě kódu
 Při vytváření diagramů závislostí, můžete také vytvořit **code mapy**. Tyto diagramy můžete zjistit vzory a závislosti při prozkoumávání kód. Pomocí Průzkumníka řešení, zobrazení tříd nebo prohlížeč objektů a prozkoumejte sestavení, obory názvů a třídy - odpovídajících často i existující vrstvy. Další informace o map kódu najdete v tématu:

-   [Mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md)

-   [Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)

-   [Nalezení potenciálních problémů pomocí analyzátorů mapy kódu](../modeling/find-potential-problems-using-code-map-analyzers.md)

## <a name="see-also"></a>Viz také

- [Video: Ověření svoje závislosti architektury v reálném čase](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)
- [Diagramy závislostí: Referenční dokumentace](../modeling/layer-diagrams-reference.md)
- [Diagramy závislostí: Pokyny](../modeling/layer-diagrams-guidelines.md)
- [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)
- [Vizualizace kódu](../modeling/visualize-code.md)
