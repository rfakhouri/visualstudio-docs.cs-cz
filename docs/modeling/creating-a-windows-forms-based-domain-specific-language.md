---
title: Vytvoření doménově specifického jazyka založeného na Windows Forms
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 2e031a87093a765c7ca79f929b6fe5666c322aad
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="creating-a-windows-forms-based-domain-specific-language"></a>Vytvoření doménově specifického jazyka založeného na Windows Forms
Windows Forms můžete použít k zobrazení stavu modelu jazyka domény (DSL), místo použití DSL diagram. Toto téma vás provede procesem vytvoření vazby formuláře Windows DSL, pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vizualizace a modelování SDK.

 ![DSL&#45;Wpf&#45;2](../modeling/media/dsl-wpf-2.png "DSL-Wpf-2") A DSL instance, zobrazující uživatelské rozhraní Windows formuláře a Průzkumníka modelu.

## <a name="creating-a-windows-forms-dsl"></a>Vytvoření Windows Forms DSL
 **Minimální Návrhář WinForm** DSL šablona vytváří minimální DSL, který můžete upravit podle vlastních potřeb.

#### <a name="to-create-a-minimal-winforms-dsl"></a>Chcete-li vytvořit minimální WinForms DSL

1.  Vytvoření DSL z **minimální Návrhář WinForm** šablony.

     V tomto názorném postupu se předpokládá, že tyto názvy:

    |||
    |-|-|
    |Název řešení a DSL|FarmApp|
    |Obor názvů|Company.FarmApp|

2.  Experimentujte s počáteční příklad, který poskytuje šablony:

    1.  Proveďte transformaci všech šablon.

    2.  Sestavení a spuštění vzorového (**CTRL + F5**).

    3.  V experimentální instanci sady Visual Studio, otevřete `Sample` v ladění projektu.

         Všimněte si, že se zobrazí v ovládacím prvku Windows Forms.

         Můžete také vidět prvky zobrazí v Průzkumníku modelu.

         Přidejte některé prvky buď ve formátu nebo Průzkumníka a Všimněte si, že se zobrazí na další.

 Hlavní instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], Všimněte si následujících bodů DSL řešení:

-   `DslDefinition.dsl` neobsahuje žádné elementy diagramu. Je to proto nebude DSL diagramy slouží k zobrazení instance modely tento DSL. Místo toho vytvoří vazbu formuláře Windows k modelu a prvky na formuláři se zobrazí modelu.

-   Kromě `Dsl` a `DslPackage` projekty, řešení obsahuje třetí projektu s názvem `UI.` **uživatelského rozhraní** projekt obsahuje definici ovládacího prvku Windows Forms. `DslPackage` závisí na `UI`, a `UI` závisí na `Dsl`.

-   V `DslPackage` projektu `UI\DocView.cs` obsahuje kód, který zobrazí ovládacího prvku Windows Forms, který je definován v `UI` projektu.

-   `UI` Projekt obsahuje pracovní vzorek ovládacího prvku formuláře vázán DSL. Však nebude fungovat, pokud jste změnili definici DSL. `UI` Projekt obsahuje:

    -   Windows Forms třídy s názvem `ModelViewControl`.

    -   Soubor s názvem `DataBinding.cs` obsahující další částečnou definici z `ModelViewControl`. Chcete-li zobrazit jeho obsah v **Průzkumníku řešení**, otevřete místní nabídku pro soubor a vyberte možnost **kód zobrazení**.

### <a name="about-the-ui-project"></a>O projektu uživatelského rozhraní
 Při aktualizaci souboru definice DSL k definování vlastní DSL, budete muset aktualizovat ovládacího prvku `UI` projektu zobrazit vaše DSL. Na rozdíl od `Dsl` a `DslPackage` projekty, ukázky `UI` projektu Binder negeneruje z `DslDefinitionl.dsl`. Můžete přidat soubory .tt ke generování kódu, pokud chcete, i když, který není zahrnutý v tomto návodu.

