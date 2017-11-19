---
title: "Přidání kódu do datových sad ve víceúrovňových aplikacích | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: n-tier applications, extending datasets
ms.assetid: d43c2ccd-4902-43d8-b1a8-d10ca5d3210c
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 26dd5500f50b185c31809d9882e03e56541a567a
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="add-code-to-datasets-in-n-tier-applications"></a>Přidání kódu do datových sad ve víceúrovňových aplikacích
Vytvoření souboru třídu pro datovou sadu a přidání kódu k němu můžete rozšířit funkce datové sady (místo přidávání kódu do *DatasetName*. Soubor Dataset.Designer). Částečné třídy povolit kód pro určité třídy rozdělit mezi několik fyzických souborů. Další informace najdete v tématu [částečné](/dotnet/visual-basic/language-reference/modifiers/partial) nebo [částečné třídy a metody](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods).  
  
Kód, který určuje datovou sadu je generována pokaždé, když jsou provedeny změny definice datové sady (v typové datové sady). Tento kód také vygeneruje, když provedete změny během spuštění všechny průvodce, který upraví konfiguraci datové sady. Abyste zabránili kódu odstraňuje během obnovování datové sady, přidejte kód do souboru třídu datovou sadu.  
  
Ve výchozím nastavení po oddělíte datovou sadu a TableAdapter kód, výsledkem je soubor diskrétní třídy v každém projektu. Původní projekt obsahuje soubor s názvem *DatasetName*. Designer.vb (nebo *DatasetName*. Designer.cs) obsahující kód TableAdapter. Projekt, který je určen v **Dataset projekt** vlastnost má souboru, který je pojmenován *DatasetName*. DataSet.Designer.vb (nebo *DatasetName*. DataSet.Designer.cs). Tento soubor obsahuje kód pro datovou sadu.  
  
> [!NOTE]
>  Když oddělíte datových sad a TableAdapters (nastavením **DataSet projekt** vlastnost), nebude automaticky přesunout existující datovou sadu částečné třídy v projektu. Částečné třídy existující datovou sadu musí ručně přesunout do projektu datovou sadu.  
  
> [!NOTE]
>  Při ověření kód musí být přidán, typové datové sady poskytuje funkce pro generování <xref:System.Data.DataTable.ColumnChanging> a <xref:System.Data.DataTable.RowChanging> obslužné rutiny událostí. Další informace najdete v tématu [přidání ověřování do vícevrstvé datové sady](../data-tools/add-validation-to-an-n-tier-dataset.md).  
  
## <a name="to-add-code-to-datasets-in-n-tier-applications"></a>Přidání kódu do datových sad ve víceúrovňových aplikacích  
  
1.  Najděte projekt, který obsahuje soubor XSD. 
  
2.  Vyberte **XSD** soubor otevřete datovou sadu.  
  
3.  Klikněte pravým tlačítkem na datová tabulka, do které chcete přidat kód (název tabulky v záhlaví) a potom vyberte **kód zobrazení**.  
  
     Částečné třídy se vytvoří a otevře v editoru kódu.  
  
4.  Přidejte kód uvnitř deklarace částečné třídy.  
  
     Následující příklad ukazuje, kde přidávání kódu do CustomersDataTable v NorthwindDataSet:  
  
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
  
## <a name="see-also"></a>Viz také
[Přehled vícevrstvých datových aplikací](../data-tools/n-tier-data-applications-overview.md)   
[Přidávání kódu do prvků TableAdapters ve víceúrovňových aplikacích](../data-tools/add-code-to-tableadapters-in-n-tier-applications.md)  
[Vytvoření a konfigurace TableAdapters](create-and-configure-tableadapters.md)  
[Přehled hierarchické aktualizace](hierarchical-update.md)     
[Datové sady nástrojů v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)