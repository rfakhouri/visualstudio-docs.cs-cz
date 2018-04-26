---
title: Jak se definuje jazyk specifický pro doménu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.dsldesigner.domainrelationship
- vs.dsltools.dsldesigner.domainclass
- vs.dsltools.dsldesigner.domaintype
helpviewer_keywords:
- Domain-Specific Language, domain class
- Domain-Specific Language, external types
- Domain-Specific Language, relationships
- Domain-Specific Language, domain properties
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 4aea2750e3900beb0aaa62156c215376ff16d1ea
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-define-a-domain-specific-language"></a>Jak se definuje jazyk specifický pro doménu
Definovat jazyk specifické pro doménu (DSL), řešení sady Visual Studio vytvořit ze šablony. Klíčovou součástí řešení je diagram definice DSL, která je uložena v DslDefinition.dsl. Definice DSL definuje třídy a obrazců DSL. Po úpravě a přidáte k těmto prvkům, můžete přidat kód programu k přizpůsobení DSL podrobněji.

Pokud jste ještě DSL, linky, doporučujeme pracovat prostřednictvím **DSL nástroje Lab**, které můžete najít v této lokalitě: [Visualizaton a modelování SDK](http://go.microsoft.com/fwlink/?LinkID=186128)

##  <a name="templates"></a> Výběr šablony řešení
 Pokud chcete definovat DSL, je třeba nainstalovat následující součásti:

|||
|-|-|
|Visual Studio|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkId=185579)|
|[!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkId=185580)|
|Visual Studio vizualizace a modelování SDK||


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]


 Chcete-li vytvořit nový jazyk specifické pro doménu, vytvořte nové řešení sady Visual Studio pomocí šablony projektu jazyka domény.

#### <a name="to-create-a-dsl-solution"></a>Chcete-li vytvořit řešení DSL

1.  Vytvoření řešení s **jazyka domény** šablony, která najdete v části **ostatní typy/rozšiřitelnost projektů** v **nový projekt** dialogové okno.

     ![Dialogové okno DSL vytvořit](../modeling/media/create_dsldialog.png "Create_DSLDialog")

     Když kliknete na tlačítko **OK**, **specifické pro doménu jazyk průvodce** otevře a zobrazí se seznam šablon DSL řešení.

2.  Klikněte na každé šabloně zobrazíte popis. Vyberte řešení, které nejvíce podobá co chcete vytvořit.

     Každá šablona DSL definuje základní funkční DSL. Upravíte tento DSL podle vlastních požadavků.

     Klikněte na jednotlivé ukázky pro další informace.

    -   Vyberte **toku úkolů** vytvořit DSL, který má plaveckých drah. Plaveckých drah jsou svislé nebo vodorovné oddíly diagramu.

    -   Vyberte **součást modely** vytvořit DSL, která má porty. Porty jsou malé obrazce na okraji větší tvar.

    -   Vyberte **diagramů tříd** k definování DSL, s prostředí tvarů. Tvary prostředí obsahovat seznam položek.

    -   Vyberte **minimální jazyk** v ostatních případech nebo pokud si nejste jisti.

    -   Vyberte **minimální Návrhář WinForm** nebo **minimální WPF Designer** vytvořit DSL, který se zobrazí na plochu Windows Forms nebo WPF. Budete muset napsat kód pro definování editoru. Další informace naleznete v následujících tématech:

         [Vytvoření jazyka specifického pro doménu založeného na modelu Windows Forms](../modeling/creating-a-windows-forms-based-domain-specific-language.md)

         [Vytvoření jazyka specifického pro doménu založeného na WPF](../modeling/creating-a-wpf-based-domain-specific-language.md)

3.  Zadejte příponu názvu souboru pro vaše DSL na stránce příslušné průvodce. Toto je rozšíření, který bude používat soubory obsahující instance vaší DSL.

    -   Zvolte příponu názvu souboru, který není spojen s libovolnou aplikací v počítači nebo v libovolném počítači, kam chcete nainstalovat DSL. Například **docx** a **htm** by mělo nepřijatelný souboru přípon.

    -   Průvodce zobrazí upozornění, pokud rozšíření, které jste zadali, je používán jako DSL. Zvažte použití příponou jiný soubor. Můžete taky resetovat Visual Studio SDK experimentální instance Vyčistit stará experimentální Designer. Klikněte na tlačítko **spustit**, klikněte na tlačítko **všechny programy**, **Microsoft Visual Studio 2010 SDK**, **nástroje**a potom **resetovat Microsoft Visual Studio 2010 experimentální instance**.

4.  Můžete upravit nastavení na jiných stránkách, nebo ponechte výchozí hodnoty.

5.  Klikněte na tlačítko **Dokončit**.

     Průvodce vytvoří řešení, které obsahuje dvě nebo tři projekty a generuje kód z definice DSL.

 Uživatelské rozhraní je nyní podobný na následujícím obrázku.

 ![Návrhář DSL](../modeling/media/dsl_designer.png "dsl_designer")

 Toto řešení definuje konkrétní jazyk domény. Další informace najdete v tématu [přehled nástroje uživatelského rozhraní pro specifické pro doménu jazyk](../modeling/overview-of-the-domain-specific-language-tools-user-interface.md).

### <a name="test-the-solution"></a>Testování řešení
 Šablona řešení poskytuje DSL, kterou můžete upravit nebo použít, protože je funkční.

 Chcete-li otestovat řešení, stiskněte klávesu F5 nebo CTRL + F5. Otevře se v experimentální režimu novou instanci sady Visual Studio.

 V nové instanci sady Visual Studio v Průzkumníku řešení otevřete soubor ukázka. Otevře se jako diagram s sady nástrojů.

 Pokud spuštění řešení, které jste vytvořili z **minimální jazyk** šablony, experimentální sady Visual Studio bude vypadat podobně jako v následujícím příkladu:

 ![](../modeling/media/dsl_min.png "DSL_min")

 Experimentujte s nástroje. Vytvořte elementy a jejich připojení.

 Ukončete experimentální instanci sady Visual Studio.

> [!NOTE]
>  Pokud jste změnili DSL, jste už nebude moci zobrazit tvary se vzorkem testovací soubor. Však bude možné k vytvoření nových elementů.

### <a name="modifying-the-template-dsl"></a>Úprava šablony DSL
 Přejmenovat a udržovat některé nebo všechny domény třídy a třídy obrazce v šabloně DSL definice. Vaše nové třídy názvů musí být platné názvy CLR, bez mezer a interpunkce.

 Je obzvláště užitečná, aby tyto třídy:

