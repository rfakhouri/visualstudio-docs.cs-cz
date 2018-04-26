---
title: Přizpůsobení okna Vlastnosti
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, Properties window
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 7020d3f49d5a693d2b64891c089138be4c073115
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="customizing-the-properties-window"></a>Přizpůsobení okna Vlastnosti
Vzhled a chování okna vlastností můžete přizpůsobit v jazyce specifické pro doménu (DSL) v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. V definici vaší DSL definovat vlastnosti domény na každou třídu domény. Ve výchozím nastavení když vyberete instance třídy v diagramu nebo v Průzkumníku modelu je každý vlastnost domain uvedené v okně Vlastnosti. To vám umožní zobrazit a upravit hodnoty vlastnosti domény, i v případě, že nebyly je namapovaný na polí obrazce v diagramu.

## <a name="names-descriptions-and-categories"></a>Kategorie, názvy a popisy
 **Název a zobrazovaný název**. V definici vaší domény vlastnosti zobrazovaný název vlastnosti je název, který se zobrazí za běhu v okně Vlastnosti. Naopak název se používá při psaní kódu programu aktualizace vlastnosti. Název musí mít správný název alfanumerické CLR, ale zobrazovaný název může obsahovat mezery.

 Když nastavíte název vlastnosti v definici DSL, jeho název zobrazení se automaticky nastaví na kopii název. Pokud píšete Pascal cased název, například "FuelGauge", zobrazovaný název bude automaticky obsahovat mezeru: "Paliva měřidlo". Ale zobrazovaný název explicitně nastavená na jinou hodnotu.

 **Popis**. Popis vlastnosti domény se zobrazí na dvou místech:

-   V dolní části okna vlastností, když uživatel vybere vlastnost. Můžete ho můžete uživatele vysvětlit, co představuje vlastnost.

-   V kódu generovaného programu. Pokud používáte zařízení dokumentace k extrakci dokumentaci k rozhraní API, zobrazí se jako popis této vlastnosti v rozhraní API.

 **Kategorie**. Kategorie je záhlaví v okně Vlastnosti.

## <a name="exposing-style-features"></a>Vystavení styl funkce
 Některé z dynamických funkcí grafické prvky může být reprezentován nebo *zveřejněné* jako vlastnosti domény. Funkce, která vystavila tímto způsobem můžete aktualizovat uživatele a další snadno aktualizovat kód programu.

 Klikněte pravým tlačítkem na třídu obrazce v definici DSL, přejděte na **přidat zveřejněné**a potom vyberte funkce.

 Na tvary můžete vystavit **FillColor**, **OutlineColor**, **TextColor**, **OutlineDashStyle**,  **OutlineThickness** a **FillGradientMode** vlastnosti. Na konektory můžete vystavit **barva**`,`**TextColor**, **DashStyle**, a **tloušťka** vlastnosti. V diagramech můžete vystavit **FillColor** a **TextColor** vlastnosti.

## <a name="forwarding-displaying-properties-of-related-elements"></a>Předávání: Zobrazení vlastností souvisejících elementů
 Když uživatel vaší DSL vybere element v modelu, zobrazí se v okně vlastností daný element vlastnosti. Můžete však také zobrazit vlastnosti zadaných souvisejících elementů. To je užitečné, pokud jste definovali skupiny elementy, které vzájemně spolupracují. Například můžete třeba definovat main element a element volitelné modulu plug-in. Pokud je hlavním prvkem namapovaná na obrazce a dalších není, je užitečné k zobrazení všech jejich vlastnosti, jako kdyby byly na jeden element.

 Tento efekt jmenuje *vlastnost předávání*, a dojde automaticky v několika případech. V ostatních případech můžete dosáhnout vlastnost předávání definováním popisovač typu domény.

### <a name="default-property-forwarding-cases"></a>Výchozí vlastnost předávání případů
 Když uživatel vybere obrazce nebo konektor nebo element v Průzkumníku, následující vlastnosti se zobrazí v okně vlastností:

-   Vlastnosti domény, které jsou definovány na třídě domény elementu modelu, včetně těch, které jsou definovány v základní třídy. Výjimkou je vlastnosti domény, pro které jste nastavili **je Procházet** k `False`.

-   Názvy elementů, které jsou propojeny prostřednictvím relací, které mají násobnost 0..1. To poskytuje pohodlnou metodu volitelně zobrazuje propojené elementy, i v případě, že není definována mapování konektor pro daný vztah.

-   Vlastnosti domény vnoření vztah, který cílí element. Protože vnoření relace nejsou obvykle zobrazují explicitně, to umožňuje uživateli najdete v části jejich vlastnosti.