## <a name="updating-the-dsl-definition"></a>Aktualizaci definice DSL
 Následující definice DSL se používá v tomto návodu.

 ![DSL&#45;Wpf&#45;1](../modeling/media/dsl-wpf-1.png "DSL-Wpf-1")

#### <a name="to-update-the-dsl-definition"></a>Chcete-li aktualizovat definici DSL

1.  Otevřete DslDefinition.dsl v Návrháři DSL.

2.  Odstranit **ExampleElement**

3.  Přejmenujte **ExampleModel** domény třídy `Farm`.

     Poskytněte vlastnosti další domény s názvem `Size` typu **Int32**, a `IsOrganic` typu **Boolean**.

    > [!NOTE]
    >  Pokud odstraníte třídu kořenové domény a pak vytvořte nové kořenové, budete muset resetovat vlastnost Editor kořenová třída. V **DSL Explorer**, vyberte **Editor**. V okně Vlastnosti nastavte **kořenová třída** k `Farm`.

4.  Použití **třída s názvem domény** nástroj k vytváření tříd následující domény:

    -   `Field` -Zadejte to o další domény vlastnost s názvem `Size`.

    -   `Animal` – V okně Vlastnosti nastavte **dědičnosti modifikátor** k **abstraktní**.

5.  Použití **domény třída** nástroj vytvořit následující třídy:

    -   `Sheep`

    -   `Goat`

6.  Použití **dědičnosti** nástroj ke `Goat` a `Sheep` dědí `Animal`.

7.  Použití **vkládání objektů** nástroj pro vložení `Field` a `Animal` pod `Farm`.

8.  Můžete chtít přehledné diagramu. Pokud chcete snížit počet elementy s duplicitním, použijte **přineste zde podstrom** příkaz v místní nabídce elementů typu list.

9. **Proveďte transformaci všech šablon** na panelu nástrojů Průzkumníka řešení.

10. Sestavení **Dsl** projektu.

    > [!NOTE]
    >  V této fázi nebudou ostatní projekty sestavení bez chyb. Chceme sestavení projektu Dsl tak, aby je k dispozici pro Průvodce zdrojem dat sestavení.

## <a name="updating-the-ui-project"></a>Aktualizace uživatelského rozhraní projektu
 Nyní můžete vytvořit nový uživatelský ovládací prvek, který se zobrazí informace, které je uložen v modelu DSL. Nejjednodušší způsob, jak připojit uživatelského ovládacího prvku do modelu je prostřednictvím vazby na data. Datové vazby typ adaptéru s názvem **ModelingBindingSource** je určená speciálně pro připojení k rozhraní jiný VMSDK DSL, linky.

#### <a name="to-define-your-dsl-model-as-a-data-source"></a>Chcete-li definovat modelu DSL jako zdroj dat

1.  Na **Data** nabídce zvolte **zobrazit zdroje dat**.

     **Zdroje dat** otevře se okno.

     Zvolte **přidat nový zdroj dat**. **Průvodce konfigurací zdroje dat** otevře.

2.  Zvolte **objekt**, **Další**.

     Rozbalte položku **Dsl**, **Company.FarmApp**a vyberte **farmy**, což je kořenová třída modelu. Zvolte **Dokončit**.

     V Průzkumníku řešení klikněte **uživatelského rozhraní** projekt nyní obsahuje **Properties\DataSources\Farm.datasource**

     V okně zdroje dat se zobrazí vlastnosti a vztahy vaší třídy modelu.

     ![DslWpf&#45;3](../modeling/media/dslwpf-3.png "DslWpf-3")

#### <a name="to-connect-your-model-to-a-form"></a>Pro připojení k formuláři modelu

1.  V **uživatelského rozhraní** projektu, odstraňte všechny existující soubory .cs.

2.  Přidejte nový **uživatelský ovládací prvek** soubor s názvem `FarmControl` k **uživatelského rozhraní** projektu.

3.  V **zdroje dat** okno, v rozevírací nabídce na **farmy**, zvolte **podrobnosti**.

     Ponechejte výchozí nastavení pro ostatní vlastnosti.

4.  Otevřete FarmControl.cs v zobrazení návrhu.

     Přetáhněte **farmy** z okna zdrojů dat na FarmControl.

     Sadu ovládacích prvků se zobrazí, jeden pro každou vlastnost. Vlastnosti vztahu negenerují ovládací prvky.

5.  Odstranit **farmBindingNavigator**. To je také automaticky generovány v `FarmControl` designer, ale není vhodný pro tuto aplikaci.

6.  Pomocí sady nástrojů, vytvořte dvě instance **DataGridView**a název je `AnimalGridView` a `FieldGridView`.

    > [!NOTE]
    >  Alternativní krok je přetáhnout položky zvířat a pole z okna zdroje dat do ovládacího prvku. Tato akce automaticky vytvoří datové mřížky a vazeb mezi zobrazení mřížky a zdroj dat. Však tato vazba nefunguje správně pro DSL, linky. Proto je lepší vytvořit datové mřížky a vazeb ručně.

7.  Pokud sada nástrojů neobsahuje **ModelingBindingSource** nástroj, přidejte ji. V místní nabídce **Data** , zvolte **zvolit položky**. V **výběr položek sady nástrojů** dialogovém okně, vyberte **ModelingBindingSource** z **rozhraní .NET Framework karta**.

8.  Pomocí sady nástrojů, vytvořte dvě instance **ModelingBindingSource**a název je `AnimalBinding` a `FieldBinding`.

9. Nastavte **DataSource** vlastnost jednotlivých **ModelingBindingSource** k **farmBindingSource**.

     Nastavte **DataMember** vlastnost **zvířat** nebo **pole**.

10. Nastavte **DataSource** vlastnosti `AnimalGridView` k `AnimalBinding`a `FieldGridView` k `FieldBinding`.

11. Upraví rozložení ovládacího prvku farmy na vaše chuť.

 **ModelingBindingSource** je adaptér, který provede několik funkcí, které jsou specifické pro DSL, linky:

-   Aktualizace se zabalí v transakci VMSDK úložiště.

     Například když uživatel odstraní řádek z mřížku zobrazení dat, regulární vazba by způsobilo výjimka transakce.

-   Zajišťuje, že když uživatel vybere řádek, zobrazí okno Vlastnosti vlastnosti odpovídající element model, místo řádku dat mřížky.

 ![DslWpf4](../modeling/media/dslwpf4.png "DslWpf4") schématu odkazů mezi zdroje dat a zobrazení.

#### <a name="to-complete-the-bindings-to-the-dsl"></a>K dokončení vazby na DSL

1.  Přidejte následující kód v samostatném souboru kódu v **uživatelského rozhraní** projektu:

    ```csharp
    using System.ComponentModel;
    using Microsoft.VisualStudio.Modeling;
    using Microsoft.VisualStudio.Modeling.Design;

    namespace Company.FarmApp
    {
      partial class FarmControl
      {
        public IContainer Components { get { return components; } }

        /// <summary>Binds the WinForms data source to the DSL model.
        /// </summary>
        /// <param name="nodelRoot">The root element of the model.</param>
        public void DataBind(ModelElement modelRoot)
        {
          WinFormsDataBindingHelper.PreInitializeDataSources(this);
          this.farmBindingSource.DataSource = modelRoot;
          WinFormsDataBindingHelper.InitializeDataSources(this);
        }
      }
    }
    ```

2.  V **DslPackage** projektu, upravit **DslPackage\DocView.tt** aktualizace definicí následující proměnné:

    ```csharp
    string viewControlTypeName = "FarmControl";
    ```

## <a name="testing-the-dsl"></a>Testování DSL
 Řešení DSL teď můžete sestavit a spustit, i když můžete chtít přidat vylepšení další později.

#### <a name="to-test-the-dsl"></a>K testování DSL

1.  Sestavení a spuštění řešení.

2.  V experimentální instanci sady Visual Studio, otevřete **ukázka** souboru.

3.  V **FarmApp Explorer**, otevřete v místní nabídce **farmy** kořenový uzel a vyberte **přidat nové koz**.

     `Goat1` Zobrazí se v **zvířat** zobrazení.

    > [!WARNING]
    >  Je nutné použít místní nabídky na **farmy** uzlu není **zvířat** uzlu.

4.  Vyberte **farmy** kořenový uzel a zobrazte její vlastnosti.

     Ve formě zobrazení změnit **název** nebo **velikost** farmy.

     Když přejdete mimo každé pole ve formuláři, odpovídající vlastnost změny v okně Vlastnosti.

## <a name="enhancing-the-dsl"></a>Rozšíření DSL

#### <a name="to-make-the-properties-update-immediately"></a>Chcete-li vlastnosti aktualizovat okamžitě

1.  V okně návrhu FarmControl.cs vyberte jednoduché pole, jako je například název, velikost nebo IsOrganic.

2.  V okně vlastností rozbalte **datové vazby** a otevřete **(rozšířené)**.

     V **formátování a rozšířené vazby** dialogové okno, v části **režim aktualizace zdroje dat**, zvolte **OnPropertyChanged –**.

3.  Sestavení a spuštění řešení.

     Ověřte, že když změníte obsah pole odpovídající vlastnost okamžitě změny modelu farmy.

#### <a name="to-provide-add-buttons"></a>K poskytování tlačítka pro přidání

1.  V okně návrhu FarmControl.cs pomocí sady nástrojů můžete vytvořit tlačítko ve formuláři.

     Upravit název a text tlačítka, například k `New Sheep`.

2.  Otevřete kódu tlačítko (například poklepáním).

     Upravte takto:

    ```csharp
    private void NewSheepButton_Click(object sender, EventArgs e)
    {
      using (Transaction t = farm.Store.TransactionManager.BeginTransaction("Add sheep"))
      {
        elementOperations.MergeElementGroup(farm,
          new ElementGroup(new Sheep(farm.Partition)));
        t.Commit();
      }
    }

    // The following code is shared with other add buttons:
    private ElementOperations operationsCache = null;
    private ElementOperations elementOperations
    {
      get
      {
        if (operationsCache == null)
        {
          operationsCache = new ElementOperations(farm.Store, farm.Partition);
        }
        return operationsCache;
      }
    }
    private Farm farm
    {
      get { return this.farmBindingSource.DataSource as Farm; }
    }

    ```

     Budete také muset vložte následující direktivu:

    ```csharp

    using Microsoft.VisualStudio.Modeling;

    ```

3.  Přidáte podobná tlačítka pro kozy a pole.

4.  Sestavení a spuštění řešení.

5.  Ověřte, že tlačítka Nová přidá položku. Nová položka by se zobrazit v Průzkumníku FarmApp a v zobrazení mřížky příslušná data.

     Nyní byste měli mít upravit název elementu v zobrazení dat mřížky. Můžete také odstranit ho z ní.

 ![DSL&#45;Wpf&#45;2](../modeling/media/dsl-wpf-2.png "DSL-Wpf-2")

### <a name="about-the-code-to-add-an-element"></a>O kódu k přidání elementu
 Následující alternativní kód je pro nová tlačítka element mírně jednodušší.

```csharp
private void NewSheepButton_Click(object sender, EventArgs e)
{
  using (Transaction t = farm.Store.TransactionManager.BeginTransaction("Add sheep"))
  {
    farm.Animals.Add(new Sheep(farm.Partition)); ;
    t.Commit();
  }
}

```

 Tento kód však není nastavena výchozí název pro novou položku. Nejde ho spustit všechny přizpůsobené sloučení, které může definujete v **– Element direktivy sloučení** z DSL, a nejde ho spustit sloučení vlastní kód, který byl definován.

 Proto doporučujeme použít <xref:Microsoft.VisualStudio.Modeling.ElementOperations> k vytvoření nových elementů. Další informace najdete v tématu [přizpůsobení Element vytváření a přesun](../modeling/customizing-element-creation-and-movement.md).

## <a name="see-also"></a>Viz také

- [Jak se definuje jazyk specifický pro doménu](../modeling/how-to-define-a-domain-specific-language.md)
- [Zápis kódu pro úpravu jazyka specifického pro doménu](../modeling/writing-code-to-customise-a-domain-specific-language.md)
- [Sada Modeling SDK pro Visual Studio – jazyky specifické pro doménu](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)