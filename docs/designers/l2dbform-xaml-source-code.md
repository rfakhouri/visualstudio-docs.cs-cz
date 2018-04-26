---
title: L2DBForm.XAML zdrojového kódu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: sample
ms.assetid: 624e96d4-6d27-4195-8ac2-2f3835f6c57e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bd9f7601a7e2a24ec41a12d194aac65445c6d159
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="l2dbformxaml-source-code"></a>L2DBForm.XAML zdrojového kódu

Toto téma obsahuje a popisuje zdrojový soubor XAML pro [WPF Data vazbu pomocí LINQ to XML příklad](../designers/wpf-data-binding-using-linq-to-xml-example.md), L2DBForm.xaml.

## <a name="overall-ui-structure"></a>Celková struktura uživatelského rozhraní

Je typické pro projekt WPF, tento soubor obsahuje jeden nadřazený element, <xref:System.Windows.Window> – element XML přidružené odvozené třídy `L2XDBFrom` v `LinqToXmlDataBinding` oboru názvů.

Klientské oblasti je obsažena v <xref:System.Windows.Controls.StackPanel> , je zadána světla modré pozadí. Tento panel obsahuje čtyři <xref:System.Windows.Controls.DockPanel> části uživatelského rozhraní odděleny <xref:System.Windows.Controls.Separator> řádky. Účelem těchto částí je popsaná v **poznámky** v [předchozí tématu](../designers/walkthrough-linqtoxmldatabinding-example.md).

Každý oddíl obsahuje štítek, který ji identifikuje. V první dvě části, je tento popisek otočený o 90 stupňů prostřednictvím <xref:System.Windows.FrameworkElement.LayoutTransform%2A>. Zbývající části obsahuje prvky uživatelského rozhraní, které jsou vhodné pro účel tohoto oddílu: text bloky, textová pole, tlačítka a tak dále. Někdy podřízenou <xref:System.Windows.Controls.StackPanel> slouží k zarovnání těchto podřízených ovládacích prvků.

## <a name="window-resource-section"></a>Části okna prostředků

Otevření `<Window.Resources>` značky na řádku 9 označuje začátek části okna prostředků. Končí na řádku 35 uzavírací značku.

`<ObjectDataProvider>` Deklaruje značku, která zahrnuje řádky 11 až 25, <xref:System.Windows.Data.ObjectDataProvider>s názvem `LoadedBooks`, která používá <xref:System.Xml.Linq.XElement> jako zdroj. <xref:System.Xml.Linq.XElement> Se inicializuje pomocí analýza embedded dokumentů XML ( `CDATA` element). Všimněte si, že mezer se zachová, i když deklarace embedded dokument XML, a také při analýze. Protože se zachová, i mezer <xref:System.Windows.Controls.TextBlock> řízení, které se používá k zobrazení nezpracované XML, nemá žádné speciální XML možnosti formátování.

Nakonec <xref:System.Windows.DataTemplate> s názvem `BookTemplate` je definován na řádky 28 prostřednictvím 34. Tato šablona se používá k zobrazení položek v **seznamu adresáře** část uživatelského rozhraní. Použije datové vazby a LINQ dynamických vlastností XML pro načtení seznamu ID a název adresáře prostřednictvím následujících přiřazení:

```
Text="{Binding Path=Attribute[id].Value}"Text="{Binding Path=Value}"
```

## <a name="data-binding-code"></a>Data vazby kód

Kromě <xref:System.Windows.DataTemplate> element, datové vazby se používá v počet jiných míst v tomto souboru.

Při otevírání `<StackPanel>` značky na řádku 38, <xref:System.Windows.FrameworkElement.DataContext%2A> tohoto panelu je nastavena na `LoadedBooks` zprostředkovatele dat.

```
DataContext="{Binding Source={StaticResource LoadedBooks}}
```

Nastavení kontextu dat umožňuje (na řádku 46) pro <xref:System.Windows.Controls.TextBlock> s názvem `tbRawXml` chcete zobrazit nezpracované XML podle vazby pro tohoto zprostředkovatele dat `Xml` vlastnost:

```
Text="{Binding Path=Xml}"
```

<xref:System.Windows.Controls.ListBox> v **seznamu adresáře** části uživatelského rozhraní na řádky 58 prostřednictvím 62, nastaví šablony položek s jeho zobrazení `BookTemplate` definovány v části okna prostředků:

```
ItemTemplate ="{StaticResource BookTemplate}"
```

Potom na řádky 59 prostřednictvím 62 skutečnými hodnotami knih je vázána na toto pole se seznamem:

```
<ListBox.ItemsSource>
    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
</ListBox.ItemsSource>
```

Třetí část uživatelského rozhraní, **upravit vybranou knihu**, nejprve váže <xref:System.Windows.FrameworkElement.DataContext%2A> nadřazené <xref:System.Windows.Controls.StackPanel> pro aktuálně vybrané položky v z **seznamu adresáře** část uživatelského rozhraní (řádek 82):

```
DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}"
```

Poté použije obousměrný datovou vazbu, tak, aby aktuální hodnoty elementů adresáře se zobrazí a aktualizovat ze dvou textových polí v tomto panelu. Datová vazba na dynamické vlastnosti je podobná použít v datové vazby `BookTemplate` data šablony:

```
Text="{Binding Path=Attribute[id].Value}"...Text="{Binding Path=Value}"
```

Poslední část uživatelského rozhraní, **přidat nové knihy**, nepoužívá datové vazby v kódu jeho XAML. Místo toho je datové vazby v jeho zpracování kód v souboru událostí *L2DBForm.xaml.cs*.