-   Vlastnosti domény, které jsou definovány na vybrané tvar nebo konektor.

### <a name="adding-property-forwarding"></a>Přidání vlastnosti předávání
 Předávání vlastnost, definujete popisovač typu domény. Pokud máte domény vztah mezi dvě třídy domény, můžete nastavit vlastnost domain první třídy na hodnotu pro vlastnost domain ve třídě druhé doméně popisovač typu domény. Například, pokud máte vztah mezi **kniha** třída domény a **Autor** třídy domény, můžete použít popisovač typu domény aby **název** vlastnost Knihy **Autor** zobrazí v okně Vlastnosti, když uživatel vybere knihy.

> [!NOTE]
>  Vlastnost předávání ovlivňuje pouze okno Vlastnosti, když uživatel upravuje modelu. K třídě přijímající nedefinuje vlastnost domain. Pokud chcete získat přístup k vlastnosti přesměrovaná domény v dalších částech tohoto definici DSL nebo v programovém kódu, je nutné získat přístup element předávání.

 Následující postup předpokládá, že jste vytvořili DSL. První několika kroky shrnují požadavky.

##### <a name="to-forward-a-property-from-another-element"></a>Předávání vlastnost z jiný element

1.  Vytvoření [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] řešení, které obsahuje minimálně dvě třídy, které v tomto příkladu se nazývají **kniha** a **Autor**. Měla by existovat vztahu buď druhu mezi **kniha** a **Autor**.

     Násobnosti atributu role zdroj (role v **kniha** straně) by měla být 0..1 nebo 1..1, že každý **kniha** má jeden **Autor**.

2.  V **DSL Explorer**, klikněte pravým tlačítkem myši **kniha** třídy domény a pak klikněte na tlačítko **přidat nové DomainTypeDescriptor**.

     Uzel s názvem **cesty popisovače vlastnosti vlastní** se zobrazí pod **popisovač typu vlastní** uzlu.

3.  Klikněte pravým tlačítkem myši **popisovač typu vlastní** uzel a pak klikněte na tlačítko **přidat nové PropertyPath**.

     Nové vlastnosti cesty se zobrazí pod **cesty popisovače vlastnosti vlastní** uzlu.

4.  Vyberte novou vlastnost cestu a v **vlastnosti** nastavte **cesta k vlastnosti** k cestě element odpovídající modelu.

     Kliknutím na šipku napravo od této vlastnosti můžete upravit cestu ve stromovém zobrazení. Další informace o cestách domény najdete v tématu [syntaxe cesty domény](../modeling/domain-path-syntax.md). Když upravíte ji, by měla vypadat přibližně cesta **BookReferencesAuthor.Author/! Autor**.

5.  Nastavit **vlastnost** k **název** vlastnost domény **Autor**.

6.  Nastavit **zobrazovaný název** k **vytvářet název**.

7.  Proveďte transformaci všech šablon, sestavit a spustit DSL.

8.  V diagramu modelu vytvořit seznam, autor a propojíte je pomocí referenční vztah. Vyberte požadovaný prvek seznamu a v okně Vlastnosti se měla zobrazit jméno autora také k vlastnostem tohoto seznamu. Změňte jméno autora propojené, nebo odkaz knihy různých autorovi a pozorovat, že se změní jméno autora knihy.

## <a name="custom-property-editors"></a>Editory vlastní vlastnosti
 V okně Vlastnosti poskytuje příslušné výchozí editační rozhraní pro typ každé vlastnosti domény. Například pro výčtový typ, uživateli se zobrazí rozevírací seznam a pro číselnou vlastnost může uživatel zadat číslic. To platí jenom pro předdefinované typy. Pokud zadáte na externí typ, bude uživatel moci prohlédnout vlastnosti hodnoty, ale nikoli pro úpravy.

 Můžete však zadat následující editory a typy:

1.  Jiný editor, který se používá s typem standardní. Můžete například zadat cestu editor souborů pro vlastnosti string.

2.  Na externí typ pro vlastnost domain a editor pro ni.

3.  Rozhraní .NET editoru, například do editoru cesta k souboru, nebo můžete vytvořit vlastní vlastní vlastnost editor.

     Převod mezi na externí typ a typ například řetězce, který má výchozí editor.

 V DSL *externí typ* není žádný typ, který není jedním z jednoduché typy (například logická hodnota nebo Int32) nebo řetězec.

#### <a name="to-define-a-domain-property-that-has-an-external-type"></a>Definovat vlastnost domény, který má na externí typ

