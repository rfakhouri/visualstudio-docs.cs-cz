---
title: Přidání kódu do datových sad v n vrstvé aplikace | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- n-tier applications, extending datasets
ms.assetid: d43c2ccd-4902-43d8-b1a8-d10ca5d3210c
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 6c788e422ea8613b77d7d0c0460d7c026916baa3
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697156"
---
# <a name="add-code-to-datasets-in-n-tier-applications"></a>Přidávání kódu do datových sad ve vícevrstvých aplikacích
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Funkce pro datovou sadu můžete rozšířit vytvořením souboru částečné třídy datové sady a přidáním kódu k němu (místo přidání kódu *DatasetName*. Soubor Dataset.Designer). Částečné třídy povolit kód pro konkrétní třídu rozdělit mezi několik fyzických souborů. Další informace najdete v tématu [částečné](https://msdn.microsoft.com/library/7adaef80-f435-46e1-970a-269fff63b448) nebo [částečné třídy a metody](https://msdn.microsoft.com/library/804cecb7-62db-4f97-a99f-60975bd59fa1).

Kód, který definuje datovou sadu je generována pokaždé, když dojde ke změně definice datové sady. Tento kód se také vygeneruje, když provedete změny za běhu všechny průvodce, který upraví konfiguraci datové sady. Aby váš kód odstranit během obnovování datové sady, přidejte kód do souboru částečné třídy datové sady.

Ve výchozím nastavení po oddělíte datové sady a `TableAdapter` kód, výsledek je soubor samostatné třídy v každém projektu. Původní projekt má filenamed *DatasetName*. Designer.vb (nebo *DatasetName*. Designer.cs), který obsahuje `TableAdapter` kódu. Projekt, který je zadaný ve **projektu Dataset** vlastnost má soubor s názvem *DatasetName*. DataSet.Designer.vb (nebo *DatasetName*. DataSet.Designer.cs). Tento soubor obsahuje kód, datové sady.

> [!NOTE]
> Když oddělíte datové sady a `TableAdapter`s (nastavením **projektu DataSet** vlastnost), existující částečné třídy v projektu nebudou automaticky přesunuty. Existující částečné třídy datové sady je nutné ručně přesunout do projektu datové sady.

> [!NOTE]
> Když kód pro ověření musí být přidán, návrháři datových sad poskytuje funkce pro generování <xref:System.Data.DataTable.ColumnChanging> a <xref:System.Data.DataTable.RowChanging> obslužných rutin událostí. Další informace najdete v tématu [přidání ověřování do vícevrstvé datové sady](../data-tools/add-validation-to-an-n-tier-dataset.md).

## <a name="add-code-to-datasets-in-n-tier-applications"></a>Přidávání kódu do datových sad ve vícevrstvých aplikacích

1. Najděte projekt, který obsahuje soubor XSD (datová sada).

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
- [TableAdapters](https://msdn.microsoft.com/library/09416de9-134c-4dc7-8262-6c8d81e3f364)
- [TableAdapterManager Overview](https://msdn.microsoft.com/library/33076d42-6b41-491a-ac11-6c6339aea650)
- [Přehled hierarchické aktualizace](https://msdn.microsoft.com/library/c4f8e8b9-e4a5-4a02-8462-d03d1e8222d6)
- [Nástroje datových sad v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)