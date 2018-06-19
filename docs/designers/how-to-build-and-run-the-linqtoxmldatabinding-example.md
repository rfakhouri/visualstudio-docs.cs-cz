---
title: 'Postupy: sestavení a spuštění ukázkového LinqToXmlDataBinding'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e78665f19f4cbc62197cc8474feb1c550cc4e491
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31923797"
---
# <a name="how-to-build-and-run-the-linqtoxmldatabinding-example"></a>Postupy: sestavení a spuštění ukázkového LinqToXmlDataBinding

Toto téma ukazuje, jak vytvořte a sestavte projekt LinqToXmlDataBinding Visual Studio a jak se spustit program výsledné příklad LinqToXmlDataBinding Windows Presentation Foundation (WPF).

Další informace o sadě Visual Studio najdete v tématu [Visual Studio IDE přehled](../ide/visual-studio-ide.md).

## <a name="creating-and-populating-the-project"></a>Vytvoření a naplnění projektu

### <a name="to-create-the-starting-project"></a>K vytvoření počáteční projektu

1. Spuštění sady Visual Studio a vytvoření aplikace C# WPF s názvem LinqToXmlDataBinding. Projekt musí používat rozhraní .NET Framework 3.5 (nebo novější).

1. Pokud není přítomna, přidejte odkazy na projekt pro následující sestavení .NET:

    - System.Data

    - System.Data.DataSetExtensions

    - System.Xml

    - System.Xml.Linq

1. Sestavte řešení stisknutím **Ctrl + Shift + B**, spusťte ho stisknutím **F5**. Projekt by měl kompilovat bez chyby a spusťte jako obecná aplikace WPF.

### <a name="to-add-custom-code-to-the-project"></a>Chcete-li přidat vlastní kód do projektu

1. V Průzkumníku řešení přejmenujte zdrojový soubor Window1.xaml L2XDBForm.xaml. Závislé zdrojový soubor Window1.xaml.cs by měl být automaticky přejmenován na L2XDBForm.xaml.cs.

1. Nahraďte nachází zdrojový kód v souboru L2XDBForm.xaml s části kódu v tématu [L2DBForm.xaml zdrojový kód](../designers/l2dbform-xaml-source-code.md). Pomocí zobrazení zdroje XAML pro práci s tohoto souboru.

1. Podobně, nahraďte kód nacházející se ve zdroji v L2XDBForm.xaml.cs [L2DBForm.xaml.cs zdrojový kód](../designers/l2dbform-xaml-cs-source-code.md).

1. V souboru App.xaml nahraďte všechny výskyty řetězce "Window1.xaml" s "L2XDBForm.xaml".

1. Sestavení řešení stiskněte **Ctrl + Shift + B**.

## <a name="running-the-program"></a>Spuštění programu

LinqToXmlDataBinding program umožňuje uživatelům zobrazit a upravit seznam seznamů, která je uložena jako vložený element XML.

### <a name="to-run-the-program-and-view-the-book-list"></a>Ke spuštění programu a zobrazení seznamu adresáře

- Spustit LinqToXmlDataBinding stisknutím **F5** (**spustit ladění**) nebo **Ctrl + F5** (**spustit bez ladění**).

   Okno program s názvem **WPF datové vazby pomocí technologie LINQ to XML** se zobrazí.

- Všimněte si v horní části uživatelského rozhraní, která zobrazuje nezpracovaná **XML** představující seznamu adresáře. Zobrazí se pomocí WPF <xref:System.Windows.Controls.TextBlock> řízení, které neumožňuje interakce pomocí myši a klávesnice.

- Druhá svislý část s názvem bez přípony **seznamu adresáře**, zobrazí knihy jako prostý text seřazený seznam. Použije <xref:System.Windows.Controls.ListBox> ovládací prvek, který umožňuje výběr ale myši a klávesnice.

### <a name="to-add-and-delete-books-from-the-list"></a>Přidat a odstranit knihy ze seznamu

- Chcete-li odstranit existující knihu ze seznamu, vyberte ho v **seznamu adresáře** části a pak klikněte na **odebrat vybrané kniha** tlačítko. Všimněte si, že položku v seznamu byla odebrána z knihy a raw výpisech zdroj XML.

- K přidání nového seznamu do seznamu, zadejte hodnoty do **ID** a **hodnotu** <xref:System.Windows.Controls.TextBox> ovládací prvky v poslední části **přidat nové knihy**, klikněte **přidat Kniha** tlačítko. Všimněte si, že seznamu se připojí k seznamu v seznamu a seznamy XML. Tento program neověřuje vstupní hodnoty.

### <a name="to-edit-an-existing-book-entry"></a>Chcete-li upravit existující položku seznamu

1. Vyberte položku v seznamu za sekundu **seznamu adresáře** části. Jeho aktuální hodnoty má být zobrazena v části třetí **upravit knihu vybrané**.

1. Upravte hodnoty pomocí klávesnice. Co nejdříve buď <xref:System.Windows.Controls.TextBox> ovládací prvek ztratí fokus, změny se automaticky rozšíří seznamy XML zdroje a adresáře.

## <a name="see-also"></a>Viz také

- [Příklad datové vazby WPF pomocí LINQ to XML](../designers/wpf-data-binding-using-linq-to-xml-example.md)
- [Návod: Příklad LinqToXmlDataBinding](../designers/walkthrough-linqtoxmldatabinding-example.md)
- [Integrované vývojové prostředí sady Visual Studio – přehled](../ide/visual-studio-ide.md)