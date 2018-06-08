---
title: Přidávání ověřování do vícevrstvé datové sady
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- n-tier applications, validating
- validation [Visual Basic], n-tier data applications
- validating n-tier data applications
ms.assetid: 34ce4db6-09bb-4b46-b435-b2514aac52d3
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 81d929aaffb6f08e5e1cda1cf3329de81fe13bc8
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845402"
---
# <a name="add-validation-to-an-n-tier-dataset"></a>Přidávání ověřování do vícevrstvé datové sady
Přidání ověřování do datové sady, který je rozdělené do řešení s n vrstvá je v podstatě stejný jako přidávání ověření do datové sady jedním souborem (datové sady v jednom projektu). Navrhované umístění k provedení ověření na data je během <xref:System.Data.DataTable.ColumnChanging> nebo <xref:System.Data.DataTable.RowChanging> události dat tabulky.

 Datová sada obsahuje funkci pro vytvoření částečné třídy, na které můžete přidat uživatelský kód Změna sloupce a řádku události tabulek dat v datové sadě. Další informace o přidání kódu do datové sady v n vrstvá řešení najdete v tématu [přidávání kódu do datových sad ve víceúrovňových aplikacích](../data-tools/add-code-to-datasets-in-n-tier-applications.md), a [přidávání kódu do prvků TableAdapters ve víceúrovňových aplikacích](../data-tools/add-code-to-tableadapters-in-n-tier-applications.md). Další informace o částečné třídy najdete v tématu [postupy: rozdělení třídy na částečné třídy (návrhář tříd)](../ide/how-to-split-a-class-into-partial-classes-class-designer.md) nebo [částečné třídy a metody](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods).

> [!NOTE]
>  Když oddělíte datové sady z TableAdapters (nastavením **DataSet projekt** vlastnost), nebude automaticky přesunout existující datovou sadu částečné třídy v projektu. Existující datovou sadu částečné třídy je třeba přesunout ručně dataset projekt.

> [!NOTE]
>  Datová sada Návrhář neprovádí automatické vytváření obslužných rutin událostí v jazyce C# pro <xref:System.Data.DataTable.ColumnChanging> a <xref:System.Data.DataTable.RowChanging> události. Budete muset ručně vytvořit obslužnou rutinu události a propojte obslužné rutiny události pro základní událost. Následující postupy popisují postup vytvoření obslužné rutiny požadované událostí v jazyce Visual Basic a C#.

## <a name="validate-changes-to-individual-columns"></a>Ověřit změny jednotlivých sloupců
 Ověřte hodnoty v jednotlivých sloupcích tak, že zpracování <xref:System.Data.DataTable.ColumnChanging> událostí. <xref:System.Data.DataTable.ColumnChanging> Událost se vyvolá, když dojde k úpravě hodnotu ve sloupci. Vytvoření obslužné rutiny události pro <xref:System.Data.DataTable.ColumnChanging> událostí poklikáním na požadovaném sloupci **návrháře Dataset**.

 Při prvním dvakrát kliknete na sloupci, návrháře generuje obslužné rutiny události pro <xref:System.Data.DataTable.ColumnChanging> událostí. `If...Then` Příkaz se vytvoří také který testů pro konkrétní sloupec. Například následující kód se vygeneruje, když dvakrát kliknete **požadované datum** sloupce v tabulce Northwind objednávky:

```vb
Private Sub OrdersDataTable_ColumnChanging(ByVal sender As System.Object, ByVal e As System.Data.DataColumnChangeEventArgs) Handles Me.ColumnChanging
    If (e.Column.ColumnName = Me.RequiredDateColumn.ColumnName) Then
        ' Add validation code here.
    End If
End Sub
```

> [!NOTE]
>  V projektů C# návrháře Dataset pouze vytvoří částečné třídy pro datovou sadu a jednotlivé tabulky v datové sadě. Návrháři Dataset nevytvoří automaticky obslužné rutiny události pro <xref:System.Data.DataTable.ColumnChanging> a <xref:System.Data.DataTable.RowChanging> událostí v jazyce C# jako je tomu v jazyce Visual Basic. V jazyce C# projekty budete muset ručně vytvořit metodu pro zpracování události a propojte metody pro základní událost. Následující postup popisuje kroky k vytvoření obslužné rutiny požadované událostí v jazyce Visual Basic a C#.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

#### <a name="to-add-validation-during-changes-to-individual-column-values"></a>Přidat ověřování během změny hodnoty jednotlivých sloupců

1.  Dvojitým kliknutím otevřete datovou sadu *XSD* souboru v **Průzkumníku řešení**. Další informace najdete v tématu [návod: vytvoření datové sady v Návrháři Dataset](walkthrough-creating-a-dataset-with-the-dataset-designer.md).

2.  Dvakrát klikněte na sloupec, který chcete ověřit. Tato akce vytvoří <xref:System.Data.DataTable.ColumnChanging> obslužné rutiny události.

    > [!NOTE]
    >  Návrháři Dataset nevytvoří automaticky obslužné rutiny události pro událost jazyka C#. Kód, který je nutné ke zpracování událostí v jazyce C# je zahrnuta v další části. `SampleColumnChangingEvent` je vytvořen a pak byl zapojen až <xref:System.Data.DataTable.ColumnChanging> událost v <xref:System.Data.DataTable.EndInit%2A> metoda.

