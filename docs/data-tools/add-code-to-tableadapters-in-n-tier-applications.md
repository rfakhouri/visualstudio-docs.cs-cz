---
title: Přidávání kódu do prvků TableAdapters ve víceúrovňových aplikacích
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- TableAdapters, n-tier applications
- n-tier applications, extending TableAdapters
ms.assetid: dafac00e-df9d-4d4a-95a6-e34b4d099425
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 70c889f6cccd5605758dce05b2a0c4d405aa6714
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="add-code-to-tableadapters-in-n-tier-applications"></a>Přidávání kódu do prvků TableAdapters ve víceúrovňových aplikacích
Vytvořením souboru třídu pro TableAdapter a přidání kódu k němu můžete rozšířit funkce TableAdapter (místo přidávání kódu do *DatasetName*. Soubor DataSet.Designer). Částečné třídy povolit kód pro určité třídy rozdělit mezi několik fyzických souborů. Další informace najdete v tématu [částečné](/dotnet/visual-basic/language-reference/modifiers/partial) nebo [partial (typ)](/dotnet/csharp/language-reference/keywords/partial-type).

Kód, který definuje TableAdapter je generována pokaždé, když jsou provedeny změny TableAdapter v datové sadě. Tento kód se vygeneroval také při změně během spuštění všechny průvodce, která upraví konfiguraci TableAdapter. Chcete-li zabránit odstranění během opětovné vygenerování TableAdapter kódu, přidejte kód do souboru třídu TableAdapter.

Ve výchozím nastavení po oddělíte datovou sadu a TableAdapter kód, výsledkem je soubor diskrétní třídy v každém projektu. Původní projekt obsahuje soubor s názvem *DatasetName*. Designer.vb (nebo *DatasetName*. Designer.cs) obsahující kód TableAdapter. Projekt, který je určen v **Dataset projekt** vlastnost má soubor s názvem *DatasetName*. DataSet.Designer.vb (nebo *DatasetName*. DataSet.Designer.cs) obsahující kód datovou sadu.

> [!NOTE]
>  Když oddělíte datových sad a TableAdapters (nastavením **DataSet projekt** vlastnost), nebude automaticky přesunout existující datovou sadu částečné třídy v projektu. Existující datovou sadu částečné třídy je třeba přesunout ručně dataset projekt.

> [!NOTE]
> Datová sada poskytuje funkce pro generování <xref:System.Data.DataTable.ColumnChanging> a <xref:System.Data.DataTable.RowChanging> obslužné rutiny událostí potřeby ověření. Další informace najdete v tématu [přidání ověřování do vícevrstvé datové sady](../data-tools/add-validation-to-an-n-tier-dataset.md).

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="to-add-user-code-to-a-tableadapter-in-an-n-tier-application"></a>Přidání uživatelského kódu do TableAdapter ve vícevrstvé aplikace

1.  Najděte projekt, který obsahuje soubor XSD.

2.  Klikněte dvakrát **XSD** soubor otevřete **návrháře Dataset**.

3.  Klikněte pravým tlačítkem na TableAdapter, který chcete přidat kód pro a potom vyberte **kód zobrazení**.

     Částečné třídy se vytvoří a otevře v editoru kódu.

4.  Přidejte kód uvnitř deklarace částečné třídy.

5.  Následující příklad ukazuje, kde má být přidejte kód, který `CustomersTableAdapter` v `NorthwindDataSet`:

    ```vb
    Partial Public Class CustomersTableAdapter
        ' Add code here to add functionality
        ' to the CustomersTableAdapter.
    End Class
    ```

    ```csharp
    public partial class CustomersTableAdapter
    {
        // Add code here to add functionality
        // to the CustomersTableAdapter.
    }
    ```

## <a name="see-also"></a>Viz také

- [Přehled vícevrstvých datových aplikací](../data-tools/n-tier-data-applications-overview.md)
- [Přidávání kódu do datových sad ve vícevrstvých aplikacích](../data-tools/add-code-to-datasets-in-n-tier-applications.md)
- [Vytvoření a konfigurace TableAdapters](create-and-configure-tableadapters.md)
- [Přehled hierarchické aktualizace](hierarchical-update.md)
