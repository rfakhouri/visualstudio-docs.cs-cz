---
title: Přidávání kódu do datových sad ve vícevrstvých aplikacích
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- n-tier applications, extending datasets
ms.assetid: d43c2ccd-4902-43d8-b1a8-d10ca5d3210c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: dbd65c5247a82f2a58a57e50402ecde5d330cc9b
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60111685"
---
# <a name="add-code-to-datasets-in-n-tier-applications"></a>Přidávání kódu do datových sad ve vícevrstvých aplikacích
Funkce pro datovou sadu můžete rozšířit vytvořením souboru částečné třídy datové sady a přidáním kódu k němu (místo přidání kódu *DatasetName*. Soubor Dataset.Designer). Částečné třídy povolit kód pro konkrétní třídu rozdělit mezi několik fyzických souborů. Další informace najdete v tématu [částečné](/dotnet/visual-basic/language-reference/modifiers/partial) nebo [částečné třídy a metody](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods).

Kód, který definuje datovou sadu je generována pokaždé, když dojde ke změně definice datové sady (v typové datové sady). Tento kód se také vygeneruje, když provedete změny za běhu všechny průvodce, který upraví konfiguraci datové sady. Aby váš kód odstranit během obnovování datové sady, přidejte kód do souboru částečné třídy datové sady.

Ve výchozím nastavení po oddělíte datové sady a kód třídy TableAdapter, výsledkem je soubor samostatné třídy v každém projektu. Původní projekt obsahuje soubor s názvem *DatasetName.Designer.vb* (nebo *DatasetName.Designer.cs*), která obsahuje kód objektu TableAdapter. Projekt, který je zadaný ve **projektu Dataset** vlastnost má soubor s názvem *DatasetName.DataSet.Designer.vb* (nebo *DatasetName.DataSet.Designer.cs*) . Tento soubor obsahuje kód, datové sady.

> [!NOTE]
>  Když oddělíte datové sady a objekty TableAdapter (nastavením **projektu DataSet** vlastnost), existující částečné třídy v projektu nebudou automaticky přesunuty. Existující částečné třídy datové sady je nutné ručně přesunout do projektu datové sady.

> [!NOTE]
>  Když kód pro ověření musí být přidán, typový dataset poskytuje funkce pro generování <xref:System.Data.DataTable.ColumnChanging> a <xref:System.Data.DataTable.RowChanging> obslužných rutin událostí. Další informace najdete v tématu [přidání ověřování do vícevrstvé datové sady](../data-tools/add-validation-to-an-n-tier-dataset.md).

## <a name="to-add-code-to-datasets-in-n-tier-applications"></a>Přidání kódu do datových sad v n vrstvé aplikace

1. Najít projekt, který obsahuje *XSD* souboru.

2. Vyberte **XSD** soubor otevřete datovou sadu.

3. Klikněte pravým tlačítkem na tabulky dat, ke kterému chcete přidat kód (název tabulky v záhlaví okna) a pak vyberte **zobrazit kód**.

     Částečné třídy se vytvoří a otevře v editoru kódu.

4. Přidejte kód do částečné deklarace třídy.

     Následující příklad ukazuje, kde přidat kód CustomersDataTable v NorthwindDataSet:

    ```vb
    Partial Public Class CustomersDataTable
        ' Add code here to add functionality
        ' to the CustomersDataTable.
    End Class
    ```

    ```csharp
    partial class CustomersDataTable
    {
        // Add code here to add functionality
        // to the CustomersDataTable.
    }
    ```

## <a name="see-also"></a>Viz také:

- [Přehled vícevrstvých datových aplikací](../data-tools/n-tier-data-applications-overview.md)
- [Přidávání kódu do objektů TableAdapter ve vícevrstvých aplikacích](../data-tools/add-code-to-tableadapters-in-n-tier-applications.md)
- [Vytvoření a konfigurace objektů TableAdapter](create-and-configure-tableadapters.md)
- [Přehled hierarchické aktualizace](hierarchical-update.md)
- [Nástroje datových sad v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)