3.  Přidejte kód, který ověřte, že `e.ProposedValue` obsahuje data, která splňuje požadavky vaší aplikace. Pokud je navrhované hodnota nemůže být přijata, nastavte sloupce k určení, že obsahuje chybu.

     Následující příklad kódu ověří, jestli **množství** sloupec obsahuje hodnotu větší než 0. Pokud **množství** je menší než nebo rovna 0, sloupec je nastavený na chybu. `Else` Klauzule vymaže chybu, pokud **množství** je větší než 0. Kód obslužné rutiny události Změna sloupec by měl vypadat takto:

    ```vb
    If (e.Column.ColumnName = Me.QuantityColumn.ColumnName) Then
        If CType(e.ProposedValue, Short) <= 0 Then
            e.Row.SetColumnError(e.Column, "Quantity must be greater than 0")
        Else
            e.Row.SetColumnError(e.Column, "")
        End If
    End If
    ```
    ```csharp
    // Add this code to the DataTable partial class.

    public override void EndInit()
    {
        base.EndInit();
        // Hook up the ColumnChanging event
        // to call the SampleColumnChangingEvent method.
        ColumnChanging += SampleColumnChangingEvent;
    }

    public void SampleColumnChangingEvent(object sender, System.Data.DataColumnChangeEventArgs e)
    {
        if (e.Column.ColumnName == QuantityColumn.ColumnName)
        {
            if ((short)e.ProposedValue <= 0)
            {
                e.Row.SetColumnError("Quantity", "Quantity must be greater than 0");
            }
            else
            {
                e.Row.SetColumnError("Quantity", "");
            }
        }
    }
    ```

## <a name="validate-changes-to-whole-rows"></a>Ověřit změny celé řádky
 Ověřte hodnoty v celé řádky tak, že zpracování <xref:System.Data.DataTable.RowChanging> událostí. <xref:System.Data.DataTable.RowChanging> Událost se vyvolá, když se potvrdí hodnoty v všechny sloupce. Je nutné k ověření ve <xref:System.Data.DataTable.RowChanging> událost v případě, že hodnota v jeden sloupec závisí na hodnotě v jiný sloupec. Zvažte například OrderDate a požadované datum v tabulce objednávky v Northwind.

 Při zadání objednávek ověření zajišťuje, že pořadí není zadaný s požadované datum, který je před OrderDate. V tomto příkladu hodnoty pro požadované datum i OrderDate sloupce musí být porovnáno více, tak ověření o změnu jednotlivé sloupce nemá smysl.

 Vytvoření obslužné rutiny události pro <xref:System.Data.DataTable.RowChanging> událostí poklikáním na název tabulky v záhlaví tabulky **návrháře Dataset**.

#### <a name="to-add-validation-during-changes-to-whole-rows"></a>Přidání ověřování během změny na celé řádky

1.  Dvojitým kliknutím otevřete datovou sadu *XSD* souboru v **Průzkumníku řešení**. Další informace najdete v tématu [návod: vytvoření datové sady v Návrháři Dataset](walkthrough-creating-a-dataset-with-the-dataset-designer.md).

2.  Dvakrát klikněte na záhlaví tabulky dat v designeru.

     Částečné třídy je vytvořena s `RowChanging` obslužné rutiny události a otevře v editoru kódu.

    > [!NOTE]
    >  Návrháři Dataset nevytvoří automaticky obslužné rutiny události pro <xref:System.Data.DataTable.RowChanging> událost v projektů C#. Je nutné vytvořit metodu ke zpracování <xref:System.Data.DataTable.RowChanging> událostí a spuštění kód pak propojte událost v inicializační metoda v tabulce.

3.  Přidejte uživatelský kód uvnitř deklarace částečné třídy.

4.  Následující kód ukazuje, kde má být přidejte kód uživatele k ověřování během <xref:System.Data.DataTable.RowChanging> událostí. Příklad C# také obsahuje kód napojit obslužná rutina události až `OrdersRowChanging` událostí.

    ```vb
    Partial Class OrdersDataTable
        Private Sub OrdersDataTable_OrdersRowChanging(ByVal sender As System.Object, ByVal e As OrdersRowChangeEvent) Handles Me.OrdersRowChanging
            ' Add logic to validate columns here.
            If e.Row.RequiredDate <= e.Row.OrderDate Then
                ' Set the RowError if validation fails.
                e.Row.RowError = "Required Date cannot be on or before the OrderDate"
            Else
                ' Clear the RowError when validation passes.
                e.Row.RowError = ""
            End If
        End Sub
    End Class
    ```
    ```csharp
    partial class OrdersDataTable
    {
        public override void EndInit()
        {
            base.EndInit();
            // Hook up the event to the
            // RowChangingEvent method.
            OrdersRowChanging += RowChangingEvent;
        }

        public void RowChangingEvent(object sender, OrdersRowChangeEvent e)
        {
            // Perform the validation logic.
            if (e.Row.RequiredDate <= e.Row.OrderDate)
            {
                // Set the row to an error when validation fails.
                e.Row.RowError = "Required Date cannot be on or before the OrderDate";
            }
            else
            {
                // Clear the RowError if validation passes.
                e.Row.RowError = "";
            }
        }
    }
    ```

## <a name="see-also"></a>Viz také:

- [Přehled vícevrstvých datových aplikací](../data-tools/n-tier-data-applications-overview.md)
- [Návod: Vytvoření vícevrstvé datové aplikace](../data-tools/walkthrough-creating-an-n-tier-data-application.md)
- [Ověřování dat v datových sadách](../data-tools/validate-data-in-datasets.md)