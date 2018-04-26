---
title: Datové vazby WPF s technologií LINQ to XML – přehled
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: 3bf80845-891b-41de-a71b-4080b5bd3ea6
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0263aba7d732c766d08bda05c6700c47d58f3d44
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="wpf-data-binding-with-linq-to-xml-overview"></a>Datové vazby WPF s technologií LINQ to XML – přehled

Toto téma představuje vazbu funkce Dynamická data v nástroji <xref:System.Xml.Linq> oboru názvů. Tyto funkce slouží jako zdroj dat pro prvky uživatelského rozhraní (UI) v aplikacích Windows Presentation Foundation (WPF). Tento scénář závisí na zvláštní *dynamické vlastnosti* z <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> a <xref:System.Xml.Linq.XElement?displayProperty=fullName>.

## <a name="xaml-and-linq-to-xml"></a>XAML a technologie LINQ to XML

Extensible aplikace Markup Language (XAML) je XML dialekt vytvořených microsoftem pro podporu technologie rozhraní .NET Framework 3.0. V grafickém subsystému WPF se používá k reprezentaci prvky uživatelského rozhraní a souvisejících funkcí, jako jsou události a datové vazby. V modelu Windows Workflow Foundation, XAML se používá k reprezentování struktura programu, jako je třeba Správa programu (*pracovních*). XAML umožňuje deklarativní aspektů technologie oddělit z související procedurální kód, který definuje více individualizovaná chování programu.

Existují dva široké způsoby, které mohou komunikovat XAML a technologie LINQ to XML:

- Protože soubory XAML jsou ve správném formátu XML, může být dotazována a s nimi manipulovat, díky technologiím XML, jako je například technologie LINQ to XML.

- Protože technologie LINQ to XML dotazy představují zdroj dat, tyto dotazy slouží jako zdroj dat pro datovou vazbu pro prvky uživatelského rozhraní grafického subsystému WPF.

Tato dokumentace popisuje druhý scénář.

## <a name="data-binding-in-the-windows-presentation-foundation"></a>Datové vazby v Windows Presentation Foundation

Datové vazby WPF umožňuje přidružit jednu ze svých vlastností zdroje dat jako element uživatelského rozhraní. Je jednoduchý příklad tohoto <xref:System.Windows.Controls.Label> jejíž text představuje hodnotu veřejná vlastnost v objektu definovaný uživatelem. Datové vazby WPF spoléhá na následující součásti:

|Součást|Popis|
|---------------|-----------------|
|Cíl vazby|Element uživatelského rozhraní pro být přidružená ke zdroji dat. Vizuální prvky v grafickém subsystému WPF jsou odvozeny od <xref:System.Windows.UIElement> třídy.|
|Vlastnost target|*Vlastnost závislosti* z vazby cíl, který odpovídá hodnotě zdroje datové vazby. Vlastnosti závislosti přímo nepodporuje <xref:System.Windows.DependencyObject> třídy, které <xref:System.Windows.UIElement> je odvozena z.|
|Zdroje vazby|Zdrojový objekt pro jednu nebo více hodnot zadaných pro element uživatelského rozhraní pro prezentaci. WPF automaticky podporuje následující typy jako vazby zdroje: CLR objekty, objekty dat ADO.NET, data XML (z technologie LINQ to XML dotazy nebo XPath) nebo jiné <xref:System.Windows.DependencyObject>.|
|Zdrojová cesta|Vlastnost zdroji vazby, který se přeloží na hodnotu nebo sadu hodnot, které má být vázána.|

Vlastnost závislosti je koncept specifické pro WPF, která představují dynamicky počítaný vlastnost prvku uživatelského rozhraní. Například vlastnosti závislosti často mají výchozí hodnoty nebo hodnoty, které jsou poskytovány nadřazený element. Tyto speciální vlastnosti jsou zajišťované instance <xref:System.Windows.DependencyProperty> – třída (a nikoli pole jako standardní vlastnostmi). Další informace najdete v tématu [přehled vlastností závislostí](/dotnet/framework/wpf/advanced/dependency-properties-overview).

### <a name="dynamic-data-binding-in-wpf"></a>Dynamické datové vazby v grafickém subsystému WPF

Ve výchozím nastavení datová vazba dojde pouze v případě, že cílový prvek uživatelského rozhraní je inicializován. To se označuje jako *jednorázové* vazby. Pro většinu účelů to není dostatečné; datové vazby řešení zpravidla vyžaduje, aby změny předány dynamicky za běhu pomocí jedné z následujících:

