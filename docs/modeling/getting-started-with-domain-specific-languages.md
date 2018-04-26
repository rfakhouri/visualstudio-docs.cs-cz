---
title: Začínáme s jazyky specifickými pro doménu
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 61fdb4b652b7fe74f3baf80c6e9d6332914a9a1e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="getting-started-with-domain-specific-languages"></a>Začínáme s jazyky specifickými pro doménu
Toto téma vysvětluje základní koncepce při definování a používání jazyka specifické pro doménu (DSL) vytvořené pomocí sady SDK modelování pro sadu Visual Studio.

> [!NOTE]
> V 2017 Visual Studio sada SDK Text šablony transformaci a Visual Studio SDK modelování instalují automaticky při instalaci konkrétní funkce sady Visual Studio. Další podrobnosti najdete v tématu [tomto příspěvku na blogu](https://blogs.msdn.microsoft.com/visualstudioalm/2016/12/12/the-visual-studio-modeling-sdk-is-now-available-with-visual-studio-2017/).

Pokud jste ještě DSL, linky, doporučujeme pracovat prostřednictvím **DSL nástroje Lab**, které můžete najít v této lokalitě: [Visualizaton a modelování SDK](http://go.microsoft.com/fwlink/?LinkID=186128)

## <a name="what-can-you-do-with-a-domain-specific-language"></a>Co se děje s jazyka domény?
 Jazyka domény je notaci, obvykle grafického rozhraní, který je určen k použití pro určitý účel. Jazyků, například UML jsou naopak pro obecné účely. V DSL můžete definovat typy element modelu a jejich vztahů a jak se mají zobrazovat na obrazovce.

 Když navrženy DSL, můžete distribuovat jako součást balíčku rozšíření integrace aplikace Visual Studio (VSIX). Uživatelé pracovat s DSL v sadě Visual Studio:

 ![Rodina stromového diagramu, nástrojů a explorer](../modeling/media/familyt_instance.png "FamilyT_Instance")

 Notace je jenom část DSL. Společně s zápis vašeho balíčku VSIX obsahuje nástroje, které uživatelé mohou nainstalovat na jejich upravit a vytvoření materiálu z jejich modelů.

 Jedním z hlavní aplikace DSL, linky je pro generování kódu programu, konfigurační soubory a jiné artefakty. Zejména v rozsáhlých projektů a řady produktů, které vytvoří několik variant produktu, generování mnoho aspektů proměnné z DSL, linky nabízejí velký nárůst v spolehlivost a velmi rychle reagovat na požadavky na změny.

 Zbytek tento přehled je návod, který představuje základní operace vytváření a používání jazyka domény v sadě Visual Studio.

## <a name="prerequisites"></a>Požadavky
 Pokud chcete definovat DSL, je třeba nainstalovat následující součásti:

|||
|-|-|
|Visual Studio|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkId=185579)|
|[!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkId=185580)|
|Modelování SDK pro Visual Studio||


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]


## <a name="creating-a-dsl-solution"></a>Vytvořením DSL řešení
 Pokud chcete vytvořit nový jazyk specifické pro doménu, vytvořte nové řešení sady Visual Studio pomocí šablony projektu jazyka domény.

#### <a name="to-create-a-dsl-solution"></a>Chcete-li vytvořit řešení DSL

1.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**.

2.  V části **typy projektů**, rozbalte **jiné typy projektů** uzel a klikněte na tlačítko **rozšiřitelnost**.

3.  Klikněte na tlačítko **Návrhář jazyka domény**.

     ![Dialogové okno DSL vytvořit](../modeling/media/create_dsldialog.png "Create_DSLDialog")

4.  V **název** zadejte **FamilyTree**. Click **OK**.

     **Specifické pro doménu jazyk průvodce** otevře a zobrazí seznam řešení DSL šablony.

     Klikněte na každé šabloně zobrazíte popis

     Šablony jsou užitečné počáteční body. Každý z nich poskytuje kompletní funkční DSL, který můžete upravit podle svých potřeb. By normálně, zvolte šablonu nejbližší co chcete vytvořit.

