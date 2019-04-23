---
title: Aktualizace oblastí formulářů v projektech Outlook při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office projects [Office development in Visual Studio], migrating to .NET Framework 4
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: fed87ee8106c3e8a09c341b9de4709060627dac1
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60048266"
---
# <a name="update-form-regions-in-outlook-projects-that-you-migrate-to-the-net-framework-4-or-the-net-framework-45"></a>Aktualizace oblastí formulářů v projektech Outlook při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5
  Pokud cílové rozhraní projektu doplňku VSTO v Outlooku se oblast formuláře se změní na [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo později, musí provést některé změny do oblasti kódu generovaném formuláři a jakýkoli kód, který vytvoří instanci určité třídy oblasti formuláře za běhu.

## <a name="update-the-generated-form-region-code"></a>Aktualizace kódu generovaném formuláři oblasti
 Pokud cílové rozhraní projektu se změní na [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, musíte změnit kód oblasti generovaném formuláři. Provedené změny se liší pro oblasti formuláře navržené v aplikaci Visual Studio a formuláře, které jste naimportovali z Outlooku. Další informace o rozdílech mezi těmito typy oblasti formuláře, naleznete v tématu [oblastí formulářů aplikace Outlook vytvořit](../vsto/creating-outlook-form-regions.md).

### <a name="to-update-the-generated-code-for-a-form-region-that-you-designed-in-visual-studio"></a>Chcete-li aktualizovat generovaný kód pro oblasti formuláře navržené v aplikaci Visual Studio

1. Otevřete soubor kódu na pozadí oblasti formuláře v editoru kódu. Tento soubor má název *YourFormRegion*. Designer.cs nebo *YourFormRegion*. Designer.vb. Tento soubor v projektech Visual Basicu zobrazíte kliknutím **zobrazit všechny soubory** tlačítko **Průzkumníka řešení**.

2. Upravte deklaraci třídy oblasti formuláře, aby se odvozuje od <xref:Microsoft.Office.Tools.Outlook.FormRegionBase> místo `Microsoft.Office.Tools.Outlook.FormRegionControl`.

3. Upravte konstruktoru třídy oblasti formuláře, jak je znázorněno v následujícím příkladu kódu.

     Následující příklad kódu ukazuje konstruktor třídy oblasti formuláře v projektu, který cílí rozhraní .NET Framework 3.5.

    ```vb
    Public Sub New(ByVal formRegion As Microsoft.Office.Interop.Outlook.FormRegion)
        MyBase.New(formRegion)
        Me.InitializeComponent()
    End Sub
    ```

    ```csharp
    public FormRegion1(Microsoft.Office.Interop.Outlook.FormRegion formRegion)
        : base(formRegion)
    {
        this.InitializeComponent();
    }
    ```

     Následující příklad kódu ukazuje konstruktor třídy oblasti formuláře v projektu, který cílí [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)].

    ```vb
    Public Sub New(ByVal formRegion As Microsoft.Office.Interop.Outlook.FormRegion)
        MyBase.New(Globals.Factory, formRegion)
        Me.InitializeComponent()
    End Sub
    ```

    ```csharp
    public FormRegion1(Microsoft.Office.Interop.Outlook.FormRegion formRegion)
        : base(Globals.Factory, formRegion)
    {
        this.InitializeComponent();
    }
    ```

4. Upravte podpis metody `InitializeManifest` způsob, jak je znázorněno níže. Ujistěte se, že neprovádějte žádné změny kódu v metodě; Tento kód představuje nastavení oblasti formuláře, které jste provedli v návrháři. Ve Vizuálu C# projektů, je třeba rozbalit oblast s názvem `Form Region Designer generated code` zobrazíte takto.

     Následující příklad kódu ukazuje podpis `InitializeManifest` metoda v projektu, který cílí na rozhraní .NET Framework 3.5.

    ```vb
    Private Shared Sub InitializeManifest(ByVal manifest As Microsoft.Office.Tools.Outlook.FormRegionManifest)

        ' Do not change code in this method.
    End Sub
    ```

    ```csharp
    private static void InitializeManifest(Microsoft.Office.Tools.Outlook.FormRegionManifest manifest)
    {
        // Do not change code in this method.
    }
    ```

     Následující příklad kódu ukazuje podpis `InitializeManifest` metoda v projektu, který se zaměřuje [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)].

    ```vb
    Private Shared Sub InitializeManifest(ByVal manifest As Microsoft.Office.Tools.Outlook.FormRegionManifest,
        ByVal factory As Microsoft.Office.Tools.Outlook.Factory)

        ' Do not change code in this method.
    End Sub
    ```

    ```csharp
    private static void InitializeManifest(Microsoft.Office.Tools.Outlook.FormRegionManifest manifest,
        Microsoft.Office.Tools.Outlook.Factory factory)
    {
        // Do not change code in this method.
    }
    ```