## <a name="example"></a>Příklad

### <a name="description"></a>Popis

> [!NOTE]
> Doporučujeme zkopírujte následující kód pod do editoru kódu, například C# editoru zdrojového kódu v sadě Visual Studio, aby čísla řádků bude jednodušší, sledovat.

### <a name="code"></a>Kód

```xml
<Window x:Class="LinqToXmlDataBinding.L2XDBForm"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:system="clr-namespace:System;assembly=mscorlib"
    xmlns:xlinq="clr-namespace:System.Xml.Linq;assembly=System.Xml.Linq"
    xmlns:local="clr-namespace:LinqToXmlDataBinding"
    Title="WPF Data Binding using LINQ-to-XML" Height="665" Width="500" ResizeMode="NoResize">

    <Window.Resources>
        <!-- Books provider and inline data -->
        <ObjectDataProvider x:Key="LoadedBooks" ObjectType="{x:Type xlinq:XElement}" MethodName="Parse">
            <ObjectDataProvider.MethodParameters>
                <system:String xml:space="preserve">
<![CDATA[
<books xmlns="http://www.mybooks.com">
  <book id="0">book zero</book>
  <book id="1">book one</book>
  <book id="2">book two</book>
  <book id="3">book three</book>
</books>
]]>
                </system:String>
                <xlinq:LoadOptions>PreserveWhitespace</xlinq:LoadOptions>
            </ObjectDataProvider.MethodParameters>
        </ObjectDataProvider>

        <!-- Template for use in Books List listbox. -->
        <DataTemplate x:Key="BookTemplate">
            <StackPanel Orientation="Horizontal">
                <TextBlock Margin="3" Text="{Binding Path=Attribute[id].Value}"/>
                <TextBlock Margin="3" Text="-"/>
                <TextBlock Margin="3" Text="{Binding Path=Value}"/>
            </StackPanel>
        </DataTemplate>
    </Window.Resources>

    <!-- Main visual content container -->
    <StackPanel Background="lightblue" DataContext="{Binding Source={StaticResource LoadedBooks}}">
        <!-- Raw XML display section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">XML
            <Label.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Label.LayoutTransform>
            </Label>
            <TextBlock Name="tbRawXml" Height="200" Background="LightGray" Text="{Binding Path=Xml}" TextTrimming="CharacterEllipsis" />
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- List box to display all books section -->
        <DockPanel Margin="5">
            <Label  Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" FontWeight="Bold">Book List
                <Label.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Label.LayoutTransform>
            </Label>
            <ListBox Name="lbBooks" Height="200" Width="415" ItemTemplate ="{StaticResource BookTemplate}">
                <ListBox.ItemsSource>
                    <Binding Path="Elements[{http://www.mybooks.com}book]"/>
                </ListBox.ItemsSource>
            </ListBox>
            <Button Margin="5" DockPanel.Dock="Right" Height="30" Width ="130" Content="Remove Selected Book" Click="OnRemoveBook">
            <Button.LayoutTransform>
                <RotateTransform Angle="90"/>
            </Button.LayoutTransform>
            </Button>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Edit current selection section -->
        <DockPanel Margin="5">
            <TextBlock Margin="5" Height="30" Width="65" DockPanel.Dock="Right" Background="LightGray" TextWrapping="Wrap" TextAlignment="Center">
                    Changes are live!
                <TextBlock.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </TextBlock.LayoutTransform>
            </TextBlock>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Edit Selected Book</Label>
                <StackPanel Margin="1" DataContext="{Binding ElementName=lbBooks, Path=SelectedItem}">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="editAttributeTextBox" Width="410" Text="{Binding Path=Attribute[id].Value}">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book ID and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="editValueTextBox" Width="410" Text="{Binding Path=Value}" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Edit the selected book Value and see it changed.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>

        <Separator Height="4" Margin="5" />

        <!-- Add new book section -->
        <DockPanel Margin="5">
            <Button Margin="5" Height="30" DockPanel.Dock="Right" Click ="OnAddBook">Add Book
                <Button.LayoutTransform>
                    <RotateTransform Angle="90"/>
                </Button.LayoutTransform>
            </Button>
            <StackPanel>
                <Label Width="450" Background="Gray" FontSize="12" BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" FontWeight="Bold">Add New Book</Label>
                <StackPanel Margin="1">
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">ID:</Label>
                        <TextBox Name="tbAddID" Width="410">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="Bold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                    <StackPanel Orientation="Horizontal">
                        <Label Width="40">Value:</Label>
                        <TextBox Name="tbAddValue" Width="410" Height="25">
                            <TextBox.ToolTip>
                                <TextBlock FontWeight="UltraBold" TextAlignment="Center">
                                    <Label>Enter a book ID and Value pair, then click Add Book.</Label>
                                </TextBlock>
                            </TextBox.ToolTip>
                        </TextBox>
                    </StackPanel>
                </StackPanel>
            </StackPanel>
        </DockPanel>
    </StackPanel>
</Window>

```

### <a name="comments"></a>Komentáře

C# zdrojového kódu pro obslužné rutiny událostí související s prvky uživatelského rozhraní grafického subsystému WPF, najdete v části [L2DBForm.xaml.cs zdrojový kód](../designers/l2dbform-xaml-cs-source-code.md).

## <a name="see-also"></a>Viz také

- [Návod: Příklad LinqToXmlDataBinding](../designers/walkthrough-linqtoxmldatabinding-example.md)
- [Zdrojový kód L2DBForm.xaml.cs](../designers/l2dbform-xaml-cs-source-code.md)