1.  V **Průzkumníku řešení**, přidejte odkaz na sestavení (DLL), které obsahuje typ externí v **Dsl** projektu.

     Sestavení může být sestavení .NET, nebo vám poskytl sestavení.

2.  Přidejte typ, který má **domény typy** seznam, pokud jste tak již neučinili.

    1.  Otevřete DslDefinition.dsl a v **DSL Explorer**, klikněte pravým tlačítkem na kořenový uzel a pak klikněte na tlačítko **přidat nový externí typ**.

         Nový záznam se zobrazí pod **domény typy** uzlu.

        > [!WARNING]
        >  Položky nabídky není na kořenový uzel DSL **domény typy** uzlu.

    2.  V okně vlastností nastavte název a obor názvů nového typu.

3.  Přidání vlastnosti domény do domény třídu obvyklým způsobem.

     V okně vlastností vyberte v rozevíracím seznamu v externí typ **typ** pole.

 V této fázi se uživatelé můžou zobrazovat hodnoty vlastnosti, ale nelze upravit. Zobrazené hodnoty jsou získány z `ToString()` funkce. Můžete napsat kód programu, které nastavuje hodnotu vlastnosti, například v příkazu nebo pravidlo.

### <a name="setting-a-property-editor"></a>Nastavení vlastností editoru
 Přidání atributu CLR pro vlastnost domain, v následující podobě:

```
[System.ComponentModel.Editor (
   typeof(AnEditor),
   typeof(System.Drawing.Design.UITypeEditor))]

```

 Atribut lze nastavit u vlastnosti pomocí **vlastní atribut** položku v okně Vlastnosti.

 Typ `AnEditor` musí být odvozen od typu zadanému v druhý parametr. Druhý parametr musí být buď <xref:System.Drawing.Design.UITypeEditor> nebo <xref:System.ComponentModel.ComponentEditor>. Další informace naleznete v tématu <xref:System.ComponentModel.EditorAttribute>.

 Můžete zadat vlastní editoru nebo editoru zadaný v [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], jako například <xref:System.Windows.Forms.Design.FileNameEditor> nebo <xref:System.Drawing.Design.ImageEditor>. Například použijte následující postup vlastnosti, ve kterém může uživatel zadat název souboru.

##### <a name="to-define-a-file-name-domain-property"></a>Chcete-li definovat domény vlastnost název souboru

1.  Přidání vlastnosti domény do domény třídu v vaší DSL definice.

2.  Vyberte novou vlastnost. V **vlastní atribut** pole v okně vlastností, zadejte následující atribut. Chcete-li zadat Tento atribut, klikněte na tlačítko se třemi tečkami **[...]**  a pak zadejte název atributu a parametry samostatně:

    ```
    [System.ComponentModel.Editor (
       typeof(System.Windows.Forms.Design.FileNameEditor)
       , typeof(System.Drawing.Design.UITypeEditor))]

    ```

3.  Ponechat typ vlastnosti domény v jeho výchozí nastavení **řetězec**.

4.  Chcete-li otestovat editoru, ověřte, aby uživatelé mohli otevřít editor název souboru chcete upravit vlastnost vaší domény.

    1.  Stisknutím kombinace kláves CTRL + F5 nebo F5. V řešení pro ladění otevřete soubor testu. Vytvořte prvek třídy domény a vyberte jej.

    2.  V okně Vlastnosti vyberte vlastnost domain. Hodnota pole ukazuje tři tečky **[...]** .

    3.  Klikněte na tlačítko se třemi tečkami. Zobrazí se dialogové okno souboru. Vyberte soubor a zavřete dialogové okno. Cesta k souboru je nyní hodnotu vlastnosti domény.

### <a name="defining-your-own-property-editor"></a>Definování vlastní editor vlastností
 Můžete definovat vlastní editor. To umožňuje uživateli upravit typ, který jste definovali nebo upravit standardní typ zvláštním způsobem by provést. Například může povolit uživatelům vstupní řetězec, který představuje vzorec.

 Můžete definovat editoru vytvořením třídy, která je odvozena z <xref:System.Drawing.Design.UITypeEditor>. Třídě musí přepsat:

-   <xref:System.Drawing.Design.UITypeEditor.EditValue%2A>, komunikovat s uživatelem a aktualizujte hodnotu vlastnosti.