5.  V tomto návodu, vyberte **minimální jazyk** šablony.

6.  Zadejte příponu názvu souboru pro vaše DSL na stránce příslušné průvodce. Toto je rozšíření, který bude používat soubory obsahující instance vaší DSL.

    -   Zvolte rozšíření, který není spojen s libovolnou aplikací v počítači nebo v libovolném počítači, kam chcete nainstalovat DSL. Například **docx** a **htm** by mělo nepřijatelný souboru přípon.

    -   Průvodce zobrazí upozornění, pokud rozšíření, které jste zadali, je používán jako DSL. Zvažte použití příponou jiný soubor. Můžete taky resetovat Visual Studio SDK experimentální instance Vyčistit stará experimentální Designer. Klikněte na tlačítko **spustit**, klikněte na tlačítko **všechny programy**, **Microsoft Visual Studio 2010 SDK**, **nástroje**a potom **resetovat Microsoft Visual Studio 2010 experimentální instance**.

7.  Zkontrolujte dalších stránek a pak klikněte na tlačítko **Dokončit**.

     Generuje se řešení, která obsahuje dva projekty. Že jsou pojmenované Dsl a DslPackage. Soubor diagramu otevře tedy s názvem DslDefinition.dsl.

    > [!NOTE]
    >  Většinu kódu, který se zobrazí ve složkách v dva projekty se generují z DslDefinition.dsl. Z tohoto důvodu většina k vaší DSL změn v tomto souboru.

 Uživatelské rozhraní je nyní podobný na následujícím obrázku.

 ![Návrhář DSL](../modeling/media/dsl_designer.png "dsl_designer")

 Toto řešení definuje konkrétní jazyk domény. Další informace najdete v tématu [přehled nástroje uživatelského rozhraní pro specifické pro doménu jazyk](../modeling/overview-of-the-domain-specific-language-tools-user-interface.md).

## <a name="the-important-parts-of-the-dsl-solution"></a>Důležitou součástí řešení DSL
 Všimněte si následujících charakteristik ve nové řešení.

-   **Dsl\DslDefinition.DSL** Toto je soubor najdete, když vytvoříte DSL řešení. Téměř všechny kód v řešení se z tohoto souboru, a většinu změn, které provedete definici DSL jsou zde provedena. Další informace najdete v tématu práci s [práce s Diagram definice DSL](../modeling/working-with-the-dsl-definition-diagram.md).

-   **Projekt DSL** tento projekt obsahuje kód, který definuje jazyk specifické pro doménu.

-   **Projekt DslPackage** tento projekt obsahuje kód, který umožňuje instancí DSL otevřít a upravovat v sadě Visual Studio.

##  <a name="Debugging"></a> Spuštění DSL
 Řešení DSL můžete spustit ihned po jeho vytvoření. Později můžete upravit definici DSL postupně, spuštění řešení znovu po každé změně.

#### <a name="to-experiment-with-the-dsl"></a>A experimentovat s DSL

