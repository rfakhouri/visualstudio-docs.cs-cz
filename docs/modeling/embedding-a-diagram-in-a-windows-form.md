---
title: Vložení diagramu do formuláře Windows
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: db011f9842d00b6a39be3f1e9f4d4d7a090f2581
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31950540"
---
# <a name="embedding-a-diagram-in-a-windows-form"></a>Vložení diagramu do formuláře Windows
Můžete vložit do ovládacího prvku Windows, která se zobrazí v diagramu DSL [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] okno.

## <a name="embedding-a-diagram"></a>Vložení Diagram

#### <a name="to-embed-a-dsl-diagram-in-a-windows-control"></a>Chcete-li vložit DSL diagram v ovládacím prvku Windows

1.  Přidejte nový **uživatelský ovládací prvek** souboru do projektu DslPackage.

2.  Ovládací prvek Panel přidáte do uživatelského ovládacího prvku. Tento panel bude obsahovat DSL diagramu.

     Přidáte další ovládací prvky, které potřebujete.

     Nastavte vlastnosti ovládacích prvků ukotvení.

3.  V Průzkumníku řešení klikněte pravým tlačítkem na soubor uživatelského ovládacího prvku a klikněte na tlačítko **kód zobrazení**. Přidejte tento konstruktor a proměnná kódu:

    ```csharp

    internal UserControl1(MyDSLDocView docView, Control content)
      : this()
    {
      panel1.Controls.Add(content);
      this.docView = docView;
    }
    private MyDSLDocView docView;

    ```

4.  Přidáte nový soubor do projektu DslPackage s následujícím obsahem:

    ```
    using System.Windows.Forms;
    namespace Company.MyDSL
    {
      partial class MyDSLDocView
      {
        private UserControl1 container;
        public override IWin32Window Window
        {
          get
          {
            if (container == null)
            {
              // Put our own form inside the DSL window:
              container = new UserControl1(this,
                (Control)base.Window);
            }
            return container;
    } } } }

    ```

5.  K testování DSL, stiskněte klávesu F5 a otevřete soubor modelu ukázka. Diagram se zobrazí uvnitř ovládacího prvku. V panelu nástrojů a další funkce fungovat normálně.

#### <a name="updating-the-form-using-store-events"></a>Aktualizace formuláře pomocí úložiště události

1.  V návrháři formuláře přidat **ListBox** s názvem `listBox1`. Tím zobrazíte seznam prvků v modelu. Se zachová v synchronism s použitím modelu *uložení událostí*. Další informace najdete v tématu [událost obslužné rutiny rozšíří změny mimo modelu](../modeling/event-handlers-propagate-changes-outside-the-model.md).

2.  V souboru vlastní kód přepište další metody pro třídu DocView:

    ```

    partial class MyDSLDocView
    {
     /// <summary>
     /// Register store event listeners.
     /// This method is called when the model and diagram
     /// have completed loading.
     /// </summary>
     protected override bool LoadView()
      {
        bool result = base.LoadView();
        Store store = this.DocData.Store;
        EventManagerDirectory emd = store.EventManagerDirectory;
        DomainClassInfo componentClass = store.DomainDataDirectory.FindDomainClass(typeof(ExampleElement));
        emd.ElementAdded.Add(componentClass, new EventHandler<ElementAddedEventArgs>(AddElement));
        emd.ElementDeleted.Add(componentClass, new EventHandler<ElementDeletedEventArgs>(RemoveElement));

        // Do the initial parts list:
        container.SetUpFormFromModel();
        return result;
      }
     /// <summary>
     /// Listener method called on creation of each instance of
     /// the ExampleElement class or its subclasses.
     /// </summary>
     private void AddElement(object sender, ElementAddedEventArgs e)
     {
       container.Add(e.ModelElement as ExampleElement);
     }
     /// <summary>
     /// Listener method called after deletion of each instance of
     /// the ExampleElement class or its subclasses.
     /// </summary>
     private void RemoveElement(object sender, ElementDeletedEventArgs e)
     {
       container.Remove(e.ModelElement as ExampleElement);
     }

    ```

3.  V kódu uživatelského ovládacího prvku vložte metody pro naslouchání elementy přidat nebo odebrat:

    ```

          public partial class UserControl1 : UserControl { ...

    private ExampleModel modelRoot;

    internal void Add(ExampleElement e) { UpdatePartsList(); }
    internal void Remove(ExampleElement e) { UpdatePartsList(); }

    internal void SetUpFormFromModel()
    {
      modelRoot = this.docView.CurrentDiagram.ModelElement as ExampleModel;
      UpdatePartsList();
    }

    private void UpdatePartsList()
    {
      StringBuilder builder = new StringBuilder();
      listBox1.Items.Clear();
      foreach (ExampleElement c in modelRoot.Elements)
      {
        listBox1.Items.Add(c.Name);
      }
    }

    ```

4.  K testování DSL, stiskněte klávesu F5 a experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], otevřete soubor modelu ukázka.

     Všimněte si, že pole se seznamem zobrazuje seznam prvků v modelu a že je správný po všech přidání nebo odstranění a po zpět a znovu.

## <a name="see-also"></a>Viz také

- [Navigace v modelu a aktualizace modelu v kódu programu](../modeling/navigating-and-updating-a-model-in-program-code.md)
- [Zápis kódu pro úpravu jazyka specifického pro doménu](../modeling/writing-code-to-customise-a-domain-specific-language.md)