-   <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A>, k určení, jestli bude vaše editoru otevřete dialogové okno nebo zadejte rozevírací nabídce.

 Můžete zadat také grafické reprezentace hodnotu vlastnosti, která se zobrazí v tabulce vlastností. Chcete-li to provést, přepište `GetPaintValueSupported`, a `PaintValue`.  Další informace naleznete v tématu <xref:System.Drawing.Design.UITypeEditor>.

> [!NOTE]
>  Přidejte kód v samostatném souboru kódu v **Dsl** projektu.

 Příklad:

```
internal class TextFileNameEditor : System.Windows.Forms.Design.FileNameEditor
{
  protected override void InitializeDialog(System.Windows.Forms.OpenFileDialog openFileDialog)
  {
    base.InitializeDialog(openFileDialog);
    openFileDialog.Filter = "Text files(*.txt)|*.txt|All files (*.*)|*.*";
    openFileDialog.Title = "Select a text file";
  }
}

```

 Použití tohoto editoru, nastavte **vlastní atribut** vlastnosti domény do:

```
[System.ComponentModel.Editor (
   typeof(MyNamespace.TextFileNameEditor)
   , typeof(System.Drawing.Design.UITypeEditor))]

```

 Další informace naleznete v tématu <xref:System.Drawing.Design.UITypeEditor>.

## <a name="providing-a-drop-down-list-of-values"></a>Poskytnutí rozevírací seznam hodnot
 Můžete zadat seznam hodnot pro uživatele lze vybírat.

> [!NOTE]
>  Tento postup poskytuje seznam hodnot, které můžete změnit za běhu. Pokud chcete poskytovat seznam, který se nemění, místo toho zvažte použití Výčtový typ jako typ vlastnosti vaší domény.

 Chcete-li definovat seznam standardních hodnot, přidejte do vaší domény vlastnost CLR atribut, který má následující formát:

```
[System.ComponentModel.TypeConverter
(typeof(MyTypeConverter))]

```

 Definice třídy, která je odvozena z <xref:System.ComponentModel.TypeConverter>. Přidejte kód v samostatném souboru v **Dsl** projektu. Příklad:

```csharp
/// <summary>
/// Type converter that provides a list of values
/// to be displayed in the property grid.
/// </summary>
/// <remarks>This type converter returns a list
/// of the names of all "ExampleElements" in the
/// current store.</remarks>
public class MyTypeConverter : System.ComponentModel.TypeConverter
{
  /// <summary>
  /// Return true to indicate that we return a list of values to choose from
  /// </summary>
  /// <param name="context"></param>
  public override bool GetStandardValuesSupported
    (System.ComponentModel.ITypeDescriptorContext context)
  {
    return true;
  }

  /// <summary>
  /// Returns true to indicate that the user has
  /// to select a value from the list
  /// </summary>
  /// <param name="context"></param>
  /// <returns>If we returned false, the user would
  /// be able to either select a value from
  /// the list or type in a value that is not in the list.</returns>
  public override bool GetStandardValuesExclusive
      (System.ComponentModel.ITypeDescriptorContext context)
  {
    return true;
  }

  /// <summary>
  /// Return a list of the values to display in the grid
  /// </summary>
  /// <param name="context"></param>
  /// <returns>A list of values the user can choose from</returns>
  public override StandardValuesCollection GetStandardValues
      (System.ComponentModel.ITypeDescriptorContext context)
  {
    // Try to get a store from the current context
    // "context.Instance"  returns the element(s) that
    // are currently selected i.e. whose values are being
    // shown in the property grid.
    // Note that the user could have selected multiple objects,
    // in which case context.Instance will be an array.
    Store store = GetStore(context.Instance);

    List<string> values = new List<string>();

    if (store != null)
    {
      values.AddRange(store.ElementDirectory
        .FindElements<ExampleElement>()
        .Select<ExampleElement, string>(e =>
      {
        return e.Name;
      }));
    }
    return new StandardValuesCollection(values);
  }

  /// <summary>
  /// Attempts to get to a store from the currently selected object(s)
  /// in the property grid.
  /// </summary>
  private Store GetStore(object gridSelection)
  {
    // We assume that "instance" will either be a single model element, or
    // an array of model elements (if multiple items are selected).

    ModelElement currentElement = null;

    object[] objects = gridSelection as object[];
    if (objects != null && objects.Length > 0)
    {
      currentElement = objects[0] as ModelElement;
    }
    else
    {
        currentElement = gridSelection as ModelElement;
    }

    return (currentElement == null) ? null : currentElement.Store;
  }

}

```

## <a name="see-also"></a>Viz také

- [Navigace v modelu a aktualizace modelu v kódu programu](../modeling/navigating-and-updating-a-model-in-program-code.md)