1.  Klikněte na tlačítko **transformaci všech šablon** na panelu nástrojů v Průzkumníku řešení. To regeneruje většinu zdrojového kódu z DslDefinition.dsl.

    > [!NOTE]
    >  Vždy, když změníte DslDefinition.dsl, musíte kliknout na **transformaci všech šablon** předtím, než znovu sestavte řešení. Tento krok můžete automatizovat. Další informace najdete v tématu [jak automatizovat transformaci všech šablon](http://msdn.microsoft.com/b63cfe20-fe5e-47cc-9506-59b29bca768a).

2.  Stisknutím klávesy F5, nebo na **ladění** nabídky, klikněte na tlačítko **spustit ladění**.

     DSL sestavení a je nainstalován v experimentální instanci sady Visual Studio.

     Spustí experimentální instanci sady Visual Studio. Experimentální instanci trvá jeho nastavení ze samostatné podstrom registru, které jsou registrované rozšíření Visual Studia pro účely ladění. Normální instance sady Visual Studio nemají přístup k rozšíření registrovaná existuje.

3.  V experimentální instanci sady Visual Studio otevřete soubor modelu s názvem **Test** z **Průzkumníku řešení**.

     \- nebo –

     Klikněte pravým tlačítkem na projekt ladění, přejděte na **přidat**a potom klikněte na **položky**. V **přidat položku** dialogové okno, vyberte typ souboru vaše DSL.

     Jako prázdný diagram otevření souboru modelu.

     V panelu nástrojů se zobrazí nástroje, které jsou vhodné pro typ diagramu.

4.  Pomocí nástrojů pro vytvoření tvarů a konektory v diagramu.

    1.  Chcete-li vytvořit tvarů, přetáhněte z nástroje příklad tvar do diagramu.

    2.  Připojení dvě tvarů, klikněte na nástroj příklad konektor, klikněte na první z nich a klepněte na tlačítko druhého obrazce.

5.  Klikněte na tlačítko popisky tvarů je změnit.

 Experimentální sady Visual Studio bude vypadat podobně jako v následujícím příkladu:

 ![](../modeling/media/dsl_min.png "DSL_min")

### <a name="the-content-of-a-model"></a>Obsah modelu
 Obsah souboru, který je instancí DSL nazývá *modelu*. Model obsahuje *modelu ** elementy* a *odkazy* mezi elementy. Definice DSL Určuje, jaké typy prvků modelu a odkazy může existovat v modelu. Například v DSL, vytvořené z šablony minimální jazyk, je jeden typ prvku modelu a jeden typ odkazu.

 Definice DSL můžete určit, jak se zobrazí v diagramu modelu. Můžete z mnoha různých styly tvarů a konektory. Můžete určit, že některé obrazce se zobrazí uvnitř ostatním tvarům.

 Můžete zobrazit modelu jako strom v **Explorer** zobrazit během úprav modelu. Při přidávání obrazců do diagramu, se zobrazí také v Průzkumníku elementů modelu. Průzkumníku lze použít, i když není k dispozici žádný diagram.

 Pokud nevidíte v Průzkumníku v ladění instanci sady Visual Studio **zobrazení** nabídce přejděte na příkaz **ostatní okna**a potom klikněte na  *\<si jazyk >* **Explorer**.

### <a name="the-api-of-your-dsl"></a>Rozhraní API vašeho DSL
 Vaše DSL generuje rozhraní API, které umožňuje číst a aktualizovat modely, které jsou instancemi třídy DSL. Jedna aplikace rozhraní API je ke generování textových souborů z modelu. Další informace najdete v tématu [vytvoření kódu v době návrhu pomocí textových šablon T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md).

 V ladění řešení otevřete šablonu soubory s příponou ".tt". Tyto ukázky ukazují, jak můžete vygenerovat text z modelů a umožňují test rozhraní API vašeho DSL. Jednou z ukázek je napsána v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], jiné v [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)].

 V každé šabloně soubor je soubor, který generuje. Rozbalte soubor šablony v Průzkumníku řešení a otevřete generovaný soubor.

 Soubor šablony obsahuje krátký segment kódu, který obsahuje všechny prvky v modelu.

 Vygenerovaný soubor obsahuje výsledek.

 Když změníte soubor modelu, zobrazí se odpovídající změny v generované soubory po vygenerování soubory.

##### <a name="to-regenerate-text-files-after-you-change-the-model-file"></a>Po změně souboru modelu vygenerovat textové soubory

1.  V experimentální instanci sady Visual Studio uložte soubor modelu.

2.  Ujistěte se, že parametr názvu souboru do každého souboru .tt odkazuje na soubor modelu, který používáte pro experimenty. Uložte soubor .tt.

3.  Klikněte na tlačítko **transformaci všech šablon** na panelu nástrojů **Průzkumníku řešení**.

     \- nebo –

     Klikněte pravým tlačítkem na šablony, které chcete obnovit a pak klikněte na tlačítko **spustit nástroj pro vlastní**.

 Můžete přidat libovolný počet textové šablony soubory do projektu. Každá šablona generuje jeden soubor s výsledky.

