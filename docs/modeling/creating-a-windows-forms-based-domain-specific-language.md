---
title: Vytvoření doménově specifického jazyka založeného na Windows Forms
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ad4e3c3007a00245f632e4645deb1014b5c22508
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2019
ms.locfileid: "67821396"
---
# <a name="create-a-windows-forms-based-domain-specific-language"></a>Vytvoření jazyka specifického pro doménu formulářů Windows

Windows Forms slouží k zobrazení stavu modelu jazyka specifického pro doménu (DSL), namísto použití DSL diagram. Toto téma vás provede vazbu formuláře Windows k DSL pomocí Visual Studio Visualization and Modeling SDK.

Následující obrázek ukazuje formulář uživatelské rozhraní Windows a Průzkumníka modelu DSL instance:

![Instance DSL v sadě Visual Studio](../modeling/media/dsl-wpf-2.png)

## <a name="create-a-windows-forms-dsl"></a>Vytvoření prvku Windows Forms DSL

**Minimální návrháře WinForm** DSL šablona vytvoří minimální DSL, který můžete upravit tak, aby vyhovoval vašim požadavkům.

1. Vytvoření DSL z **minimální návrháře WinForm** šablony.

    V tomto názorném postupu se předpokládá, že následující názvy:

   | | |
   |-|-|
   | Název řešení a DSL | FarmApp |
   | Obor názvů | Company.FarmApp |

2. Experimentujte s počáteční příklad, který poskytuje šablony:

   1. Transformujte všechny šablony.

   2. Sestavení a spuštění ukázky (**Ctrl**+**F5**).

   3. V experimentální instanci sady Visual Studio, otevřete `Sample` soubor v ladění projektu.

        Všimněte si, že se zobrazí v ovládacím prvku Windows Forms.

        Můžete také vidět prvky zobrazí v Průzkumníku modelu.

        Přidat některé prvky ve formuláři nebo v Průzkumníku a Všimněte si, že se zobrazí na další.

   V hlavní instanci aplikace Visual Studio Všimněte si, že informace o řešení DSL následující body:

- `DslDefinition.dsl` neobsahuje žádné elementy diagramu. Je to proto, že diagramy DSL nebudeme používat k zobrazení instance modely tento DSL. Místo toho vytvoří vazbu mezi formuláři Windows a modelu a prvky ve formuláři se zobrazí modelu.

- Kromě `Dsl` a `DslPackage` projekty, řešení obsahuje projekt třetí s názvem `UI.` **uživatelského rozhraní** projekt obsahuje definici ovládacího prvku Windows Forms. `DslPackage` závisí na `UI`, a `UI` závisí na `Dsl`.

- V `DslPackage` projektu `UI\DocView.cs` obsahuje kód, který zobrazí ovládacího prvku Windows Forms, který je definován v `UI` projektu.

- `UI` Projekt obsahuje ukázkový pracovní ovládacího prvku formuláře vázán na DSL. Ale nebude fungovat, pokud jste změnili definici DSL. `UI` Projekt obsahuje:

  - Windows Forms třídu s názvem `ModelViewControl`.

  - Soubor s názvem `DataBinding.cs` , který obsahuje další částečnou definici z `ModelViewControl`. Chcete-li zobrazit jeho obsah v **Průzkumníka řešení**, otevřete místní nabídku pro soubor a zvolte **zobrazit kód**.

### <a name="about-the-ui-project"></a>Informace o projektu uživatelského rozhraní

Při aktualizaci souboru definice DSL definovat vlastní DSL, budete muset aktualizovat ovládacího prvku `UI` projektu k zobrazení vašeho DSL. Na rozdíl od `Dsl` a `DslPackage` projekty, ukázka `UI` projektu negeneruje z `DslDefinitionl.dsl`. Můžete přidat soubory .tt ke generování kódu, pokud chcete, i když v tomto názorném postupu, který není součástí.

## <a name="update-the-dsl-definition"></a>Aktualizovat definici DSL

Následující definice DSL se používá v tomto názorném postupu.

