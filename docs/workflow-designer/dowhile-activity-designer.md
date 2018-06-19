---
title: Návrhář postupu provádění - DoWhile Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.DoWhile.UI
ms.assetid: 948deb35-d72f-462b-bea6-4b119c10a148
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 23588a044596ce5250cc68d01263f5d80775866a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31969975"
---
# <a name="dowhile-activity-designer"></a>Návrhář aktivity DoWhile

<xref:System.Activities.Statements.DoWhile> Aktivita provádí aktivity obsažené v jeho <xref:System.Activities.Statements.DoWhile.Body%2A> alespoň jednou, dokud je zadaná podmínka vyhodnocena jako **false**. Pokud potřebujete aktivity obsažené v těla smyčky spouštění nula nebo více dobu, použijte <xref:System.Activities.Statements.While> aktivity místo.

## <a name="dowhile-properties-in-the-workflow-designer"></a>Vlastnosti DoWhile v Návrháři pracovních postupů

V následující tabulce jsou velmi užitečné <xref:System.Activities.Statements.DoWhile> vlastnosti aktivity a popisuje, jak je používat v Návrháři:

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.DoWhile.Body%2A>|False|Aktivita provést, když je podmínka vyhodnocena jako **true**. Chcete-li přidat <xref:System.Activities.Statements.DoWhile.Body%2A> aktivity, vyřaďte aktivitu z panelu nástrojů do **textu** pole na **DoWhile** Návrhář aktivity s text nápovědy "Aktivity Sem přetáhněte".|
|<xref:System.Activities.Statements.DoWhile.Condition%2A>|Hodnota TRUE|Podmínky pro vyhodnocení po každé iteraci smyčky. Chcete-li nastavit <xref:System.Activities.Statements.DoWhile.Condition%2A>, zadejte výraz jazyka Visual Basic v **podmínku** pole na **DoWhile** aktivity návrháře nebo v tabulce vlastností.|

## <a name="see-also"></a>Viz také

- [Chvíli](../workflow-designer/while-activity-designer.md)
- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)