> [!NOTE]
>  Když změníte definici DSL, ukázkový text šablony kód nebude fungovat, pokud ho aktualizujete.

 Další informace najdete v tématu [generování kódu z jazyka domény](../modeling/generating-code-from-a-domain-specific-language.md) a [psaní kódu jazyka domény sestavit si](../modeling/writing-code-to-customise-a-domain-specific-language.md).

## <a name="customizing-the-dsl"></a>Přizpůsobení DSL
 Pokud chcete upravit definici DSL, ukončete experimentální instanci a aktualizovat definice v hlavní instance Visual Studio.

> [!NOTE]
>  Po úpravě definice DSL může dojít ke ztrátě informací v modelů testů, které jste vytvořili pomocí starší verze.  Například ladění řešení obsahuje souboru, který je pojmenován vzorku, který obsahuje některé tvarů a konektory. Po spuštění k vývoji vaší definice DSL, nebudou viditelné a budou ztraceny při ukládání souboru.

 Můžete provést širokou škálu rozšíření vaší DSL. Následující příklady vám poskytne dojem možností.

 Po každé změně, Uložit definici DSL, klikněte na tlačítko **transformaci všech šablon** v **Průzkumníku řešení**a potom stiskněte klávesu **F5** a experimentovat s změněné DSL.

### <a name="rename-the-types-and-tools"></a>Přejmenujte typy a nástroje
 Přejmenujte existující třídy domény a vztahy. Například od Dsl definice vytvořené z šablony minimální jazyk, je může provést následující operace přejmenování, aby DSL představují stromy rodiny.

##### <a name="to-rename-domain-classes-relationships-and-tools"></a>Přejmenování domény třídy, vztahy a nástroje