-   Kořenová třída se zobrazuje v levé horní DSL definice diagramu, v části **třídy a vztahy**. Přejmenujte jej na název liší od DSL. Například DSL s názvem **MusicLibrary** může mít kořenová třída s názvem **Hudba**.

-   Třída diagramu se zobrazí v pravém dolním rohu diagram DSL definice v **elementy diagramu** sloupce. Možná bude muset se posuňte doprava k jeho zobrazení. Je obvykle název * YourDsl ***Diagram**.

-   Pokud jste použili **toku úkolů** šablony a chcete vytvořit diagramy s plaveckých drah, zachovat a přejmenujte objektu Actor domény třídy a ActorSwimlane tvaru.

 Odstraňte nebo přejmenujte ostatní třídy podle svých potřeb.

##  <a name="patterns"></a> Vzory pro definování DSL
 Doporučujeme, abyste vývoji DSL přidávání nebo úpravě jedno nebo dvě funkce současně. Přidání funkce, spusťte DSL a otestovat ji a poté přidejte jeden nebo dva další funkce. Typické funkce vaší DSL, může být:

-   Třídu domény vnoření vztah, který připojí elementu k modelu, tvaru vyžadována k zobrazení elementy této třídy v diagramu a nástroj element, který umožňuje uživatelům vytvářet prvky.

-   Vlastnosti domény třídu domény a dekorátory, které je zobrazit na obrazce.

-   Referenční vztah a konektor, který se zobrazuje v diagramu a nástroj konektor, který umožňuje uživatelům vytvořit odkazy.

-   Přizpůsobení, které vyžaduje kód programu, například omezení ověření nebo příkazu nabídky.

 Následující části popisují, jak vytvořit velmi užitečné druhy DSL funkce. Existuje mnoho dalších vzorech, pomocí kterých lze sestavit DSL, avšak ty jsou nejčastěji používají.

> [!NOTE]
>  Po přidání funkce, nezapomeňte znovu klikněte na tlačítko **transformaci všech šablon** na panelu nástrojů Průzkumníka řešení před sestavení a spuštění vaší DSL.

 Následující obrázek ukazuje třídy a vztahy část DSL, který slouží jako příklad v tomto tématu.

 ![Vložení a referenční dokumentace vztahy](../modeling/media/music_classes.png "Music_Classes")

 Následující obrázek je příklad model z této DSL:

 ![Instance modelu generovaného DSL](../modeling/media/music_instance.png "Music_Instance")

> [!NOTE]
>  "Model" odkazuje na instanci vaše DSL, vytvoříte uživatele a obvykle se zobrazí jako diagram. Toto téma popisuje diagram DSL definice a modelu diagramy, které se zobrazí při vaší DSL se používá.

##  <a name="classes"></a> Definice tříd domény
 Třídy domény představují koncepty vaší DSL. Instance jsou *modelu elementy*. Například v **MusicLibrary** DSL může mít třídy domény s názvem **Album** a **skladbu**.

 Pro vytvoření třídy domény, můžete přetáhnout z **třída s názvem domény** nástroje k diagramu a přejmenujte třídy.

 Další informace najdete v tématu [vlastnosti domény třídy](../modeling/properties-of-domain-classes.md).

### <a name="create-an-embedding-relationship-for-each-domain-class"></a>Vytvořit vztah vnoření pro každou třídu domény
 Každá třída domény s výjimkou kořenová třída musí být cílem alespoň jeden vnoření relace, nebo musí dědit ze třídy, která je cílem vnoření relace.

 Každý element modelu v modelu, je uzel v jediném stromu vnoření vztahy. Zdrojové a cílové vnoření relace jsou často označovány jako nadřazené a podřízené.

 Výběr nadřazené úlohy pro třídu domény závisí na tom, jak chcete, aby jeho elementy životnosti závislý na další prvky. Pokud uzel stromu odstraněna, jeho podstromu je obvykle také odstraněny. Třídy elementu, které mají nezávislé existence jsou proto vložených přímo pod kořenová třída.

 Obvykle Pokud chcete zobrazovat element uvnitř elementu jiného, budete chtít znamenat relaci vlastníka. V takovém případě nejvhodnější nadřazené třídy je třída kontejneru. Výjimkou je ve skutečnosti jenom použití odkazu na element nezávislé po položce, který se zobrazí uvnitř kontejneru. V takovém případě odstranění kontejneru odstraní odkaz, ale není cíli.

 V vzory DSL definice popsaných v tomto tématu bude předpokládáme, že elementy zobrazí uvnitř kontejneru se odstraní při odstranění kontejneru. Složitější schémata je možné a dosáhnout tak, že definujete pravidla.

|Zobrazení – element|(Vložení) nadřazené třídy|Příklad v šabloně řešení DSL|
|------------------------------|--------------------------------|--------------------------------------|
|Obrazec v diagramu.<br /><br /> Dráha.|Kořenová třída DSL.|Minimální jazyk.<br /><br /> Tok úkolů: Třída objektu Actor.|
|Obrazce v dráha.|Třída domény elementů, které se zobrazují jako plaveckých drah.|Tok úkolů: Třída úlohy.|
|Položka v seznamu ve tvaru, kde je položka odstraněna, když je odstranit kontejner.<br /><br /> Port na okraji tvaru.|Třída domény, která je namapovaná na tvar kontejneru.|Diagram třídy: třídy atributů.<br /><br /> Diagram komponent: Port třídy.|
|Položka v seznamu, nebyl odstraněn, je-li kontejneru odstraněna.|Kořenová třída DSL.<br /><br /> Zobrazí se seznam referenčních odkazů.||
|Ne přímo zobrazí.|Třída, která je součástí.||

 V příkladu knihovna Hudba alb zobrazují jako obdélníky, ve kterých jsou uvedené názvy skladeb. Proto nadřazeného alb je kořenová třída Hudba a nadřazeného skladbu je alb.

 Chcete-li vytvořit třídu domény a jeho vložení ve stejnou dobu, klikněte na tlačítko **vložení vztah** nástroj, pak klikněte na tlačítko nadřazené třídy a potom klikněte na prázdnou část diagramu.

 Není obvykle nutné upravit název vnoření relace a její role, protože bude automaticky sledovat názvy tříd.

 Další informace najdete v tématu [vztahy domén vlastnosti](../modeling/properties-of-domain-relationships.md) a [Vlastnosti rolí domény](../modeling/properties-of-domain-roles.md).

