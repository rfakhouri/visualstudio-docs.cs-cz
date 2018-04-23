---
title: Filtrování a řazení dat v aplikaci Windows Forms
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- row states, filtering
- data views, sorting
- row version, filtering
- row states
- data views, filtering
- sorting datasets, using data views
- dataset filtering, using data views
ms.assetid: f4f100f1-776d-46dc-b2fd-5b35b98d9561
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: ff5c31b14f13252fbcad0f42762627a14e610591
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="filter-and-sort-data-in-a-windows-forms-application"></a>Filtrování a řazení dat v aplikaci Windows Forms
Filtrování dat nastavením <xref:System.Windows.Forms.BindingSource.Filter%2A> vlastnost řetězcového výrazu, který vrací požadované záznamy.

 Řazení dat nastavením <xref:System.Windows.Forms.BindingSource.Sort%2A> vlastnost na název sloupce chcete seřadit, připojit `DESC` seřadí v sestupném pořadí nebo připojit `ASC` seřadit ve vzestupném pořadí.

> [!NOTE]
>  Pokud vaše aplikace nepoužívá <xref:System.Windows.Forms.BindingSource> součásti, můžete filtrovat a řadit data pomocí <xref:System.Data.DataView> objekty. Další informace najdete v tématu [DataView](/dotnet/framework/data/adonet/dataset-datatable-dataview/dataviews).

## <a name="to-filter-data-by-using-a-bindingsource-component"></a>K filtrování dat pomocí součásti BindingSource

-   Nastavte <xref:System.Windows.Forms.BindingSource.Filter%2A> vlastnost výrazu vracet. Například následující kód vrátí zákazníkům `CompanyName` , které začíná "B":

     [!code-csharp[VbRaddataDisplaying#6](../data-tools/codesnippet/CSharp/filter-and-sort-data-in-a-windows-forms-application_1.cs)]
     [!code-vb[VbRaddataDisplaying#6](../data-tools/codesnippet/VisualBasic/filter-and-sort-data-in-a-windows-forms-application_1.vb)]

## <a name="to-sort-data-by-using-a-bindingsource-component"></a>Řazení dat pomocí součásti BindingSource

-   Nastavte <xref:System.Windows.Forms.BindingSource.Sort%2A> vlastnost, která má sloupec, který chcete seřadit. Například následující kód seřadí zákazníkům na `CompanyName` sloupec v sestupném pořadí:

     [!code-csharp[VbRaddataDisplaying#7](../data-tools/codesnippet/CSharp/filter-and-sort-data-in-a-windows-forms-application_2.cs)]
     [!code-vb[VbRaddataDisplaying#7](../data-tools/codesnippet/VisualBasic/filter-and-sort-data-in-a-windows-forms-application_2.vb)]

## <a name="see-also"></a>Viz také

- [Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)