1.  V diagramu DslDefinition přejmenovat **ExampleModel** k **FamilyTreeModel**, **ExampleElement** k **osoba**,  **Cíle** k **nadřazené položky**, a **zdroje** k **podřízené objekty**. Můžete kliknout na každý popisek ho změnit.

     ![Diagram DSL definice &#45; rodiny stromu modelu](../modeling/media/familyt_person.png "FamilyT_Person")

2.  Přejmenování elementu a konektor nástroje.

    1.  Otevřete okno Průzkumníka DSL kliknutím na kartu v Průzkumníku řešení. Pokud nevidíte, na **zobrazení** nabídce přejděte na příkaz **ostatní okna** a pak klikněte na **DSL Explorer**. DSL Explorer je viditelná jenom v případě, že diagram DSL definice je aktivní okno.

    2.  Otevřete okno Vlastnosti a umístěte ho tak, aby se zobrazí DSL Průzkumníka a vlastnosti ve stejnou dobu.

    3.  V Průzkumníku DSL rozbalte **Editor**, **sada nástrojů karty**,  *\<vaše DSL >* a potom **nástroje**.

    4.  Klikněte na tlačítko **ExampleElement**. Toto je položka panelu nástrojů, který se používá k vytváření prvků.

    5.  V okně vlastností změňte **název** vlastnost **osoba**.

         Všimněte si, že **popisek** také změny vlastností.

    6.  Stejným způsobem, změňte název **ExampleConnector** nástroj k **ParentLink**. Příkaz ALTER **popisek** vlastnost, aby není kopii vlastnost Name. Zadejte například **nadřazený odkaz**.

3.  Znovu sestavte DSL.

    1.  Uložte soubor definice DSL.

    2.  Klikněte na tlačítko **transformaci všech šablon** na panelu nástrojů Průzkumníku řešení

    3.  Stiskněte klávesu F5. Počkejte, až se zobrazí experimentální instanci sady Visual Studio.

4.  V ladění řešení v experimentální instanci sady Visual Studio otevřete soubor modelu testu. Přetažením elementů na ji z panelu nástrojů. Všimněte si, že nástroj titulky a názvy typů v Průzkumníku DSL změnily.

5.  Uložte soubor modelu.

6.  Otevřete soubor .tt a nahraďte výskyty starý typ a vlastnost názvy nové názvy.

7.  Ujistěte se, že Určuje název souboru, který je zadaný v souboru .tt testovací modelu.

8.  Uložte soubor .tt. Otevřete generovaný soubor zobrazíte výsledek spuštění kódu v souboru .tt. Ověřte, zda je správný.

### <a name="add-domain-properties-to-classes"></a>Přidání vlastnosti domény do třídy
 Přidání vlastnosti do třídy domény, například k reprezentaci let narození a smrti osoby.

 Chcete-li nové vlastnosti viditelné v diagramu, musíte přidat *dekoratéry* na obrazec, který zobrazí element modelu. Musíte také mapovat vlastnosti dekorátory.

##### <a name="to-add-properties-and-display-them"></a>K přidání vlastností a jejich zobrazení

1.  Přidáte vlastnosti.

    1.  V definici DSL diagramu, klikněte pravým tlačítkem myši **osoba** třídy domény, přejděte na příkaz **přidat**a potom klikněte na **vlastnost Domain**.

    2.  Zadejte seznam nové názvy vlastností, například **narození** a **smrti**. Stiskněte klávesu **Enter** po každé z nich.

2.  Přidejte dekoratéry, které se zobrazí vlastnosti ve tvaru.

    1.  Postupujte podle šedou čáru, která od třídy osoba domény na druhou stranu diagramu. Toto je diagram elementu mapy. Třída domény odkazuje na třídu tvaru.

    2.  Klikněte pravým tlačítkem na tuto třídu tvaru, přejděte na **přidat**a potom klikněte na **Text Dekoratéra**.

    3.  Přidejte dva dekoratéry s názvy, například **BirthDecorator** a **DeathDecorator**.

    4.  Vyberte každý nový dekoratéra a v okně vlastností nastavte **pozice** pole. Určuje, kde bude zobrazovat hodnota vlastnosti domény na tvaru. Například nastavit **InnerBottomLeft** a **InnerBottomRight**.

         ![Prostoru pro definice na tvar](../modeling/media/familyt_compartment.png "FamilyT_Compartment")

3.  Mapovat dekoratéry vlastnosti.

    1.  Otevřete okno DSL podrobnosti. Na kartě vedle ve výstupním okně je obvykle. Pokud nevidíte, na **zobrazení** nabídky, přejděte na příkaz **ostatní okna**a potom klikněte na **DSL podrobnosti**.

    2.  Diagram definice DSL, klikněte na řádek, který se připojuje **osoba** třída domény k třídě tvaru.

    3.  V **DSL podrobnosti**na **Dekoratéra mapy** kartě, klikněte na zaškrtávací políčko na nenamapovaný dekoratéra. V **zobrazení vlastnost**, vyberte vlastnost domény, ke které má být ji namapovat. Například mapování **BirthDecorator** k **narození**.

4.  Uložit DSL, klikněte na tlačítko transformaci všech šablon a stisknutím klávesy F5.

5.  V diagramu modelu ukázka ověřte, zda lze nyní klikněte na umístění, které jste zvolili a zadejte hodnoty do nich. Kromě toho, když vyberete **osoba** tvaru, v okně Vlastnosti zobrazí nové vlastnosti narození a smrti.

6.  V souboru .tt můžete přidat kód, který získá vlastnosti každá osoba.

 ![Rodina stromového diagramu, nástrojů a explorer](../modeling/media/familyt_instance.png "FamilyT_Instance")

### <a name="define-new-classes"></a>Definovat nové třídy
 Třídy domény a vztahy můžete přidat k modelu. Můžete například vytvořit novou třídu k reprezentaci městech a nový vztah k reprezentaci, že uživatel žít ve městě.

 Chcete-li různé typy odlišné v diagramu modelu, můžete namapovat třídy domény různé druhy tvar nebo obrazců pomocí různých geometrie a barvy.

##### <a name="to-add-and-display-a-new-domain-class"></a>Přidat a zobrazit novou třídu domény

1.  Přidání třídy domény a nastavit jej jako podřízená kořenové modelu.

    1.  V definici DSL diagramu, klikněte na tlačítko **vložení vztah** nástroje, klikněte na tlačítko kořenová třída **FamilyTreeModel**a potom klikněte na prázdnou část diagramu.

         Novou třídu domény se zobrazí, která je připojena k FamilyTreeModel s vnoření vztah.

         Nastavit jeho název, například **městě**.

        > [!NOTE]
        >  Každá třída domény s výjimkou kořenové modelu musí být cílem alespoň jeden vnoření relace, nebo musí dědit ze třídy, která je cílem vložení. Z tohoto důvodu je často vhodné pro vytvoření třídy domény pomocí nástroje vložení vztah.

    2.  Přidání vlastnosti domény pro novou třídu, například **název**.

2.  Referenční vztah mezi osobou a městě přidáte.

    1.  Klikněte **referenční vztah** nástroje, klikněte na tlačítko osoby a pak klikněte na města.

         ![Fragment definice DSL: kořen stromu rodiny](../modeling/media/familyt_root.png "FamilyT_Root")

        > [!NOTE]
        >  Referenční relace představují křížové odkazy z jedné části stromu modelu do jiného.

3.  Přidejte obrazce představují městech v diagramech modelu.

    1.  Přetáhněte **geometrické obrazce** z nástrojů pro diagram a přejmenujte ji, například **TownShape**.

    2.  V okně Vlastnosti nastavte vzhled pole nový tvar, jako je například barva výplně a Geometry.

    3.  Přidejte Dekoratéra, zobrazí se název města a přejmenujte ji NameDecorator. Nastavte vlastnost pozici.

4.  Mapovat TownShape třídě městě domény.

    1.  Klikněte na tlačítko **Diagram Element mapy** nástroje a potom klikněte na třídu městě domény a třídu TownShape tvaru.

    2.  V **Dekoratéra mapy** kartě **DSL podrobnosti** vybrané okno s konektorem mapování, zkontrolujte NameDecorator a nastavte **zobrazení vlastnost** název.

5.  Vytvořte konektor k zobrazení vztah mezi osoby a městech.

    1.  Přetáhněte konektor z panelu nástrojů pro diagram. Přejmenujte ji a nastavte vlastnosti vzhledu.

    2.  Použití **Diagram Element mapy** nástroj pro nový konektor propojit vztah mezi osoby a města.

         ![Definice rodiny stromu s přidané obrazce mapy](../modeling/media/familyt_shapemap.png "FamilyT_ShapeMap")

6.  Vytvořte nástroj pro vytváření nové městě na element.

    1.  V **DSL Explorer**, rozbalte položku **Editor** pak **sada nástrojů karty**.

    2.  Klikněte pravým tlačítkem na  *\<vaše DSL >* a pak klikněte na **přidejte nový Element nástroj**.

    3.  Nastavit **název** vlastnost nového nástroje a nastavte jeho **třída** vlastnost města.

    4.  Nastavte **ikonu panelu nástrojů** vlastnost. Klikněte na tlačítko **[...]**  a v **název souboru** pole, vyberte soubor ikony.

7.  Vytvořte konektor nástroj pro vytváření propojení mezi městech a osoby.

    1.  Klikněte pravým tlačítkem na  *\<vaše DSL >* a pak klikněte na **přidat nový nástroj konektor**.

    2.  Nastaví vlastnost název nového nástroje.

    3.  V **ConnectionBuilder** vlastnosti, vyberte tvůrce, který obsahuje název města osoba relace.

    4.  Nastavte **ikonu panelu nástrojů**.

8.  Uložit definici DSL, klikněte na tlačítko **transformaci všech šablon**a potom stiskněte klávesu **F5**.

9. V experimentální instanci sady Visual Studio otevřete soubor modelu testu. Použijte nové nástroje k vytvoření městech a odkazů mezi městech a osoby. Všimněte si, že můžete vytvořit pouze propojení mezi správné typy elementu.

10. Vytvořte kód, který uvádí města, ve kterém je každá osoba umístěn. Textové šablony jsou jedno z míst, kde můžete spouštět takový kód. Například může upravit existující soubor Sample.tt v řešení pro ladění, tak, aby obsahoval následující kód:

    ```
    <#@ template inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" debug="true" #>
    <#@ output extension=".txt" #>
    <#@ FamilyTree processor="FamilyTreeDirectiveProcessor" requires="fileName='Sample.ftree'" #>

    <#
      foreach (Person person in this.FamilyTreeModel.People)
      {
    #>
        <#= person.Name #><#if (person.Town != null) {#> of <#= person.Town.Name #> <#}#>

    <#
          foreach (Person child in person.Children)
      {
    #>
                <#= child.Name #>
    <#
      }
      }
    #>

    ```

     Při ukládání souboru *.tt vytvoří jiné soubor, který obsahuje seznam osoby a jejich objekty. Další informace najdete v tématu [generování kódu z jazyka domény](../modeling/generating-code-from-a-domain-specific-language.md).

## <a name="validation-and-commands"></a>Ověření a příkazy
 Tato další DSL může vyvíjet přidáním omezení ověřování. Tato omezení jsou metody, které můžete definovat, které se ujistěte, že model je ve správném stavu. Například můžete definovat omezení a ujistěte se, datum narození dítěte je novější než jejích nadřazených tříd. Funkce ověřování zobrazí upozornění, pokud uživatel DSL pokusí uložit model, který dělí žádné omezení. Další informace najdete v tématu [ověření v jazyce specifické pro doménu](../modeling/validation-in-a-domain-specific-language.md).

 Můžete také definovat příkazy nabídky, které může uživatel vyvolat. Příkazy můžete upravit modelu. Takže může také komunikovat s jinými modely v sadě Visual Studio a externím prostředkům. Další informace najdete v tématu [postupy: Úprava standardních příkazů nabídky](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md).

## <a name="deploying-the-dsl"></a>Nasazení DSL
 Povolit jiných uživatelů použití jazyka specifické pro doménu, distribuujete soubor rozšíření Visual Studio (VSIX). Tím se vytvoří při sestavování řešení DSL.

 Vyhledejte soubor VSIX do složky bin vašeho řešení. Zkopírujte jej do počítače, na kterém chcete nainstalovat. Na tomto počítači poklikejte na soubor VSIX. DSL lze ve všech instancích sady Visual Studio na tomto počítači.

 Stejný postup slouží k instalaci DSL ve vašem počítači, takže nemusíte používat experimentální instanci sady Visual Studio.

 Další informace najdete v tématu [nasazení řešení jazyk specifické pro doménu](../modeling/deploying-domain-specific-language-solutions.md).

##  <a name="Reset"></a> Odebrání starého experimentální DSL, linky
 Pokud jste vytvořili experimentální DSL, které již nechcete linky, můžete je odebrat z počítače resetováním Visual Studio experimentální instanci.

 Tato akce odebere z počítače všechny experimentální DSL, linky a další experimentální rozšíření sady Visual Studio. Jedná se o rozšíření, které byly provedeny v režimu ladění.

 Tento postup neodebere DSL, linky nebo jiné rozšíření sady Visual Studio, které byly nainstalovány plně spuštěním souboru VSIX.

#### <a name="to-reset-the-visual-studio-experimental-instance"></a>Chcete-li obnovit Visual Studio experimentální instanci

1.  Klikněte na tlačítko **spustit**, klikněte na tlačítko **všechny programy**, **Microsoft Visual Studio 2010 SDK**, **nástroje**a potom **resetovat Microsoft Visual Studio 2010 experimentální instance**.

2.  Znovu vytvořit všechny experimentální DSL, linky nebo jiných experimentální rozšíření sady Visual Studio, které chcete použít.

## <a name="see-also"></a>Viz také

- [Porozumění modelům, třídám a vztahům](../modeling/understanding-models-classes-and-relationships.md)
- [Jak se definuje jazyk specifický pro doménu](../modeling/how-to-define-a-domain-specific-language.md)