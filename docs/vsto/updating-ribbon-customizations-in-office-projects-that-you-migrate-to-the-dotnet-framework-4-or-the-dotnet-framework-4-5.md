---
title: "Aktualizace vlastních nastavení pásu karet v projektech Office při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: Office projects [Office development in Visual Studio], migrating to .NET Framework 4
ms.assetid: 3b7c8ad4-a616-4b42-9d62-9658fdefe6a3
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: d2c7dfef925ff61255e57315a3980fa6a145c235
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="updating-ribbon-customizations-in-office-projects-that-you-migrate-to-the-net-framework-4-or-the-net-framework-45"></a>Aktualizace vlastních nastavení pásu karet v projektech Office při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5
  Pokud projekt obsahuje přizpůsobení pásu karet, která byla vytvořena pomocí **pásu karet (vizuálního návrháře)** položek projektu, pokud rozhraní target framework se změní na, je třeba provést následující změny do projektu kódu [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo později.  
  
-   Upravte generovaný kód pásu karet.  
  
-   Upravte kód, který vytvoří instanci ovládacích prvků pásu karet za běhu, zpracovává události pásu karet nebo nastaví pozici součásti pásu karet prostřednictvím kódu programu.  
  
## <a name="updating-the-generated-ribbon-code"></a>Aktualizace kód vygenerovaný pásu karet  
 Pokud je na změnit cílový framework projektu [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, musíte změnit generovaný kód pro položku pás karet tak, že provedete následující kroky. Soubory kódu, které je potřeba aktualizovat závisí na programovací jazyk a vytváření projektu:  
  
-   V projektech Visual Basic nebo v projektech Visual C#, které jste vytvořili v některém [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)] nebo [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)] proveďte všechny kroky v souboru kódu na pozadí pásu karet (*YourRibbonItem*. Designer.cs nebo *YourRibbonItem*. Designer.vb). Chcete-li naleznete v souboru kódu na pozadí v projekty Visual Basic, klikněte na tlačítko **zobrazit všechny soubory** tlačítka na **Průzkumníku řešení**.  
  
-   V projektech Visual C#, které jste vytvořili v sadě Visual Studio 2008 a pak upgradovat na [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)], proveďte první dva kroky v souboru kódu pásu karet (*YourRibbonItem*.cs nebo *YourRibbonItem*VB), a Proveďte zbývající kroky v souboru kódu na pozadí pásu karet.  
  
#### <a name="to-change-the-generated-ribbon-code"></a>Chcete-li změnit generovaný kód pásu karet  
  
1.  Upravit deklaraci třídy pás karet tak, aby je odvozena z <xref:Microsoft.Office.Tools.Ribbon.RibbonBase> místo Microsoft.Office.Tools.Ribbon.OfficeRibbon.  
  
2.  Upravte konstruktoru třídy pásu karet, jak je uvedeno níže. Pokud jste přidali všechny vlastní kód do konstruktoru, neměňte vašeho kódu. V projektech Visual Basic upravte pouze konstruktor bez parametrů. Ignorujte jiné konstruktoru.  
  
     Následující příklad kódu ukazuje výchozí konstruktor třídy pásu karet v projektu s cílem rozhraní .NET Framework 3.5.  
  
    ```vb  
    Public Sub New()  
        MyBase.New()  
        InitializeComponent()  
    End Sub  
    ```  
  
    ```csharp  
    public Ribbon1()  
    {  
        InitializeComponent();  
    }  
    ```  
  
     Následující příklad kódu ukazuje výchozí konstruktor třídy pásu karet v projektu s cílem [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější.  
  
    ```vb  
    Public Sub New()  
        MyBase.New(Globals.Factory.GetRibbonFactory())  
        InitializeComponent()  
    End Sub  
    ```  
  
    ```csharp  
    public Ribbon1()  
        : base(Globals.Factory.GetRibbonFactory())  
    {  
        InitializeComponent();  
    }  
    ```  
  
3.  V `InitializeComponent` metoda, upravit kód, který vytvoří ovládacího prvku pás karet tak, aby kód místo toho používá jednu z metod helper <xref:Microsoft.Office.Tools.Ribbon.RibbonFactory> objektu.  
  
    > [!NOTE]  
    >  V jazyce Visual C# projekty, je třeba rozbalit oblasti, který je pojmenován `Component Designer generated code` zobrazíte `InitializeComponent` metoda.  
  
     Předpokládejme například, že soubor obsahuje následující řádek kódu, který vytvoří <xref:Microsoft.Office.Tools.Ribbon.RibbonButton> s názvem `button1` v projektu, jehož cílem rozhraní .NET Framework 3.5.  
  
    ```vb  
    Me.button1 = New Microsoft.Office.Tools.Ribbon.RibbonButton()  
    ```  
  
    ```csharp  
    this.button1 = new Microsoft.Office.Tools.Ribbon.RibbonButton();  
    ```  
  
     V projektu, jehož cílem [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, musíte použít následující kód místo.  
  
    ```vb  
    Me.button1 = Me.Factory.CreateRibbonButton()  
    ```  
  
    ```csharp  
    this.button1 = this.Factory.CreateRibbonButton();  
    ```  
  
     Úplný seznam pomocné metody pro ovládací prvky pásu karet najdete v tématu [vytváření instancí ovládacích prvků pásu karet](#ribboncontrols).  
  
4.  V projekty Visual C#, upravte každý řádek kódu v `InitializeComponent` metoda, která používá <xref:System.EventHandler%601> delegátovi, aby se místo toho použít konkrétní delegáta pásu karet.  
  
     Předpokládejme například, že soubor obsahuje následující řádek kódu, který zpracovává <xref:Microsoft.Office.Tools.Ribbon.RibbonButton.Click> událost v projektu, jehož cílem rozhraní .NET Framework 3.5.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
     V projektu, jehož cílem [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, musíte použít následující kód místo.  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
     Úplný seznam delegátů pásu karet najdete v tématu [zpracování události pásu karet](#ribbonevents).  
  
5.  V projektech Visual Basic, vyhledejte `ThisRibbonCollection` třída na konci souboru. Upravte deklaraci této třídy tak, aby ho už nebude dědit z Microsoft.Office.Tools.Ribbon.RibbonReadOnlyCollection.  
  
##  <a name="ribboncontrols"></a>Vytváření instancí ovládacích prvků pásu karet  
 Je třeba upravit kód, který dynamicky vytvoří ovládacích prvků pásu karet. V projektech cílených pro rozhraní .NET Framework 3.5 ovládacích prvků pásu karet jsou třídy, které můžete vytvořit instanci přímo v některých scénářích. V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, jsou tyto prvky rozhraní, které nelze vytvořit instanci přímo. Ovládací prvky musí vytvořit pomocí metody, které jsou poskytovány <xref:Microsoft.Office.Tools.Ribbon.RibbonFactory> objektu.  
  
 Existují dva způsoby pro přístup <xref:Microsoft.Office.Tools.Ribbon.RibbonFactory> objektu:  
  
-   Pomocí vlastnosti objektu pro vytváření třídy pásu karet. Použijte tento přístup z kódu ve své třídě pásu karet.  
  
-   Pomocí metody Globals.Factory.GetRibbonFactory. Použijte tento přístup z kódu mimo svou třídu pásu karet. Další informace o třídě Globals najdete v tématu [globální přístup k objektům v projektech Office](../vsto/global-access-to-objects-in-office-projects.md).  
  
 Následující příklad kódu ukazuje, jak vytvořit <xref:Microsoft.Office.Tools.Ribbon.RibbonButton> ve třídě pásu karet v projektu, jehož cílem [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější.  
  
<CodeContentPlaceHolder>10</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>11</CodeContentPlaceHolder>  
 Následující tabulka uvádí prvky, můžete programově vytvořit a způsob, kterým chcete-li vytvořit ovládací prvky v projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější.  
  
|Ovládací prvek|Metoda RibbonFactory pro použití v [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] a novější projekty|  
|-------------|---------------------------------------------------------------------------------------------------------------|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonButton%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonButtonGroup>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonButtonGroup%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonCheckBox%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonComboBox%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonDialogLauncher>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonDialogLauncher%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>:|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonDropDown%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDownItem>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonDropDownItem%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonEditBox%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonGallery%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonGroup>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonGroup%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonLabel>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonLabel%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonManager>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonManager%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonMenu%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonSeparator%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonSplitButton%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonTab%2A>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|<xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.CreateRibbonToggleButton%2A>|  
  
##  <a name="ribbonevents"></a>Zpracování událostí pásu karet  
 Je třeba upravit kód, který zpracovává události ovládacích prvků pásu karet. V projektech cílených pro rozhraní .NET Framework 3.5, tyto události jsou zpracovávány obecná <xref:System.EventHandler%601> delegovat. V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, tyto události se teď požádat o další delegáti.  
  
 Následující tabulka uvádí události pásu karet a delegáti, které jsou spojeny s nimi v projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější.  
  
|Událost|Delegát pro použití v [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] a novější projekty|  
|-----------|---------------------------------------------------------------------------------------------------|  
|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.LoadImage>událost v generovaná třída pásu karet|<xref:Microsoft.Office.Tools.Ribbon.RibbonLoadImageEventHandler>|  
|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.Load>|<xref:Microsoft.Office.Tools.Ribbon.RibbonUIEventHandler>|  
|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton.Click><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox.Click><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.ItemsLoading><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.TextChanged><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.ButtonClick><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.ItemsLoading><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown.SelectionChanged><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox.TextChanged><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ButtonClick><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.Click><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ItemsLoading><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGroup.DialogLauncherClick><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu.ItemsLoading><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton.Click><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton.Click>|<xref:Microsoft.Office.Tools.Ribbon.RibbonControlEventHandler>|  
  
## <a name="setting-the-position-of-a-ribbon-component-programmatically"></a>Nastavení polohy součásti pásu karet prostřednictvím kódu programu  
 Je třeba upravit kód, který nastavuje pozici skupin, karty nebo ovládací prvky pásu karet. V projektech cílených pro rozhraní .NET Framework 3.5 můžete metody AfterOfficeId a BeforeOfficeId statické třídy Microsoft.Office.Tools.Ribbon.RibbonPosition přiřadit vlastnost umístění skupiny, karta nebo ovládací prvek. V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, musí tyto metody přístupu pomocí <xref:Microsoft.Office.Tools.Ribbon.RibbonFactory.RibbonPosition%2A> vlastnost poskytované <xref:Microsoft.Office.Tools.Ribbon.RibbonFactory> objektu.  
  
 Existují dva způsoby pro přístup <xref:Microsoft.Office.Tools.Ribbon.RibbonFactory> objektu:  
  
-   Pomocí vlastnosti objektu pro vytváření třídy pásu karet. Použijte tento přístup z kódu ve své třídě pásu karet.  
  
-   Pomocí metody Globals.Factory.GetRibbonFactory. Použijte tento přístup z kódu mimo svou třídu pásu karet. Další informace o třídě Globals najdete v tématu [globální přístup k objektům v projektech Office](../vsto/global-access-to-objects-in-office-projects.md).  
  
 Následující příklad kódu ukazuje, jak nastavit vlastnost umístění na kartě v třídě pásu karet v projektu s cílem rozhraní .NET Framework 3.5.  
  
```vb  
Me.tab1.Position = RibbonPosition.AfterOfficeId("TabHome")  
```  
  
```csharp  
this.tab1.Position = RibbonPosition.AfterOfficeId("TabHome");  
```  
  
 Následující příklad kódu ukazuje pro stejnou úlohu v projektu, jehož cílem [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)].  
  
```vb  
Me.tab1.Position = Me.Factory.RibbonPosition.AfterOfficeId("TabHome")  
```  
  
```csharp  
this.tab1.Position = this.Factory.RibbonPosition.AfterOfficeId("TabHome");  
```  
  
## <a name="see-also"></a>Viz také  
 [Migrace řešení Office na rozhraní .NET Framework 4 nebo novější](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)   
 [Návrhář pásu karet](../vsto/ribbon-designer.md)  
  
  