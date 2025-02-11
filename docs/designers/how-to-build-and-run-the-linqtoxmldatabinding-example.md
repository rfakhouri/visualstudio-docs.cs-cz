---
title: 'Postupy: Sestavení a spuštění příkladu LinqToXmlDataBinding'
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d53f8d08222eb35660f7a4454164d6b821a976d9
ms.sourcegitcommit: 5483e399f14fb01f528b3b194474778fd6f59fa6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2019
ms.locfileid: "66714831"
---
# <a name="how-to-build-and-run-the-linqtoxmldatabinding-example"></a>Postupy: Postupy: Sestavení a spuštění příkladu LinqToXmlDataBinding

Toto téma ukazuje, jak vytvořit a sestavit projekt sady Visual Studio LinqToXmlDataBinding a spuštění výsledné program příklad LinqToXmlDataBinding Windows Presentation Foundation (WPF).

Další informace o sadě Visual Studio najdete v tématu [přehled Visual Studio IDE](../get-started/visual-studio-ide.md).

## <a name="create-the-project"></a>Vytvoření projektu

1. Otevřete Visual Studio a vytvořte C# **aplikace WPF** s názvem **LinqToXmlDataBinding**.

   Projekt musí cílit na rozhraní .NET Framework 3.5 (nebo novější).

1. Pokud není již k dispozici, přidejte odkazy na projekt pro následující sestavení .NET:

    - System.Data

    - System.Data.DataSetExtensions

    - System.Xml

    - System.Xml.Linq

1. Sestavte řešení stisknutím kombinace kláves **Ctrl**+**Shift**+**B**, spusťte ji stisknutím klávesy **F5**. Projekt by měl kompilovat bez chyb a spustit jako obecná aplikace WPF.

## <a name="add-code-to-the-project"></a>Přidání kódu do projektu

1. V **Průzkumníka řešení**, přejmenujte zdrojový soubor **Window1.xaml** k **L2XDBForm.xaml**. Závislé zdrojový soubor **Window1.xaml.cs** by měl automaticky přejmenovat na **L2XDBForm.xaml.cs**.

1. Nahradit v souboru zdrojového kódu najít **L2XDBForm.xaml** s oddílem kód z tématu [zdrojový kód L2DBForm.xaml](../designers/l2dbform-xaml-source-code.md). Použijte zobrazení zdroje XAML pro práci s tímto souborem.

1. Podobně, nahraďte zdrojem **L2XDBForm.xaml.cs** s kódem v [zdrojový kód L2DBForm.xaml.cs](../designers/l2dbform-xaml-cs-source-code.md).

1. V souboru **App.xaml**, nahraďte všechny výskyty řetězce `Window1.xaml` s `L2XDBForm.xaml`.

1. Sestavte řešení stisknutím **CTRL**+**SHIFT**+**B**.

## <a name="run-the-program"></a>Spuštění programu

LinqToXmlDataBinding program umožňuje uživateli zobrazit a pracovat s seznam knihy, které se ukládá jako vložený element XML.

### <a name="to-run-the-program-and-view-the-book-list"></a>Ke spuštění programu a zobrazení seznamu knihy

Spustit LinqToXmlDataBinding stisknutím klávesy **F5** (**spustit ladění**) nebo **Ctrl**+**F5** (**Start Bez ladění**). Okno aplikace s názvem **WPF datové vazby pomocí LINQ to XML** se zobrazí.

- Všimněte si, že v horní části uživatelského rozhraní, které zobrazí nezpracovaný **XML** , která představuje seznam knihy. Zobrazí se pomocí WPF <xref:System.Windows.Controls.TextBlock> ovládací prvek, který neumožňuje interakce prostřednictvím klávesnice nebo myši.

- Druhá svislý část s názvem **Book List**, zobrazuje – knihy jako prostý text seřazený seznam. Použije <xref:System.Windows.Controls.ListBox> ovládací prvek, který umožňuje výběr ale myš či klávesnice.

### <a name="to-add-and-delete-books-from-the-list"></a>Můžete přidávat a odstraňovat knihy ze seznamu

- Nová kniha přidat do seznamu, zadejte hodnoty do **ID** a **hodnotu** <xref:System.Windows.Controls.TextBox> ovládacích prvků v poslední části **přidat nová kniha**, klikněte **přidat Kniha** tlačítko. Všimněte si, že knihy se připojí k seznamu v knihy a výpisy XML. Tento program nelze ověřit vstupní hodnoty.

- Pokud chcete odstranit existující knihu ze seznamu, vyberte ho v **Book List** části a pak klikněte na tlačítko **odebrat vybrané knihy** tlačítko. Všimněte si, že položku v seznamu se odebral z knihy a raw výpisy zdroj XML.

### <a name="to-edit-an-existing-book-entry"></a>Chcete-li upravit existující položka adresáře

1. Vyberte položku v seznamu ve druhém **Book List** oddílu. Jeho aktuální hodnoty má být zobrazen v třetí části **upravit vybrané knihy**.

1. Upravte hodnoty pomocí klávesnice. Hned <xref:System.Windows.Controls.TextBox> ovládací prvek ztratí fokus, změny se automaticky rozšíří na zdroj a knihy uvedené XML.

## <a name="see-also"></a>Viz také:

- [Datové vazby WPF pomocí LINQ na ukázkový kód XML](../designers/wpf-data-binding-using-linq-to-xml-example.md)
- [Návod: Příklad LinqToXmlDataBinding](../designers/walkthrough-linqtoxmldatabinding-example.md)
- [Visual Studio IDE – přehled](../get-started/visual-studio-ide.md)