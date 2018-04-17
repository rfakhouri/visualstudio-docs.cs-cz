---
title: Testování aplikací služby SharePoint pomocí programových testů uživatelského rozhraní v sadě Visual Studio | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 0ed08d82e186f83b71a01dab0b267410fde7267d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="test-sharepoint-applications-with-coded-ui-tests"></a>Testování aplikací služby SharePoint pomocí uživatelského rozhraní programových testů

Včetně programové testy uživatelského rozhraní v aplikaci SharePoint umožňuje ověřit, zda je správně funguje celou aplikaci, včetně jeho ovládacích prvků uživatelského rozhraní. Programové testy uživatelského rozhraní můžete také ověřit, hodnoty a logiku v uživatelském rozhraní.

Další informace o výhodách pomocí programových testů uživatelského rozhraní, najdete v části [automatizace uživatelského rozhraní použijte k testování kódu](../test/use-ui-automation-to-test-your-code.md).

**Požadavky**

- Visual Studio Enterprise

## <a name="create-a-coded-ui-test-for-a-sharepoint-app"></a>Vytvoření programového testu uživatelského rozhraní pro aplikaci služby SharePoint

[Vytváření programové testy uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md) pro vaše aplikace služby SharePoint je stejný jako vytváření testů pro jiné typy aplikací. Záznam a přehrávání jsou podporovány pro všechny ovládací prvky v rozhraní Web úpravy. Rozhraní pro výběr kategorie a webové části jsou všechny standardní ovládací prvky.

![Webové části služby SharePoint](../test/media/cuit_sharepoint.png)

> [!NOTE]
> Pokud nahráváte akce, ověření akce před generování kódu. Vzhledem k tomu, že existují různé chování přidružené hover myš, je ve výchozím nastavení. Pečlivě redundantní umístění ukazatele odebrání programové testy uživatelského rozhraní. To provedete tak, že upravíte kód pro test, nebo pomocí [programového Editor testů uživatelského rozhraní](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).

## <a name="test-office-controls-within-a-sharepoint-app"></a>Ovládací prvky Office testu v rámci aplikace SharePoint

Jak povolit automatizaci pro některé webové části office ve vaší aplikaci služby SharePoint, budete muset provést některé změny menší kódu.

> [!NOTE]
> Testování aplikace Visio a PowerPoint ovládací prvky v aplikaci SharePoint není podporována.

### <a name="excel-cell-controls"></a>Ovládací prvky aplikace Excel buňky

Zahrnout ovládací prvky aplikace Excel buněk, je nutné provést některé změny v kódu programového testu uživatelského rozhraní.

> [!WARNING]
> Zadávání textu v libovolnou buňku aplikace Excel, následuje klíče akce šipku, nezaznamenává správně. Výběr buněk pomocí myši.

Záznamu akcí na prázdné buňky, je třeba upravit kód double klepnutím na buňku a následnému provedením operace set text. To je nutné, protože se aktivuje a klikněte na buňku následuje žádnou akci klávesnice `textarea` v rámci buňky. Jednoduše zaznamenávání `setvalue` na prázdné buňky by Hledat `editbox` které není přítomno, dokud klepnutí na buňky. Příklad:

```csharp
Mouse.DoubliClick(uiItemCell,new Point(31,14));
uiGridKeyboardInputEdit.Text=value;
```

Pokud jsou zaznamenávání akcí v buňce není prázdná, pak záznam získá trochu složitější, protože v okamžiku přidat text buňky s hodnotou, nový \<div > ovládací prvek přidán jako podřízená položka buňky. Nové \<div > ovládací prvek obsahuje text, který jste právě zadali. Záznam musí zaznamenat akce na novém \<div > řízení; však nelze protože nové \<div > ovládací prvek neexistuje až po zadání test. Musíte ručně proveďte následující změny kódu pro uložení tohoto problému.

1. Přejděte do buňky inicializace a ujistěte se, `RowIndex` a `ColumnIndex` primární vlastnosti:

    ```csharp
    this.mUIItemCell.SearchProperties[HtmlCell.PropertyNames. RowIndex] = "3";
    this.mUIItemCell.SearchProperties[HtmlCell.PropertyNames. ColumnIndex] = "3";
    ```

2. Najít `HtmlDiv` podřízená položka buňky:

    ```csharp
    private UITestControl getControlToDoubleClick(HtmlCell cell)
    {
         if (String.IsNullOrEmpty(cell.InnerText)) return cell;
         HtmlDiv pane = new HtmlDiv(cell);
         pane.FilterProperties[HtmlDiv.PropertyNames.InnerText] = cell.InnerText;
         // Class is an important property in finding pane
         pane.FilterProperties[HtmlDiv.PropertyNames.Class] = "cv-nwr";
         UITestControlCollection panes = pane.FindMatchingControls();
         return panes[0];
    }
    ```

3. Přidat kód pro myš dvakrát klikněte na akci na `HtmlDiv`:

    ```csharp
    Mouse.DoubleClick(uIItemPane, new Point(31, 14)); )
    ```

4. Přidejte kód pro nastavení text na `TextArea`:

    ```csharp
    uIGridKeyboardInputEdit.Text = value; }
    ``

## See also

- [Use UI Automation To Test Your Code](../test/use-ui-automation-to-test-your-code.md)
- [Create SharePoint Solutions](/office-dev/office-dev/create-sharepoint-solutions)
- [Verifying and Debugging SharePoint Code](/office-dev/office-dev/verifying-and-debugging-sharepoint-code)
- [Building and Debugging SharePoint Solutions](/office-dev/office-dev/building-and-debugging-sharepoint-solutions)
- [Profiling the Performance of SharePoint Applications](/office-dev/office-dev/profiling-the-performance-of-sharepoint-applications)