> [!NOTE]
>  Vložení není stejný jako dědičnosti. Podřízené objekty v relaci vnoření nedědí funkce ze svých nadřazených složek.

### <a name="add-domain-properties-to-each-domain-class"></a>Přidat vlastnosti domény pro různé třídy domény
 Vlastnosti domény ukládat hodnoty. Příklady: název, název, datum publikace.

 Klikněte na tlačítko **vlastnosti domény** ve třídě, stiskněte klávesu ENTER a pak zadejte název vlastnosti. Vlastnost domain na výchozí typ je řetězec. Pokud chcete změnit typ, vyberte vlastnost domain a nastavte **typ** v **vlastnosti** okno. Pokud není typ, který chcete v rozevíracím seznamu, přečtěte si téma [přidání typy vlastností](#addTypes).

 **Nastavte vlastnost název elementu.** Vyberte vlastnost domény, který můžete použít k identifikaci elementy v Průzkumníku jazyk. Například ve třídě domény skladbu, můžete třeba vybrat vlastnost název domény. V **vlastnosti** nastavte **název elementu, který je** k `true`.

### <a name="create-derived-domain-classes"></a>Vytvoření domény odvozené třídy
 Pokud chcete třídu domény tak, aby měl varianty, které dědí jeho vlastností a vztahů, vytváření třídy, které jsou odvozeny od jeho. Například Album odvozených od třídy WMA a MP3.

 Vytvořte pomocí odvozené třídy **domény třída** nástroj.

 Klikněte **dědičnosti** nástroje, klikněte odvozené třídy a pak klikněte na základní třídy.

 Zvažte nastavení **dědičnosti modifikátor** základní třídy pro **abstraktní**. Pokud se domníváte, že může být nutné instance základní třídy, zvažte místo vytvoření samostatné odvozené třídy pro ně.

 Odvozené třídy dědí vlastnosti a rolí jejich základní třídy.

### <a name="tidy-the-dsl-definition-diagram"></a>Přehledné Diagram definice DSL
 Když přidáte vztahy, některé třídy se zobrazí na více než jednom místě. Pokud chcete snížit počet vzhled a ujistěte se, diagram širší, klikněte pravým tlačítkem na cílové třídy vztahu a pak klikněte na tlačítko **přineste zde stromu**. Opačný účinek, klikněte pravým tlačítkem na cílové třídy relace a klikněte na tlačítko **rozdělení stromu**. Pokud se tyto příkazy nabídky nezobrazí, ujistěte se, zda je vybrána pouze třídu domény.

 Pomocí kombinace kláves CTRL + ŠIPKA NAHORU a CTRL + ŠIPKA DOLŮ pro přesun domény třídy a třídy tvaru.

### <a name="test-the-domain-classes"></a>Testování třídy domény

##### <a name="to-test-the-new-domain-classes"></a>K testování nových třídách domény

1.  **Klikněte na tlačítko transformaci všech šablon** na panelu nástrojů Průzkumníka řešení pro generování kódu DSL návrháře. Tento krok můžete automatizovat. Další informace najdete v tématu [jak automatizovat transformaci všech šablon](http://msdn.microsoft.com/b63cfe20-fe5e-47cc-9506-59b29bca768a).

2.  **Sestavte a spusťte DSL.** Stisknutím klávesy F5 nebo CTRL + F5 spustí novou instanci sady Visual Studio v režimu experimentální. V experimentální instanci sady Visual Studio otevřete nebo vytvořte soubor, který má příponu názvu souboru z vaší DSL.

3.  **Otevřete Průzkumníka.** Na straně diagramu je okno Průzkumníka jazyk, který je obvykle s názvem *YourLanguage* Explorer. Pokud se toto okno nezobrazí, může to být na kartě pod Průzkumníku řešení. Pokud nemůžete najít, na **zobrazení** nabídky, přejděte na příkaz **ostatní okna**a potom klikněte na *YourLanguage* **Explorer**.

     Aplikace explorer představuje stromové zobrazení modelu.

4.  **Vytvoření nových elementů.** Klikněte pravým tlačítkem na kořenový uzel v horní části a pak klikněte na tlačítko **přidat nové *** YourClass*.

     V jazyce Průzkumníka se zobrazí novou instanci třídy třídě.

5.  Ověřte, že každá instance má jiný název, při vytváření nové instance. Toto se vztahuje pouze v případě, že jste nastavili **název elementu, který je** příznak na vlastnost domain.

6.  **Podívejte se na vlastnosti domény. S instancí třídě vybrána** zkontrolujte okno vlastností. Měl by se zobrazit vlastnosti domény, které jste definovali na této třídě domény.

7.  **Uložení souboru, zavřete je a znovu ho otevřete**. Všechny instance, kterou jste vytvořili by měly jít vidět v Průzkumníku po rozbalte uzly.

##  <a name="shapes"></a> Definování tvarů diagram.
 Můžete definovat třídy elementů, které se zobrazují v diagramu jako obdélníky, symbol tří teček nebo ikon.

#### <a name="to-define-a-class-of-elements-that-appear-as-shapes-on-a-diagram"></a>Chcete-li definovat třídu elementů, které se zobrazují jako obrazce v diagramu

1.  **Definování a testování třídu domény, jak je popsáno v**[definice třídy domény](#classes) **.** 

    -   Kořenová třída by měla být nadřazené třídy. To znamená měla by existovat vnoření relaci mezi kořenová třída a nová třída domény.

    -   Pokud váš obrázek plaveckých drah, může být nadřazené třídě domény, který je namapovaný na dráha. Než budete pokračovat tímto postupem, najdete v části [definování DSL, který má plaveckých drah](#swimlanes).

2.  **Přidání třídy tvar** představují elementy v diagramu modelu. Přetažením z jednoho z následujících nástrojů do definice DSL diagramu:

    -   **Geometrické obrazce** poskytuje obdélníku nebo třemi tečkami.

    -   **Obrázek tvar** zobrazí obrázek, který zadáte.

    -   **Prostoru pro tvar** je obdélníku, která obsahuje jeden nebo více seznam položek.

     Přejmenujte tvar třídy, která se zobrazí na pravé straně diagramu definice DSL, v části tvarů a konektory.

3.  **Zadejte bitovou kopii, pokud jste vytvořili obrazce bitové kopie**.

    1.  Vytvořte soubor image jakékoli velikosti. Podporované jsou formáty BMP, JPEG, GIF a EMF.

    2.  V Průzkumníku řešení soubor přidáte do řešení v části Dsl\Resources.

    3.  Vraťte do diagramu DSL definice a vyberte novou třídu tvar bitové kopie.

    4.  V okně vlastností klikněte **Image** vlastnost.

    5.  V **vyberte bitovou kopii** dialogové okno pole, klikněte na rozevírací nabídku, v části **název souboru**a vyberte bitovou kopii.

4.  **Přidáte dekoratéry text tvaru, chcete-li zobrazit vlastnosti domény.**

     Zobrazit název nebo název prvku modelu, budete pravděpodobně potřebovat alespoň jeden dekoratéra text.

     Klikněte pravým tlačítkem na hlavičku třídy shape, přejděte na **přidat**a potom klikněte na **Text Dekoratéra**. Nastavte název dekoratéra a v sadě okno Vlastnosti jeho **pozice**.

5.  **Připojení každého obrazce s Diagram Element mapu do třídy domény, která by se měl zobrazit**.

     Klikněte na tlačítko **Diagram Element mapy** nástroj, pak klikněte na třídu domény a pak klikněte na třídu tvaru.

6.  **Mapování vlastností k dekoratéry text.**

    1.  Vyberte šedé řádek mezi třídou domény a tvar třídu, která reprezentuje element diagramu.

    2.  V **DSL podrobnosti** okně klikněte na tlačítko **Dekoratéra mapy** kartě. Pokud se nezobrazí **DSL podrobnosti** okno na **zobrazení** nabídky, přejděte na příkaz **ostatní okna** a pak klikněte na **DSL podrobnosti**. Je často nutné vyvolat horní části tohoto okna a zobrazit tak všechny jeho obsah.

    3.  Vyberte název dekoratéra. V části **zobrazit vlastnosti**, vyberte název vlastnosti třídy domény. Tento postup opakujte pro každý dekoratéra.

         Pokud chcete zobrazit vlastnost související elementu, klikněte na rozevírací seznam stromu navigátoru v části **cesta k zobrazení vlastností**.

    4.  Ujistěte se, že spolu s každou dekoratéra název se zobrazí zaškrtnutí.

     ![Mapování tvar a podrobnosti DSL okno](../modeling/media/dsldetailswindow.png "DslDetailsWindow")

7.  **Zkontrolujte položky sady nástrojů pro vytváření elementy třídy domény.**

    1.  V **DSL Explorer**, rozbalte **Editor** uzlu a všech jeho podřízených uzlů.

    2.  Klikněte pravým tlačítkem na uzel v rámci **sada nástrojů karty** který má stejný název jako DSL, například MusicLibrary. Klikněte na tlačítko **přidat nástroj pro Element**.

        > [!NOTE]
        >  Pokud kliknete pravým tlačítkem na **nástroje** uzlu, neuvidíte **přidat nástroj pro Element**. Místo toho klikněte na uzel nad ním.

    3.  V okně vlastností nový vybraný element nástroj nastavit **třída** do třídy domény, který jste nedávno přidali.

    4.  Nastavit **popisek** a **popisek**.

    5.  Nastavit **ikonu panelu nástrojů** na ikonu, která se zobrazí v panelu nástrojů. Můžete ho nastavit na novou ikonu nebo ikonu již používá pro jiný nástroj.

         Chcete-li vytvořit novou ikonu, otevřete Dsl\Resources v **Průzkumníku řešení**. Zkopírujte a vložte jednu z existující soubory BMP nástroj elementu. Přejmenujte vložených kopírování a dvakrát jej upravit.

         Vraťte do diagramu definice DSL, vyberte nástroj a v okně vlastností klikněte na tlačítko **[...]**  v **ikonu panelu nástrojů**. V **vyberte rastrový obrázek** dialogové okno, vyberte vaše. Soubor BMP z rozevírací nabídky.

 Další informace najdete v tématu [vlastnosti geometrické obrazce](../modeling/properties-of-geometry-shapes.md) a [vlastnosti bitové kopie tvarů](../modeling/properties-of-image-shapes.md).

#### <a name="to-test-shapes"></a>K testování tvarů

1.  **Klikněte na tlačítko transformaci všech šablon** na panelu nástrojů Průzkumníka řešení pro generování kódu DSL návrháře.

2.  **Sestavte a spusťte DSL.** Stisknutím klávesy F5 nebo CTRL + F5 spustí novou instanci sady Visual Studio v režimu experimentální. V experimentální instanci sady Visual Studio otevřete nebo vytvořte soubor, který má příponu názvu souboru z vaší DSL.

3.  **Ověřte, že nástroje element zobrazují na panelu nástrojů.**

4.  **Vytvoření tvarů** přetažením z nástroje do diagramu modelu.

5.  **Ověřte, zda každý dekoratéra text se zobrazí,** a že:

    1.  Můžete upravit, pokud jste nastavili **je jen pro čtení uživatelského rozhraní** příznak na vlastnost domain.

    2.  Pokud upravujete vlastnosti buď v okně Vlastnosti nebo dekoratéra, ostatní zobrazení se aktualizuje.

 Po dokončení testu nejprve obrazce, můžete upravit některé jeho vlastnosti a přidejte některé pokročilejší funkce. Další informace najdete v tématu [přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md).

##  <a name="references"></a> Definování relací odkaz
 Můžete definovat referenční vztah mezi všechny zdrojové domény třídy a všechny domény třídu cíle. Referenční relace se obvykle zobrazují v diagramu jako konektory, které jsou řádky mezi tvarů.

 Například pokud Hudba alba a umělci jsou zobrazeny jako obrazce v diagramu, můžete třeba definovat relace s názvem ArtistsAppearedOnAlbums, který odkazuje na alb, na kterých už pracovali umělci. Podívejte se na příklad na obrázku.

 ![Instance modelu generovaného DSL](../modeling/media/music_instance.png "Music_Instance")

 Referenční relace, můžete také propojit elementy stejného typu. Například v DSL, představující stromu rodiny, vztah mezi nadřazené položky a jejich podřízené je referenční vztah osoby z osoby.

### <a name="define-a-reference-relationship"></a>Definování referenční vztah
 Klikněte na nástroj referenční vztah pak klikněte na domény třída zdroje relace a klikněte s třídou cílové domény. Třída cíle může být stejná jako třída zdroje.

 Každý vztah má dvě role, reprezentována řádku na každé straně pole relace. Můžete vybrat jednotlivé role a nastavit jeho vlastnosti v okně Vlastnosti.

 **Vezměte v úvahu přejmenování role**. Například ve vztahu mezi osoby a osoby, můžete změnit výchozí názvy nadřazených složek a podřízených prvků, správce a podřízené, učitele a Student a tak dále.

 **Upravit mnohočetnostmi jednotlivých rolí**, pokud je to nezbytné. Pokud chcete, aby každá osoba mít maximálně jeden Manager, nastavte násobnost, který se zobrazí pod popiskem správce v diagramu na 0..1.

 **Vlastnosti domény přidáte do relace.** Na obrázku má vztah umělcem úrovni alb vlastnost role.

 **Nastavte vlastnost relace, umožňuje duplikuje** Pokud mezi stejného páru prvků modelu může existovat více než jeden odkaz pro stejnou třídu. Například může povolit učitelem naučit více než jeden vztahují stejné Student.

 ![Obrazce mapy pro konektory](../modeling/media/music_connector.png "Music_Connector")

 Další informace najdete v tématu [vztahy domén vlastnosti](../modeling/properties-of-domain-relationships.md) a [Vlastnosti rolí domény](../modeling/properties-of-domain-roles.md).

### <a name="define-a-connector-to-display-the-relationship"></a>Definování konektor zobrazíte relace
 Konektor zobrazí řádek mezi dvě tvary v diagramu modelu.

 Přetáhněte **konektor** nástroj do diagramu DSL definice.

 Pokud chcete zobrazit popisky na konektoru, přidejte text dekorátory. Nastavte jejich pozic. Aby mohl uživatel přesunout text dekoratéra, nastavte jeho **je lze přesunout** vlastnost.

 Použití **Diagram Element mapy** nástroj, který konektor propojit referenční vztah.

 S diagram element mapy vybrána, otevřete **DSL podrobnosti** okna a otevřete **Dekoratéra mapy** kartě.

 Vyberte jednotlivé **Dekoratéra** a nastavte **zobrazit vlastnosti** pro vlastnost správnou doménu.

 Ujistěte se, že se zobrazí zaškrtnutí u jednotlivých položek **Dekoratéry** seznamu.

### <a name="define-a-connection-builder-tool"></a>Definování nástroj Tvůrce připojení
 V **DSL Explorer** okno, rozbalte **Editor** uzel a všechny jeho podřízené uzly.

 Klikněte pravým tlačítkem na uzel, který má stejný název jako vaše DSL a pak klikněte na **přidat nový nástroj pro připojení**.

 Když je vybraný nový nástroj, v okně vlastností:

-   Nastavte **popisek** a **popisek**.

-   Klikněte na tlačítko **připojení Tvůrce** a vyberte příslušné tvůrce pro nový vztah.

-   Nastavit **ikonu panelu nástrojů** na ikonu, která se má zobrazit v panelu nástrojů. Můžete ho nastavit na novou ikonu nebo ikonu již používá pro jiný nástroj.

     Chcete-li vytvořit novou ikonu, otevřete Dsl\Resources v **Průzkumníku řešení**. Zkopírujte a vložte jednu z existující soubory BMP nástroj elementu. Přejmenujte vložených kopírování a dvakrát jej upravit.

     Vraťte do diagramu definice DSL, vyberte nástroj a v okně vlastností klikněte na tlačítko **[...]**  v **ikonu panelu nástrojů**. V **vyberte rastrový obrázek** dialogové okno, vyberte vaše. Soubor BMP z rozevírací nabídky.

##### <a name="to-test-a-reference-relationship-and-connector"></a>K testování referenční vztah a konektor

1.  **Klikněte na tlačítko transformaci všech šablon** na panelu nástrojů Průzkumníka řešení pro generování kódu DSL návrháře.

2.  **Sestavte a spusťte DSL.** Stisknutím klávesy F5 nebo CTRL + F5 spustí novou instanci sady Visual Studio v režimu experimentální. V experimentální instanci sady Visual Studio otevřete nebo vytvořte soubor, který má příponu názvu souboru z vaší DSL.

3.  **Ověřte, že se na panelu nástrojů zobrazí nástroje pro připojení.**

4.  **Vytvoření tvarů** přetažením z nástroje do diagramu modelu.

5.  **Vytvoření připojení** mezi obrazce. Klikněte na nástroj konektor, klikněte na tlačítko obrazce a klikněte na položku jiného obrazce.

6.  **Ověřte, že nelze vytvořit připojení mezi nevhodných třídy.** Například pokud vaše vztah mezi alb a umělci, ověřte, že umělci nemůže propojit s umělci.

7.  **Ověřte, zda mnohočetnostmi jsou správné. Ověřte například, že uživatel nemůže připojit k více než jeden správce.**

8.  **Ověřte, zda každý dekoratéra text se zobrazí,** a že:

    1.  Můžete upravit, pokud jste nastavili **je jen pro čtení uživatelského rozhraní** příznak na vlastnost domain.

    2.  Pokud upravujete vlastnosti buď v okně Vlastnosti nebo dekoratéra, ostatní zobrazení se aktualizuje.

 Po dokončení testu nejprve konektor, můžete upravit některé jeho vlastnosti a přidejte některé pokročilejší funkce. Další informace najdete v tématu [přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md).

##  <a name="compartments"></a> Definování tvarů, které obsahují seznamy: prostoru pro tvarů
 Obrazce prostředí obsahuje jeden nebo více seznam položek. Například v DSL knihovna Hudba, můžete použít prostředí tvarů představují Hudba alb. V každé Album je seznam skladeb.

 ![Prostoru pro tvar](../modeling/media/compartmentshape.png "CompartmentShape")

 V Nejjednodušším způsobem, jak dosažení tímto účelem se v definici DSL definujete jednu třídu domény pro kontejner a jednu třídu domény pro každý seznamu. Kontejner – třída je namapována na tvar prostředí.

 ![Obrazce mapy](../modeling/media/music_mapcomp.png "Music_MapComp")

 Další informace najdete v tématu [vlastnosti prostředí tvarů](../modeling/properties-of-compartment-shapes.md).

#### <a name="to-define-a-compartment-shape"></a>Chcete-li definovat obrazce prostředí

1.  **Vytvořte třídu domény kontejneru**. Klikněte **vložení vztah** nástroje, klikněte na tlačítko kořenová třída modelu a klikněte na prázdnou část diagram definice DSL. Tím se vytvoří třídu domény s názvem Album příklad obrázku.

     Místo vkládání ve třídě, root, případně můžete vložit kontejneru v třídě domény, který je namapovaný na dráha.

     Přidejte do třídy vlastnosti domény, například název a nastavit jeho **název elementu, který je** příznak v okně Vlastnosti.

2.  **Vytvořte třídu domény položky seznamu**. Klikněte **vložení vztah** nástroje, klikněte na možnost kontejner – třída (Album) a potom klikněte na prázdnou část diagramu. Tím se vytvoří třídu domény s názvem skladbu příklad obrázku.

     Přidat vlastnosti domény, například název pro třídu a nastavit jeho **název elementu, který je** příznak.

     Přidejte další vlastnosti domény.

     Přidejte další třídu domény položku seznamu pro každý seznam, který chcete zobrazit.

3.  **Chcete-li kombinovat několik typů položek v seznamu**, vytváření třídy, které dědí z třídy seznamu. Vytvořte abstraktní třídu seznamu nastavením jeho **dědičnosti modifikátor**.

     Například pokud chcete seřadit podle autora místo umělcem klasického Hudba, můžete vytvořit dvě podtřídy skladbu, ClassicalSong a NonClassicalSong.

4.  **Vytvořit prostředí tvaru**. Přetáhněte z **prostředí tvar** nástroj do diagramu DSL definice.

     Přidejte text dekoratéra a nastavte její název.

     Přidejte prostředí a nastavte její název.

5.  Aby mohl uživatel skrýt přihrádky seznamu, klikněte pravým tlačítkem na třídu tvar prostředí, přejděte na **přidat**a potom klikněte na **Rozbalit/sbalit Dekoratéra**. V okně Vlastnosti nastavte pozici dekoratéra.

6.  Klikněte na tlačítko **Diagram Element mapy** nástroje, klikněte na kontejner domény – třída a klikněte na tlačítko tvaru prostředí.

7.  Vyberte odkaz diagram element mapy mezi třídou domény a tvar. V **DSL podrobnosti** okno:

    1.  Klikněte **Dekoratéry** kartě. Klikněte na název dekoratéra a potom vyberte příslušnou položku v části **zobrazení vlastnost**. Ujistěte se, že se zobrazí zaškrtnutí vedle názvu dekoratéra.

    2.  Klikněte na tlačítko **prostředí mapy** kartě.

         Klikněte na název oddílu.

         V části **cestu ke kolekci elementů zobrazené**, přejděte na třída prvku seznam (skladbu). Klikněte na šipku rozevíracího seznamu použití nástroje Navigátor.

         V části **zobrazení vlastnost**, vyberte vlastnosti, která má být zobrazena v seznamu. V příkladu je to název.

> [!NOTE]
>  Pomocí pole cesty v mapě Dekoratéra a prostoru pro mapování polí můžete nastavit složitější vztahy mezi domény třídy a tvar prostředí.

#### <a name="to-define-a-tool-for-creating-the-shape"></a>Chcete-li definovat nástroj pro vytváření tvaru

1.  **Zkontrolujte položky sady nástrojů pro vytváření elementy třídy domény.**

2.  V **DSL Explorer**, rozbalte **Editor** uzlu a všech jeho podřízených uzlů.

3.  Klikněte pravým tlačítkem na uzel v rámci **sada nástrojů karty** který má stejný název jako DSL, například MusicLibrary. Klikněte na tlačítko **přidat nástroj pro Element**.

    > [!NOTE]
    >  Pokud kliknete pravým tlačítkem na **nástroje** uzlu, neuvidíte **přidat nástroj pro Element**. Místo toho klikněte na uzel nad ním.

4.  V okně vlastností nový vybraný element nástroj nastavit **třída** do třídy domény, který jste nedávno přidali.

5.  Nastavit **popisek** a **popisek**.

6.  Nastavit **ikonu panelu nástrojů** na ikonu, která se zobrazí v panelu nástrojů. Můžete ho nastavit na novou ikonu nebo ikonu již používá pro jiný nástroj.

     Chcete-li vytvořit novou ikonu, otevřete Dsl\Resources v **Průzkumníku řešení**. Zkopírujte a vložte jednu z existujících nástrojů element. Soubory BMP. Přejmenujte vložených kopírování a dvakrát jej upravit.

     Vraťte do diagramu definice DSL, vyberte nástroj a v okně vlastností klikněte na tlačítko **[...]**  v **ikonu panelu nástrojů**. V **vyberte rastrový obrázek** dialogu vyberte z rozevírací nabídky souboru BMP.

#### <a name="to-test-a-compartment-shape"></a>Pro testovací prostředí obrazce

1.  **Klikněte na tlačítko transformaci všech šablon** na panelu nástrojů Průzkumníka řešení pro generování kódu DSL návrháře.

2.  **Sestavte a spusťte DSL.** Stisknutím klávesy F5 nebo CTRL + F5 spustí novou instanci sady Visual Studio v režimu experimentální. V experimentální instanci sady Visual Studio otevřete nebo vytvořte soubor, který má příponu názvu souboru z vaší DSL.

3.  **Ověřte, zda nástroj zobrazí na panelu nástrojů.**

4.  Přetáhněte nástroj do diagramu modelu. Vytvoří se obrazce.

     Ověřte, zda se zobrazí název elementu a je automaticky nastaven na výchozí hodnotu.

5.  Klikněte pravým tlačítkem na záhlaví nový tvar a pak klikněte na tlačítko Přidat *si položky seznamu.* Příkaz v příkladu je přidat skladbu.

     Ověřte, že položka je uvedena v seznamu a jeho nový název.

6.  Klikněte na jednu z položky seznamu a potom si prohlédněte okno vlastností. Měli byste vidět vlastnosti položky seznamu.

7.  Otevřete Průzkumníka jazyk. Ověřte, uvidíte kontejner uzly s uzlů položky seznamu v rámci.

 ![Vygenerovaný explorer DSL](../modeling/media/music_explorer.png "Music_Explorer")

 Po dokončení testu nejprve obrazce prostředí, můžete upravit některé jeho vlastnosti a přidejte některé pokročilejší funkce. Další informace najdete v tématu [přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md).

### <a name="displaying-a-reference-link-in-a-compartment"></a>Zobrazení použití odkazu ve prostředí
 Element, který se zobrazí ve prostředí je obvykle podřízený element, který je reprezentována tvaru prostředí. Ale v některých případech se má zobrazit element, který bude propojen s referenční vztah.

 Například může přidáme druhý prostředí k AlbumShape, který zobrazí seznam umělci, které jsou propojeny s alba.

 V takovém případě by měl prostředí zobrazovat odkazu, který je místo je odkazovaný element. Důvodem je, že když uživatel vybere položku v prostoru a stiskem tlačítka odstraňte, chcete odkaz, který má být odstraněn, není je odkazovaný element.

 Nicméně může mít název je odkazovaný element zobrazí v prostoru.

 Následující postup předpokládá, že jste již vytvořili třídy domény, referenční vztah, tvar prostředí a diagram element mapy, jak je popsáno výše v této části.

##### <a name="to-display-a-reference-link-in-a-compartment"></a>Chcete-li zobrazit použití odkazu ve prostředí

1.  **Přidání prostoru do prostoru pro obrazce**. Diagram definice DSL, klikněte pravým tlačítkem na třídu tvar prostředí, přejděte na **přidat**a potom klikněte na **prostředí**.

2.  Nastavit **cestu ke kolekci elementů zobrazené** přejděte na odkaz, namísto jeho cílový element. Klikněte na rozevírací nabídku a pomocí stromové struktury vyberte referenční vztah místo cíli. V tomto příkladu relace je **ArtistAppearedOnAlbums**.

3.  Nastavit **cesta k zobrazení vlastností** přejděte na odkaz na target element. V příkladu je to **umělcem**.

4.  Nastavit **zobrazení vlastnost** na příslušnou vlastnost prvku, třeba **název**.

5.  **Proveďte transformaci všech šablon**, sestavit a spustit DSL a otevřete testovací modelu.

6.  V diagramu modelu vytvořit příslušné třídy tvaru, nastavit jejich názvy a vytvořit propojení mezi nimi. V prostředí tvaru by se zobrazit názvy propojených elementů.

7.  Vyberte odkaz nebo položky ve tvaru prostředí. Odkaz a položka má zmizí.

##  <a name="ports"></a> Definování porty na hranici jiného obrazce
 Port je tvar, který se nachází na hraniční jiného obrazce.

 Porty lze také poskytnout pevné spojovací bod druhého obrazce, ke kterému může uživatel kreslení konektory. V takovém případě můžete nastavit port tvaru transparentní.

 Pokud chcete zobrazit příklad, který používá porty, vyberte **Diagram komponent** šablonu při vytváření nové DSL řešení. Tento příklad znázorňuje hlavní body, které můžete zvážit při definování porty:

-   Je třída domény, která představuje kontejner porty, `Component`.

-   Je třída domény, která představuje porty. V příkladu je to `ComponentPort`.

-   Je vnoření vztah z třídy kontejner domény do domény třída portu. Další informace najdete v tématu [definice třídy domény](#classes).

-   Pokud chcete různé typy portu, která se kombinovat na stejném kontejneru, můžete vytvořit podtřídami třídy domény portu. V příkladu `InPort` a `OutPort` dědí `ComponentPort`.

-   Kontejner – třída domény lze mapovat na jakýkoli druh tvaru. V příkladu je `ComponentShape`. Další informace najdete v tématu [definování tvarů](#shapes).

-   Třídy domény portu jsou namapované na portu tvarů. Můžete buď mapy odvozených třídách k oddělení tříd tvar port nebo mapování základní třída pro třídu tvar jeden port.

 V ostatních ohledech chovat tvarů portu, jak je popsáno v [definování tvarů](#shapes).

 Další informace najdete v tématu [vlastnosti portu tvarů](../modeling/properties-of-port-shapes.md).

##  <a name="swimlanes"></a> Definování DSL, který má plaveckých drah
 Plaveckých drah jsou vodorovné nebo svislé oddílu diagram. Jednotlivé dráhy odpovídá element modelu. Vaše definice DSL vyžaduje jednu třídu domény pro dráha elementy.

 Nejlepší způsob, jak vytvořit DSL s plaveckých drah je vytvořte nové řešení DSL a zvolte šablonu řešení tok úkolů. V definici DSL třídu objektu Actor je třída domény namapované na dráha. Přejmenujte tento a ostatní třídy tak, aby vyhovovala projektu.

 Přidat třídu, která se zobrazí jako obrazce uvnitř dráha, vytvořte vložení vztah mezi třídou dráha a novou třídu. Uživatelé budou moci přetáhněte elementy z jedné dráze, ale každý prvek bude vždy uvnitř konkrétní dráha. V šabloně řešení tok úkolů FlowElement je podřízená dráha třídy.

 Pokud chcete přidat třídu, která se zobrazí jako obrazce nezávisle na plaveckých drah, vytvořte vložení vztah mezi kořenová třída a novou třídu. Uživatelé budou moci tyto obrazce kdekoli v diagramu, včetně napříč hranicemi plaveckých drah a mimo plaveckých drah. V šabloně řešení tok úkolů komentář je podřízená kořenové třídy.

 Další informace najdete v tématu [vlastnosti plaveckých drah](../modeling/properties-of-swimlanes.md).

##  <a name="addTypes"></a> Přidání typů vlastností

### <a name="domain-enumerations-and-literals"></a>Výčty domény a literály
 Výčtu doména je typ literálu hodnotami.

 Přidat výčtu doména, klikněte pravým tlačítkem na kořen modelu v **DSL Explorer** a pak klikněte na **přidat nové výčtu doména**. Element se zobrazí v **DSL Explorer** pod **domény typy** uzlu. Tento prvek se nezobrazí v diagramu.

 Pokud chcete přidat do domény výčtu výčtu literály, klikněte pravým tlačítkem na výčet domény ve **DSL Explorer** a pak klikněte na **přidat nové výčet literálu**.

 Ve výchozím nastavení můžete nastavit vlastnost, která má typ výčtu pouze jedna hodnota výčtu najednou. Pokud chcete uživatelům a programátory mohli nastavit libovolné kombinace hodnot – "bitové pole" – nastavte **IsFlags** vlastnost výčtu.

### <a name="external-types"></a>Externí typy
 Pokud nastavíte typ vlastnosti domény, pokud nelze nalézt typ chcete v **typ** rozevíracího seznamu, můžete přidat na externí typ. Například můžete přidat **System.Drawing.Color** typu do seznamu.

 Přidání typu, klikněte pravým tlačítkem na kořen modelu v Průzkumníku DSL a pak klikněte na tlačítko **přidat nový externí typ**. V okně vlastností nastavte název na **barva** a oboru názvů **System.Drawing**. Tento typ se teď zobrazí v Průzkumníku DSL pod **domény typy**. Můžete jej kdykoliv nastavit typ vlastnosti domény.

##  <a name="custom"></a> Přizpůsobení DSL
 Pomocí technik popsaných v tomto tématu, můžete rychle vytvořit DSL s graficky zápis, čitelné podoby XML a základní nástroje, které jsou požadovány pro generování kódu a další artefaktů.

 Rozšíření definice DSL dvěma způsoby:

1.  DSL upřesnit pomocí více funkcí DSL definice. Například můžete použít nástroj jeden konektor, který můžete vytvořit několik typů konektoru a můžete řídit pravidla odstraněním které jeden element dojde také k odstranění souvisejících elementů. Tyto postupy jsou většinou dosáhnout nastavením hodnoty v definici DSL a některé vyžadovat zadání několika řádků kódu programu.

     Další informace najdete v tématu [přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md).

2.  Rozšíření vaší nástroje pro modelování pomocí kód programu k dosažení pokročilejší účinky. Například můžete vytvořit příkazy nabídky, které můžete změnit model, a můžete vytvořit nástroje, které se integrují DSL, dvě nebo více linky. VMSDK je navrženo konkrétně k snadno integrovat kód, který se vygeneruje z definice DSL rozšíření.  Další informace najdete v tématu [psaní kódu jazyka domény sestavit si](../modeling/writing-code-to-customise-a-domain-specific-language.md).

### <a name="changing-the-dsl-definition"></a>Změna definice DSL
 Když vytvoříte libovolnou položku v definici DSL, mnoho výchozí hodnoty jsou nastaveny automaticky. Po jejich nastavení, můžete je změnit. To usnadňuje vývoj DSL, zároveň umožňuje efektivní přizpůsobení.

 Například když je obrazce mapovat na element, nadřazená cesta Element mapování je automaticky nastavena podle vnoření relace třídy domény. Ale pokud později změníte vnoření relace, nadřazená cesta element není změnit automaticky.

 Proto byste měli být vědět, že při změně některých vztahy v definici vaší DSL, není pro zaslání chyby při uložení definice nebo při transformaci všech šablon. Většina tyto chyby jsou snadno opravit. Dvakrát klikněte na zprávu o chybách zobrazíte umístění chyby.

 Viz také [postupy: Změna Namespace jazyka specifické pro doménu](../modeling/how-to-change-the-namespace-of-a-domain-specific-language.md).

##  <a name="trouble"></a> Řešení potíží
 V následující tabulce jsou uvedeny některé nejčastější problémy, které jsou došlo při návrhu DSL, společně s návrhy pro jejich řešení. Další Rady, jak je k dispozici na [vizualizace nástroje Extensibililty fórum](http://go.microsoft.com/fwlink/?LinkId=186074).

|Problém|Návrh|
|-------------|----------------|
|Změny, které mají provedené v souboru definice DSL nemají žádný vliv.|Klikněte na tlačítko **transformaci všech šablon** na panelu nástrojů nad Průzkumníku řešení a pak znovu sestavit řešení.|
|Tvary zobrazit název dekoratéra místo hodnoty vlastnosti.|Nastavte mapování dekoratéra. Na diagramu definice DSL klikněte na element mapy diagram, což je šedé řádek mezi domény třídy a třídy tvaru.<br /><br /> Otevřete **DSL podrobnosti** okno. Pokud nevidíte, v nabídce zobrazení, přejděte na **ostatní okna**a potom klikněte na **DSL podrobnosti**.<br /><br /> Klikněte **Dekoratéra mapy** kartě. Vyberte název dekoratéra. Ujistěte se, že je zaškrtnuté políčko vedle sebe. V části **zobrazit vlastnosti**, vyberte název vlastnosti domény.<br /><br /> Další informace najdete v tématu [tvarů diagram](#shapes).|
|V Průzkumníku DSL nelze přidat do kolekce. Například při kliknutí pravým tlačítkem myši nástroje, neexistuje žádný příkaz "Přidat Tool" v nabídce.<br /><br /> V Průzkumníku pro moje DSL nelze přidat element do seznamu.|Klikněte pravým tlačítkem na položku výše uzlu, který se pokoušíte. Pokud chcete přidat do seznamu, je příkaz přidat, není v uzlu seznamu, ale jeho vlastníka.|
|Po vytvoření třídy domény, ale nelze vytvořit instance v Průzkumníku jazyk.|Každá třída domény s výjimkou kořenové musí být cílem vnoření relace.|
|V Průzkumníku pro moje DSL elementy jsou zobrazeny pouze s jejich názvy typů.|V definici DSL, vyberte vlastnost domain třídy a ve vlastnostech okno, nastavte **název elementu, který je** na hodnotu true.|
|Moje DSL se vždy otevře v editoru XML.|K tomu dochází z důvodu chyby při při čtení souboru. Ale i poté, co můžete vyřešit tuto chybu, musíte explicitně nastavit editoru být vašeho DSL návrháře.<br /><br /> Klikněte pravým tlačítkem na položku projektu, klikněte na tlačítko **otevřít v** a vyberte * YourLanguage ***návrháře (výchozí)**.|
|Sady nástrojů Moje DSL nezobrazí po změně názvy sestavení.|Zkontrolovat a aktualizovat **DslPackage\GeneratedCode\Package.tt** Další informace najdete v tématu [postupy: Změna Namespace jazyka specifické pro doménu](../modeling/how-to-change-the-namespace-of-a-domain-specific-language.md).|
|Sady nástrojů Moje DSL nezobrazí, ale I nedošlo ke změně názvu sestavení.<br /><br /> Nebo, zobrazí se okno se zprávou, reporting selhání načtení rozšíření.|Resetovat experimentální instanci a znovu sestavte řešení.<br /><br /> 1.  V systému Windows nabídky Start, v části **všechny programy**, rozbalte položku [!INCLUDE[vssdk_current_long](../misc/includes/vssdk_current_long_md.md)], pak **nástroje**a potom klikněte na **resetovat Visual Studio experimentální instanci Microsoft**.<br />2.  V sadě Visual Studio**sestavení** nabídky, klikněte na tlačítko **znovu sestavit řešení**.|

## <a name="see-also"></a>Viz také

- [Začínáme s jazyky specifickými pro doménu](../modeling/getting-started-with-domain-specific-languages.md)
- [Vytvoření jazyka specifického pro doménu založeného na modelu Windows Forms](../modeling/creating-a-windows-forms-based-domain-specific-language.md)
- [Vytvoření jazyka specifického pro doménu založeného na WPF](../modeling/creating-a-wpf-based-domain-specific-language.md)