5. Přidáte novou oblast formuláře Outlooku položku do projektu. Otevřete soubor kódu na pozadí pro novou oblast formuláře, vyhledejte *YourNewFormRegion* `Factory` a `WindowFormRegionCollection` třídy v souboru a zkopírujte tyto třídy do schránky.

6. Odstraňte novou oblast formuláře, které jste přidali do svého projektu.

7. V souboru kódu na pozadí, kterou aktualizujete pro práci v projektu přesměrovanou oblasti formuláře, vyhledejte *YourOriginalFormRegion* `Factory` a `WindowFormRegionCollection` třídy a nahraďte kód, který jste zkopírovali ze novou oblast formuláře.

8. V *YourNewFormRegion* `Factory` a `WindowFormRegionCollection` třídy, vyhledejte všechny odkazy *YourNewFormRegion* třídy a změňte každý odkaz na  *YourOriginalFormRegion* namísto třídy. Například je název oblasti formuláře při aktualizaci `SalesDataFormRegion` a novou oblast formuláře, kterou jste vytvořili v kroku 5 se jmenuje `FormRegion1`, změňte všechny odkazy na `FormRegion1` k `SalesDataFormRegion`.

#### <a name="to-update-the-generated-code-for-a-form-region-that-you-imported-from-outlook"></a>Chcete-li aktualizovat generovaný kód pro oblasti formuláře, který jste naimportovali z Outlooku

1. Otevřete soubor kódu na pozadí oblasti formuláře v editoru kódu. Tento soubor má název *YourFormRegion*. Designer.cs nebo *YourFormRegion*. Designer.vb. Tento soubor v projektech Visual Basicu zobrazíte kliknutím **zobrazit všechny soubory** tlačítko **Průzkumníka řešení**.

2. Upravte deklaraci třídy oblasti formuláře, aby se odvozuje od <xref:Microsoft.Office.Tools.Outlook.ImportedFormRegionBase> místo `Microsoft.Office.Tools.Outlook.ImportedFormRegion`.

3. Upravte konstruktoru třídy oblasti formuláře, jak je znázorněno v následujícím příkladu kódu.

     Následující příklad kódu ukazuje konstruktor třídy oblasti formuláře v projektu, který cílí rozhraní .NET Framework 3.5.

    ```vb
    Public Sub New(ByVal formRegion As Microsoft.Office.Interop.Outlook.FormRegion)
        MyBase.New(formRegion)
    End Sub
    ```

    ```csharp
    public ImportedFormRegion1(Microsoft.Office.Interop.Outlook.FormRegion formRegion)
        : base(formRegion)
    {
        this.FormRegionShowing += new System.EventHandler(this.TaskFormRegion_FormRegionShowing);
        this.FormRegionClosed += new System.EventHandler(this.TaskFormRegion_FormRegionClosed);
    }
    ```

     Následující příklad kódu ukazuje podpis konstruktoru třídy oblasti formuláře v projektu, který cílí [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)].

    ```vb
    Public Sub New(ByVal formRegion As Microsoft.Office.Interop.Outlook.FormRegion)
        MyBase.New(Globals.Factory, formRegion)
    End Sub
    ```

    ```csharp
    public ImportedFormRegion1(Microsoft.Office.Interop.Outlook.FormRegion formRegion)
        : base(Globals.Factory, formRegion)
    {
        this.FormRegionShowing += new System.EventHandler(this.TaskFormRegion_FormRegionShowing);
        this.FormRegionClosed += new System.EventHandler(this.TaskFormRegion_FormRegionClosed);
    }
    ```

