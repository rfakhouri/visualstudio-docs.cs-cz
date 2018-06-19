---
title: L2DBForm.XAML.cs zdrojového kódu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: sample
ms.assetid: 5a40dad3-6763-4576-b3ad-874df3f2c8d9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 793e1cbe4c03cb5ddfec51d583437a9b5294fbd2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31926054"
---
# <a name="l2dbformxamlcs-source-code"></a>L2DBForm.XAML.cs zdrojového kódu

Toto téma obsahuje obsah a popis C# zdrojový kód v souboru L2DBForm.xaml.cs. L2XDBForm třídu obsažené v tomto souboru je možné rozdělit do tří logických částí: datové členy a `OnRemove` a `OnAddBook` obslužné rutiny události kliknutí na tlačítko.

## <a name="data-members"></a>Datové členy

Dva členové privátní data se používají k přidružení této třídy lze použít v L2DBForm.xaml prostředky okno.

-   Obor názvů proměnná `myBooks` je inicializováno `"http://www.mybooks.com"`.

-   Člen `bookList` je inicializován v konstruktoru CDATA řetězec v L2DBForm.xaml tento řádek:

    ```
    bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
    ```

## <a name="onaddbook-event-handler"></a>Obslužné rutiny události OnAddBook

Tato metoda obsahuje následující tři příkazy:

-   První příkaz podmíněného slouží k ověření vstupu.

-   Druhý příkaz vytvoří novou <xref:System.Xml.Linq.XElement> z řetězce hodnoty zadané uživatelem v **přidat nové knihy** části uživatelské rozhraní (UI).

-   Poslední příkaz přidá tento nový element adresáře ke zprostředkovateli dat v L2DBForm.xaml. V důsledku toho se dynamické datová vazba automaticky aktualizuje uživatelské rozhraní s touto novou položkou; žádné velmi kód uživatele je povinný.

## <a name="onremove-event-handler"></a>Obslužné rutiny události OnRemove

`OnRemove` Obslužná rutina je složitější než `OnAddBook` obslužná rutina dvou důvodů. Protože původní XML obsahuje zachovaných prázdné znaky, odpovídající vložení znaků newline musí také být nejprve odebrány s položku v seznamu. Výběr, která byla odstraněné položky, druhý pro potřeby se resetuje předchozímu v seznamu.

Základní pracovní položce vybrané knihy odebrání ale provádí pouze dva příkazy:

-   Nejprve je načíst prvek knihy spojené s aktuálně vybrané položky v seznamu:

    ```
    XElement selBook = (XElement)lbBooks.SelectedItem;
    ```

-   Tento element je neodstraní z poskytovatele dat:

    ```
    selBook.Remove();
    ```

Znovu dynamické datová vazba zaručuje, že programu rozhraní automaticky aktualizováno.

## <a name="example"></a>Příklad

### <a name="code"></a>Kód

```csharp
using System;
using System.Linq;
using System.Collections;
using System.Collections.Generic;
using System.Diagnostics;
using System.Text;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Input;
using System.Xml;
using System.Xml.Linq;

namespace LinqToXmlDataBinding {
    /// <summary>
    /// Interaction logic for L2XDBForm.xaml
    /// </summary>

    public partial class L2XDBForm : System.Windows.Window
    {
        XNamespace mybooks = "http://www.mybooks.com";
        XElement bookList;

        public L2XDBForm()
        {
            InitializeComponent();
            bookList = (XElement)((ObjectDataProvider)Resources["LoadedBooks"]).Data;
        }

        void OnRemoveBook(object sender, EventArgs e)
        {
            int index = lbBooks.SelectedIndex;
            if (index < 0) return;

            XElement selBook = (XElement)lbBooks.SelectedItem;
            //Get next node before removing element.
            XNode nextNode = selBook.NextNode;
            selBook.Remove();

            //Remove any matching newline node.
            if (nextNode != null && nextNode.ToString().Trim().Equals(""))
            { nextNode.Remove(); }

            //Set selected item.
            if (lbBooks.Items.Count > 0)
            {  lbBooks.SelectedItem = lbBooks.Items[index > 0 ? index - 1 : 0]; }
        }

        void OnAddBook(object sender, EventArgs e)
        {
            if (String.IsNullOrEmpty(tbAddID.Text) ||
                String.IsNullOrEmpty(tbAddValue.Text))
            {
                MessageBox.Show("Please supply both a Book ID and a Value!", "Entry Error!");
                return;
            }
            XElement newBook = new XElement(
                                mybooks + "book",
                                new XAttribute("id", tbAddID.Text),
                                tbAddValue.Text);
            bookList.Add("  ", newBook, "\r\n");
        }
    }
}

```

### <a name="comments"></a>Komentáře

Související zdroje XAML pro tyto obslužné rutiny, najdete v části [L2DBForm.xaml zdrojový kód](../designers/l2dbform-xaml-source-code.md).

## <a name="see-also"></a>Viz také

- [Návod: Příklad LinqToXmlDataBinding](../designers/walkthrough-linqtoxmldatabinding-example.md)
- [Zdrojový kód L2DBForm.xaml](../designers/l2dbform-xaml-source-code.md)