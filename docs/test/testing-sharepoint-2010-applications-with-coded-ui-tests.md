---
title: Testování aplikací pro SharePoint pomocí programových testů uživatelského rozhraní v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: bafbce3a67178e10d71c2935de41c7d18709cf21
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/20/2018
ms.locfileid: "39177506"
---
# <a name="test-sharepoint-applications-with-coded-ui-tests"></a>Testování aplikací pro SharePoint pomocí programových testů uživatelského rozhraní

Zahrnutí programových testů UI v aplikaci SharePoint slouží k ověření, že celá aplikace včetně jeho ovládacích prvků uživatelského rozhraní pracuje správně. Programové testy uživatelského rozhraní můžete také ověřit, hodnoty a logiku v uživatelském rozhraní.

Další informace o výhodách používání programové testy UI, naleznete v tématu [automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md).

**Požadavky**

- Visual Studio Enterprise

## <a name="create-a-coded-ui-test-for-a-sharepoint-app"></a>Vytvořit programový test uživatelského rozhraní pro aplikace SharePoint

[Vytvoření programové testy UI](../test/use-ui-automation-to-test-your-code.md) aplikací služby SharePoint je stejné jako vytvoření testů pro ostatní typy aplikací. Záznam a přehrávání je podporován pro všechny ovládací prvky **webových úprav** rozhraní. Rozhraní pro výběr kategorie a webové části jsou všechny standardní webové ovládací prvky.

![Webové části služby SharePoint](../test/media/cuit_sharepoint.png)

> [!NOTE]
> Pokud záznam akce ověření akce před generováním kódu. Vzhledem k tomu, že existují různé chování spojené s myší najedete, je ve výchozím nastavení. Nezapomeňte odebrat redundantní ukazatele z programových testů uživatelského rozhraní. Provedete to tak, že upravíte kód testu, nebo pomocí [editoru programového testu UI](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).

## <a name="test-office-controls-within-a-sharepoint-app"></a>Ovládací prvky Office testu v rámci aplikace služby SharePoint

Pokud chcete povolit automatizaci některých webových částí office v aplikaci SharePoint, budete muset provést některé změny drobné úpravy v kódu.

> [!NOTE]
> Testování aplikace Visio a PowerPoint ovládacích prvků v aplikaci služby SharePoint není podporován.

### <a name="excel-cell-controls"></a>Ovládací prvky Excelu buňky

Zahrnout ovládací prvky Excelu buňky, je třeba provést některé změny v kódu programového testu uživatelského rozhraní.

> [!WARNING]
> Zadávání textu v libovolnou buňku aplikace Excel, za nímž následuje klíče akci šipku, nezaznamenává správně. Vyberte buňky pomocí myši.

Záznamu akce na prázdnou buňku, je třeba upravit kód, double klikněte na buňku a následnému provedením operace text nastavení. To je potřeba proto klikněte na buňku, následované žádnou akci klávesnice aktivuje `textarea` v buňce. Jednoduše záznam `setvalue` na prázdnou buňku by vyhledejte `editbox` která není k dispozici, dokud se kliklo na buňku. Příklad:

```csharp
Mouse.DoubliClick(uiItemCell,new Point(31,14));
uiGridKeyboardInputEdit.Text=value;
```

Pokud se nahrávání akcí na prázdné buňky, pak záznam získá o něco složitější, protože v okamžiku, přidejte text do buňky, nový \<div > ovládací prvek je přidán jako podřízený objekt buňky. Nové \<div > ovládací prvek obsahuje text, který jste právě zadali. Záznam je potřeba zaznamenat akce na novém \<div > ovládací prvek; ale není toho schopen, protože nový \<div > ovládací prvek neexistuje až po zadání testu. Musíte ručně provést následující změny kódu tak, aby vyhovovaly tento problém.

1. Přejděte do buňky inicializace a ujistěte se, `RowIndex` a `ColumnIndex` primární vlastnosti:

    ```csharp
    this.mUIItemCell.SearchProperties[HtmlCell.PropertyNames. RowIndex] = "3";
    this.mUIItemCell.SearchProperties[HtmlCell.PropertyNames. ColumnIndex] = "3";
    ```

2. Najít `HtmlDiv` podřízené buňky:

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

3. Přidejte kód pro myši dvakrát klikněte na akci na `HtmlDiv`:

    ```csharp
    Mouse.DoubleClick(uIItemPane, new Point(31, 14)); )
    ```

4. Přidejte kód pro nastavení na text `TextArea`:

    ```csharp
    uIGridKeyboardInputEdit.Text = value; }
    ``

## See also

- [Use UI Automation To Test Your Code](../test/use-ui-automation-to-test-your-code.md)
- [Create SharePoint Solutions](../sharepoint/create-sharepoint-solutions.md)
- [Verifying and Debugging SharePoint Code](../sharepoint/verifying-and-debugging-sharepoint-code.md)
- [Building and Debugging SharePoint Solutions](../sharepoint/building-and-debugging-sharepoint-solutions.md)
- [Profiling the Performance of SharePoint Applications](../sharepoint/profiling-the-performance-of-sharepoint-applications.md)
