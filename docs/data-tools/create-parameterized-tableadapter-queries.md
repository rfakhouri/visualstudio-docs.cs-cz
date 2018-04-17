---
title: Vytváření parametrizovaných dotazů TableAdapter | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], TableAdapters
- TableAdapters, parameterized queries
- data [Visual Studio], searching data
- queries [Visual Studio], creating
- TableAdapters, searching data
- queries [Visual Studio], TableAdapters
ms.assetid: 104d1d19-b5a9-4071-b81e-1b3af08e9c7b
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 361bb7f9acea5d07283b63cb1b3b1b97bb495a8e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="create-parameterized-tableadapter-queries"></a>Vytváření parametrizovaných dotazů TableAdapter
Zadání parametrizovaného dotazu vrátí data, která splňuje podmínky klauzule WHERE v dotazu. Například můžete parametrizovat seznam zákazníků k zobrazení pouze zákazníků v určitém městě přidáním `WHERE City = @City` na konec příkazu SQL, který vrátí seznam zákazníků.  
  
 Vytváření parametrizovaných dotazů TableAdapter v **návrháře Dataset**. Můžete také vytvořit v aplikaci Windows s **Parametrizace zdroj dat** příkaz na **Data** nabídky. **Parametrizace zdroj dat** příkaz vytvoří ovládacích prvků do formuláře, kde můžete zadat hodnoty parametrů a spusťte dotaz.  
  
> [!NOTE]
>  Při vytváření parametrizovaného dotazu, použijte parametr zápis, která je specifická pro databázi, kterou jste kódování proti. Například přístup a OleDb zdroje dat použít znaky otazníku '?' k označení parametrů, takže klauzule WHERE bude vypadat takto: `WHERE City = ?`.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídky, které vidíte, se může lišit od těch popsaných v nápovědě, v závislosti na nastavení aktivní nebo edici, kterou používáte. Chcete-li změnit nastavení, přejděte na **nástroje** nabídku a vyberte **nastavení importu a exportu**. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="create-a-parameterized-tableadapter-query"></a>Vytvoření parametrického dotazu TableAdapter  
  
#### <a name="to-create-a-parameterized-query-in-the-dataset-designer"></a>Vytvoření parametrického dotazu v Návrháři Dataset  
  
-   Vytvořte nový TableAdapter, přidáte klauzuli WHERE se požadované parametry do příkazu SQL. Další informace najdete v tématu [vytvořit a nakonfigurovat TableAdapters](../data-tools/create-and-configure-tableadapters.md).  
  
     -nebo-  
  
-   Přidejte dotaz do existující TableAdapter, přidáte klauzuli WHERE se požadované parametry do příkazu SQL.
  
#### <a name="to-create-a-parameterized-query-while-designing-a-data-bound-form"></a>Vytvoření parametrického dotazu při návrhu formuláře vázané na data  
  
1.  Vyberte ovládací prvek na formuláři, který je již vázána na datovou sadu. Další informace najdete v tématu [vazby Windows Forms – ovládací prvky k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md).  
  
2.  Na **Data** nabídce vyberte možnost **přidat dotazu**.  
  
3.  Dokončení **Tvůrce kritérií vyhledávání** dialogové okno, přidáte klauzuli WHERE se požadované parametry do příkazu SQL.  
  
### <a name="to-add-a-query-to-an-existing-data-bound-form"></a>Přidání dotazu do existujícího formuláře vázané na data  
  
1.  Otevřete formulář v **Návrhář formulářů Windows**.  
  
2.  Na **Data** nabídce vyberte možnost **přidat dotazu** nebo **inteligentních značek Data**.  
  
    > [!NOTE]
    >  Pokud **přidat dotazu** není k dispozici na **Data** nabídky, vyberte ovládací prvek na formuláři, zobrazí zdroj dat, které chcete přidat Parametrizace k. Například, pokud formulář zobrazuje data <xref:System.Windows.Forms.DataGridView> řídit, vyberte ji. Pokud formuláře zobrazí data v jednotlivých ovládacích prvků, vyberte všechny ovládací prvky vázané na data.  
  
3.  V **vyberte data zdrojová tabulka** oblasti, vyberte tabulku, která chcete přidat Parametrizace k.  
  
4.  Zadejte název do **nový název dotazu** pole, pokud vytváříte nový dotaz.  
  
     -nebo-  
  
     Vybrat v dotazu **název dotazu existující** pole.  
  
5.  V **Text dotazu** zadejte dotaz, který používá parametry.  
  
6.  Vyberte **OK**.  
  
     Ovládací prvek pro vstupní parametr a **zatížení** tlačítko jsou přidány do formuláře v <xref:System.Windows.Forms.ToolStrip> ovládacího prvku.  
  
#### <a name="querying-for-null-values"></a>Dotazování pro hodnoty null  
TableAdapter parametry můžete přiřadit hodnoty null, pokud chcete zadat dotaz na záznamy, které nemají aktuální hodnotu. Zvažte například následující dotaz, který má `ShippedDate` parametr v jeho `WHERE` klauzule:  
  
 ```sql
SELECT CustomerID, OrderDate, ShippedDate  
FROM Orders  
WHERE (ShippedDate = @ShippedDate) OR (ShippedDate IS NULL)
```  
  
 Pokud to byly dotazů v TableAdapter, můžete dotazovat pro všechny příkazy, které byly dodány s následujícím kódem:  
  
 [!code-csharp[VbRaddataTableAdapters#8](../data-tools/codesnippet/CSharp/create-parameterized-tableadapter-queries_1.cs)]
 [!code-vb[VbRaddataTableAdapters#8](../data-tools/codesnippet/VisualBasic/create-parameterized-tableadapter-queries_1.vb)]  

 Chcete-li povolit dotaz tak, aby přijímal hodnoty null:

1.  V **návrháře Dataset**, vyberte TableAdapter dotaz, který je potřeba přijmout parametr null hodnoty.  
  
2.  V **vlastnosti** vyberte **parametry**, pak klikněte na tlačítko se třemi tečkami (**...** ) tlačítko Otevřít **Editor kolekce parametrů**.  
  
3.  Vyberte parametr, který povoluje hodnoty null a nastavte **AllowDbNull** vlastnost `true`.  
  
## <a name="see-also"></a>Viz také  
 [Vyplnění datové sady s použitím objektů TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md)