- *Jednosměrné* vazby způsobí, že se změny mohly rozšířit automaticky jedné straně. Nejčastěji změny zdroj se odrazí v cílové, ale naopak někdy může být užitečná.

- V *obousměrný* vazby, změny zdroje se automaticky rozšíří k cíli a změny k cíli se automaticky rozšíří zdroji.

Pro jednosměrné, nebo pomocí obousměrné vazby proběhnout, zdroj musí implementovat vhodný mechanismus oznámení změny, například implementací <xref:System.ComponentModel.INotifyPropertyChanged> rozhraní nebo pomocí *PropertyNameChanged* vzor pro každou vlastnost podporována.

Další informace o vazbě dat v grafickém subsystému WPF najdete v tématu [vazby dat (WPF)](/dotnet/framework/wpf/data/data-binding-wpf).

## <a name="dynamic-properties-in-linq-to-xml-classes"></a>Dynamické vlastnosti v technologii LINQ to XML třídy

Většina třídy LINQ to XML nemohou být jako správné WPF dynamické datové zdroje. Některé velmi užitečné informace je k dispozici pouze prostřednictvím metody, nikoli vlastnosti a vlastnosti v těchto tříd neimplementují oznámení o změnách. Pro podporu datové vazby WPF, technologie LINQ to XML zveřejňuje sadu *dynamické vlastnosti*.

Tyto dynamické vlastnosti jsou speciální běhu vlastnosti, které duplikují funkce stávajících metod a vlastností v <xref:System.Xml.Linq.XAttribute> a <xref:System.Xml.Linq.XElement> třídy. Byly přidány do těchto tříd výhradně a umožňuje jim tak, aby fungoval jako dynamické zdroje dat. pro grafický subsystém WPF. Ke splnění tohoto požadavku, implementujte tyto dynamické vlastnosti oznámení o změnách. V další části, se poskytuje podrobné referenční těchto dynamických vlastností [technologie LINQ to XML dynamické vlastnosti](../designers/linq-to-xml-dynamic-properties.md).

> [!NOTE]
> Řadu standardní veřejné vlastnosti v různých tříd v nalezen <xref:System.Xml.Linq> obor názvů, je možné pro jednorázové datovou vazbu. Nezapomeňte však, že zdrojový ani cílový bude dynamicky aktualizovat v rámci tohoto systému.

### <a name="accessing-dynamic-properties"></a>Přístup k dynamické vlastnosti

Dynamické vlastnosti v <xref:System.Xml.Linq.XAttribute> a <xref:System.Xml.Linq.XElement> třídy nelze získat přístup, jako je standardní vlastnosti. Například v kompatibilní se standardem CLR jazyků, například C#, nemohou být:

- Přistupovat přímo v době kompilace. Dynamické vlastnosti jsou neviditelná pro kompilátor a Visual Studio IntelliSense.

- Zjištěné nebo používaná v době běhu pomocí reflexe .NET. I v době běhu nejsou vlastnosti v tom smyslu, základní CLR.

V jazyce C#, dynamické vlastnosti přístupný pouze za běhu prostřednictvím zařízení, které jsou podle <xref:System.ComponentModel> oboru názvů.

Naproti tomu však ve formátu XML dynamických vlastností zdroje je přístupné prostřednictvím přehledné zápis v následující podobě:

```
<object>.<dynamic-property>
```

Dynamické vlastnosti pro tyto dvě třídy buď překládat hodnotu, která je možné přímo, nebo na indexer, který je nutné zadat s indexem získání výsledná hodnota nebo shromažďování hodnot. Druhé syntaxe má podobu:

```
<object>.<dynamic-property>[<index-value>]
```

Další informace najdete v tématu [technologie LINQ to XML dynamické vlastnosti](../designers/linq-to-xml-dynamic-properties.md).

Pokud chcete implementovat dynamické vazby WPF, se použije dynamické vlastnosti, poskytované systémem <xref:System.Windows.Data> obor názvů, zejména <xref:System.Windows.Data.Binding> třídy.

## <a name="see-also"></a>Viz také

- [Datová vazba WPF s LINQ to XML](../designers/wpf-data-binding-with-linq-to-xml-overview.md)
- [Dynamické vlastnosti LINQ to XML](../designers/linq-to-xml-dynamic-properties.md)
- [XAML ve WPF](/dotnet/framework/wpf/advanced/xaml-in-wpf)
- [Datová vazba (WPF)](/dotnet/framework/wpf/data/data-binding-wpf)
- [Pomocí značka pracovního postupu](http://go.microsoft.com/fwlink/?LinkId=98685)