4. Pro každý jednotlivý řádek kódu `InitializeControls` metodu, která inicializuje ovládací prvek ve třídě oblasti formuláře, upravte kód, jak je znázorněno níže.

     Následující příklad kódu ukazuje, jak inicializovat ovládací prvek v projektu, který cílí rozhraní .NET Framework 3.5. V tomto kódu `GetFormRegionControl` metoda má parametr typu, který určuje typ ovládacího prvku, který je vrácen.

    ```vb
    Me.olkTextBox1 = Me.GetFormRegionControl(Of Microsoft.Office.Interop.Outlook.OlkTextBox)("OlkTextBox1")
    ```

    ```csharp
    this.olkTextBox1 = this.GetFormRegionControl<Microsoft.Office.Interop.Outlook.OlkTextBox>("OlkTextBox1");
    ```

     Následující příklad kódu ukazuje, jak inicializovat ovládací prvek v projektu, který cílí [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]. V tomto kódu <xref:Microsoft.Office.Tools.Outlook.ImportedFormRegionBase.GetFormRegionControl%2A> metoda nemá parametr typu. Musí se přetypovávat návratovou hodnotu pro typ ovládacího prvku, který se inicializuje.

    ```vb
    Me.olkTextBox1 = CType(GetFormRegionControl("OlkTextBox1"), Microsoft.Office.Interop.Outlook.OlkTextBox)
    ```

    ```csharp
    this.olkTextBox1 = (Microsoft.Office.Interop.Outlook.OlkTextBox)GetFormRegionControl("OlkTextBox1");
    ```

5. Přidáte novou oblast formuláře Outlooku položku do projektu. Otevřete soubor kódu na pozadí pro novou oblast formuláře, vyhledejte *YourNewFormRegion* `Factory` a `WindowFormRegionCollection` třídy v souboru a zkopírujte tyto třídy do schránky.

6. Odstraňte novou oblast formuláře, které jste přidali do svého projektu.

7. V souboru kódu na pozadí, kterou aktualizujete pro práci v projektu přesměrovanou oblasti formuláře, vyhledejte *YourOriginalFormRegion* `Factory` a `WindowFormRegionCollection` třídy a nahraďte kód, který jste zkopírovali ze novou oblast formuláře.

8. V *YourNewFormRegion* `Factory` a `WindowFormRegionCollection` třídy, vyhledejte všechny odkazy *YourNewFormRegion* třídy a změňte každý odkaz na  *YourOriginalFormRegion* namísto třídy. Například je název oblasti formuláře při aktualizaci `SalesDataFormRegion` a novou oblast formuláře, kterou jste vytvořili v kroku 5 se jmenuje `FormRegion1`, změňte všechny odkazy na `FormRegion1` k `SalesDataFormRegion`.

## <a name="instantiate-form-region-classes"></a>Vytvoření instance třídy oblasti formuláře
 Je třeba upravit jakýkoli kód, který dynamicky vytvoří instanci určité třídy oblasti formuláře. V projektech cílených rozhraní .NET Framework 3.5, lze vytvořit instanci třídy oblasti formuláře jako `Microsoft.Office.Tools.Outlook.FormRegionManifest` přímo. V projektech, které se zaměřují [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, jsou tyto třídy rozhraní, které nelze přímo vytvořit instanci.

 Pokud cílové rozhraní projektu se změní na [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, musíte vytvořit instanci rozhraní pomocí metod, které jsou poskytovány `Globals.Factory` vlastnost. Další informace o `Globals.Factory` vlastnost, naleznete v tématu [globální přístup k objektům v projektech Office](../vsto/global-access-to-objects-in-office-projects.md).

 Následující tabulka uvádí oblasti formuláře typu a metody pro použití k vytvoření instancí typů v projektech, které se zaměřují [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější.

|Type|Metoda Factory se má použít|
|----------|---------------------------|
|<xref:Microsoft.Office.Tools.Outlook.FormRegionCustomAction>|<xref:Microsoft.Office.Tools.Outlook.Factory.CreateFormRegionCustomAction%2A>|
|<xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs>|<xref:Microsoft.Office.Tools.Outlook.Factory.CreateFormRegionInitializingEventArgs%2A>|
|<xref:Microsoft.Office.Tools.Outlook.FormRegionManifest>|<xref:Microsoft.Office.Tools.Outlook.Factory.CreateFormRegionManifest%2A>|

## <a name="see-also"></a>Viz také:
- [Migrace řešení Office na rozhraní .NET Framework 4 nebo novější](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)
- [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)