![DSL&#45;Wpf&#45;1](../modeling/media/dsl-wpf-1.png)

1. Otevřete DslDefinition.dsl v Návrháři DSL.

2. Odstranit **ExampleElement**

3. Přejmenovat **ExampleModel** doménovou třídu `Farm`.

     Nabízí další doménu vlastnosti s názvem `Size` typu **Int32**, a `IsOrganic` typu **logická**.

    > [!NOTE]
    > Pokud odstraníte třídu kořenové domény a pak vytvořte nový kořen, budete muset obnovit vlastnost kořenová třída editoru. V **Průzkumník DSL**vyberte **Editor**. V okně Vlastnosti nastavte **kořenová třída** k `Farm`.

4. Použití **doménovou třídu s názvem** nástroj k vytvoření následujících doménové třídy:

    - `Field` -Zadejte to další doménovou vlastnost s názvem `Size`.

    - `Animal` – V okně Vlastnosti nastavte **modifikátor dědičnosti** k **abstraktní**.

5. Použití **doménové třídy** vytvořte následující třídy:

    - `Sheep`

    - `Goat`

6. Použití **dědičnosti** nástroj aby `Goat` a `Sheep` dědí `Animal`.

7. Použití **obsažení** nástroj pro vložení `Field` a `Animal` pod `Farm`.

8. Můžete chtít přehledné diagramu. Chcete-li snížit počet duplicitních prvků, použijte **přenést zde podstrom** příkazu v místní nabídce prvky listu.

9. **Transformovat všechny šablony** na panelu nástrojů Průzkumníku řešení.

10. Sestavení **Dsl** projektu.

    > [!NOTE]
    > V této fázi nebude ostatních projektů se sestaví bez chyb. Chceme sestavení projektu Dsl tak, aby byla k dispozici v Průvodci zdroje dat jeho sestavení.

## <a name="update-the-ui-project"></a>Aktualizovat projekt uživatelského rozhraní

Nyní můžete vytvořit nového uživatelského ovládacího prvku, který se zobrazí informace, které je uložen v modelu DSL. Nejjednodušší způsob, jak připojit uživatelský ovládací prvek modelu je prostřednictvím datové vazby. Datové vazby adaptér typ s názvem **ModelingBindingSource** je navržená speciálně pro připojení k rozhraní vmsdk následující položky DSL.

### <a name="define-your-dsl-model-as-a-data-source"></a>Definovat jako zdroj dat modelu DSL

1. Na **Data** nabídce zvolte **zobrazit zdroje dat**.

     **Zdroje dat** otevře se okno.

     Zvolte **přidat nový zdroj dat**. **Průvodce konfigurací zdroje dat** otevře.

2. Zvolte **objekt**, **Další**.

     Rozbalte **Dsl**, **Company.FarmApp**a vyberte **farmy**, což je kořenová třída modelu. Zvolte **Dokončit**.

     V Průzkumníku řešení klikněte **uživatelského rozhraní** projekt nyní obsahuje **Properties\DataSources\Farm.datasource**

     V okně zdroje dat se zobrazí vlastnosti a vztahy třídy modelu.

     ![DslWpf&#45;3](../modeling/media/dslwpf-3.png)

### <a name="connect-your-model-to-a-form"></a>Připojte se k formuláři modelu

1. V **uživatelského rozhraní** projektu, odstraňte všechny existující soubory CS.

2. Přidat nový **uživatelský ovládací prvek** soubor s názvem `FarmControl` k **uživatelského rozhraní** projektu.

3. V **zdroje dat** okna, v rozevírací nabídce **farmy**, zvolte **podrobnosti**.

    Ponechejte výchozí nastavení pro ostatní vlastnosti.

4. V návrhovém zobrazení otevřete FarmControl.cs.

    Přetáhněte **farmy** z okna zdroje dat do FarmControl.

    Sadu ovládacích prvků se zobrazí, jeden pro každou vlastnost. Vlastnosti relace nelze vytvořit ovládací prvky.

5. Odstranit **farmBindingNavigator**. To je také automaticky generovány v `FarmControl` návrháře, ale není užitečné pro tuto aplikaci.

6. Pomocí nástrojů, vytvořte dvě instance **DataGridView**a pojmenujte je `AnimalGridView` a `FieldGridView`.

   > [!NOTE]
   > Alternativní krokem je přetáhnout položky pole a zvířat z okna zdroje dat na ovládací prvek. Tato akce automaticky vytvoří datových mřížek a vazby mezi zobrazení mřížky a zdrojem dat. Nicméně tato vazba nefunguje správně pro DSL. Proto je vhodnější vytvořit datových mřížek a vazby ručně.

7. Pokud nebude obsahovat panelu nástrojů **ModelingBindingSource** nástroj, přidejte ji. V místní nabídce **Data** kartě **zvolit položky**. V **zvolit položky nástrojů** dialogového okna, vyberte **ModelingBindingSource** z **rozhraní .NET Framework** kartu.

8. Pomocí nástrojů, vytvořte dvě instance **ModelingBindingSource**a pojmenujte je `AnimalBinding` a `FieldBinding`.

9. Nastavte **DataSource** vlastnosti každého **ModelingBindingSource** k **farmBindingSource**.

     Nastavte **DataMember** vlastnost **zvířat** nebo **pole**.

10. Nastavte **DataSource** vlastnosti `AnimalGridView` k `AnimalBinding`a `FieldGridView` k `FieldBinding`.

11. Upravte rozložení ovládacího prvku farmy, aby vaše to zkusit.

    **ModelingBindingSource** je adaptér, který provádí několik funkcí, které jsou specifické pro DSL:

- Aktualizace objektu v transakci Store vmsdk následující položky.

   Například když uživatel odstraní řádek z zobrazení mřížky dat, pravidelné vazby způsobí výjimka transakce.

- Zajišťuje, že když uživatel vybere řádek, v okně vlastností zobrazuje vlastnosti odpovídající prvek modelu, namísto řádek mřížky dat.

  ![DslWpf4](../modeling/media/dslwpf4.png) schématu propojení mezi zdroji dat a zobrazení.

### <a name="complete-the-bindings-to-the-dsl"></a>Dokončení vazby na DSL

1. Přidejte následující kód v samostatném souboru kódu v **uživatelského rozhraní** projektu:

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

2. V **DslPackage** projektu, upravit **DslPackage\DocView.tt** aktualizace definicí následující proměnné:

    ```csharp
    string viewControlTypeName = "FarmControl";
    ```

## <a name="test-the-dsl"></a>Testování DSL

DSL řešení teď můžete sestavit a spustit, i když může být vhodné případná zlepšení další rozšíření později.

1. Sestavte a spusťte řešení.

2. V experimentální instanci sady Visual Studio, otevřete **ukázka** souboru.

3. V **FarmApp Explorer**, otevřete místní nabídku na **farmy** kořenový uzel a zvolte **přidat nové Goat**.

     `Goat1` Zobrazí se v **zvířat** zobrazení.

    > [!WARNING]
    > Nabídku je nutné použít na **farmy** uzlu, ne **zvířat** uzlu.

4. Vyberte **farmy** kořenový uzel a zobrazte její vlastnosti.

     Ve formě zobrazení změnit **název** nebo **velikost** farmy.

     Když přejdete mimo každé pole ve formuláři, odpovídající změny vlastností v okně Vlastnosti.

## <a name="enhance-the-dsl"></a>Vylepšení DSL

### <a name="make-the-properties-update-immediately"></a>Vlastnosti aktualizovat hned

1. V návrhovém zobrazení FarmControl.cs vyberte jednoduché pole, jako je název, velikost nebo IsOrganic.

2. V okně Vlastnosti rozbalte **DataBindings** a otevřete **(rozšířené)** .

     V **formátování a rozšířené vazby** dialogového okna, v části **režim aktualizace zdroje dat**, zvolte **OnPropertyChanged –** .

3. Sestavte a spusťte řešení.

     Ověřte, že když změníte obsah pole odpovídající vlastnost okamžitě změny modelu farmy.

### <a name="provide-add-buttons"></a>Zadejte tlačítka pro přidání

1. V návrhovém zobrazení FarmControl.cs vytvoření tlačítka na formuláři pomocí panelu nástrojů.

    Upravit název a text na tlačítku, třeba `New Sheep`.

2. Otevřete kódu na pozadí tlačítka (například tím, že na ni poklikáte).

    Upravte následujícím způsobem:

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

    Také je potřeba vložit následující direktivy:

   ```csharp

   using Microsoft.VisualStudio.Modeling;
   ```

3. Přidání tlačítek podobné koz a polí.

4. Sestavte a spusťte řešení.

5. Ověřte, že nové tlačítko přidá položka. Nová položka by se zobrazit v Průzkumníku FarmApp a v zobrazení mřížky příslušná data.

    Je třeba možnost upravit název elementu v zobrazení mřížky dat. Můžete také odstranit ji z něj.

   ![DSL&#45;Wpf&#45;2](../modeling/media/dsl-wpf-2.png)

### <a name="about-the-code-to-add-an-element"></a>O kódu pro přidání elementu

Pro nový prvek tlačítka následující alternativní kód je poněkud jednodušší.

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

Tento kód však není nastavena výchozí název pro novou položku. Nejde spustit všechny přizpůsobené sloučení, které může jste definovali v **direktivy sloučení elementů** nástroje DSL, a nejde ho spustit jakýkoli kód vlastní sloučení, které byly definovány.

Proto doporučujeme použít <xref:Microsoft.VisualStudio.Modeling.ElementOperations> k vytvoření nových prvků. Další informace najdete v tématu [přizpůsobení vytvoření a přesunutí elementu](../modeling/customizing-element-creation-and-movement.md).

## <a name="see-also"></a>Viz také:

- [Jak se definuje jazyk specifický pro doménu](../modeling/how-to-define-a-domain-specific-language.md)
- [Zápis kódu pro úpravu jazyka specifického pro doménu](../modeling/writing-code-to-customise-a-domain-specific-language.md)
- [Sada Modeling SDK pro Visual Studio – jazyky specifické pro doménu](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)
