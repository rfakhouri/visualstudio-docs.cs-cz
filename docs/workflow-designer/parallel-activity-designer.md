---
title: Návrhář postupu provádění – Návrhář paralelní aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Parallel.UI
ms.assetid: 0306dc3b-075a-4091-ac3a-96486fbabed5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c2315c27bc0a35ac1dc839b5fd98003105d92bd4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="parallel-activity-designer"></a>Návrhář paralelní aktivity

<xref:System.Activities.Statements.Parallel> Aktivita provede kolekce aktivit podřízené současně.

## <a name="the-parallel-activity"></a>Paralelní aktivita

<xref:System.Activities.Statements.Parallel> Aktivity ukládá jejich podřízené aktivity v <xref:System.Activities.Statements.Parallel.Branches%2A> kolekce. Použití <xref:System.Activities.Statements.Parallel> aktivity místo <xref:System.Activities.Statements.Sequence> aktivitu, pokud některé podřízené aktivity, může se stát nečinnosti.

<xref:System.Activities.Statements.Parallel> Aktivita má <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> vlastnost, která obsahuje jméno uživatele zadaný výraz jazyka Visual Basic. <xref:System.Activities.Statements.Parallel> Aktivita vyhodnotí tuto vlastnost po dokončení každé větve. Pokud je vyhodnocen jako **True**, pak se <xref:System.Activities.Statements.Parallel> bez provádění ostatní větve zůstanou dokončení aktivity. Pokud <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> není vyhodnocen **True**, pak se <xref:System.Activities.Statements.Parallel> dokončení aktivity, když byly dokončeny všechny jeho podřízené aktivity.

### <a name="using-the-parallel-activity-designer"></a>Pomocí návrháře paralelní aktivita

**Paralelní** Návrhář aktivity naleznete v **tok řízení** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**karty na levé straně návrháře pracovních postupů (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

**Paralelní** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na návrháře aktivit jsou obvykle umístěny, například uvnitř **Pořadí** Návrhář aktivity. Po vyřazení ho do návrháře pracovních postupů, vytvoří <xref:System.Activities.Statements.Parallel> aktivity, který ve výchozím nastavení obsahuje <xref:System.Activities.Activity.DisplayName%2A> z **paralelní**

Přidat aktivitu do <xref:System.Activities.Statements.Parallel.Branches%2A> kolekce paralelní aktivity, přetáhněte některé jiné Návrhář aktivity z **sada nástrojů** na trojúhelníček uvnitř **paralelní** Návrhář aktivity. Trojúhelníčky paždíku aktivity obsažené v větve. Opakováním tohoto postupu lze přidat další aktivity. Aktivity lze přeuspořádány přetahováním myší je v rámci **paralelní** Návrhář aktivity.

### <a name="parallel-activity-properties-in-the-workflow-designer"></a>Vlastnosti paralelní aktivity v Návrháři pracovních postupů

Následující tabulka uvádí vlastnosti paralelních aktivit a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje popisný Zobrazovaný název Návrhář aktivity v hlavičce. Výchozí hodnota je **paralelní**. Hodnota může volitelně upravena v **vlastnosti** mřížky nebo přímo v hlavičce Návrhář aktivity.|
|<xref:System.Activities.Statements.Parallel.Branches%2A>|Hodnota TRUE|Obsahuje kolekci podřízené aktivity a provést.|
|<xref:System.Activities.Statements.Parallel.CompletionCondition%2A>|False|Vyhodnocení po dokončení větev. Pokud je vyhodnocen jako **True**, pak naplánované čekající na vyřízení větví došlo ke zrušení. Pokud tato vlastnost není nastaven, nebo se vyhodnocuje **False**, když byly dokončeny všechny jeho podřízené aktivity dokončení aktivity. Výchozí hodnota je **null**.|

## <a name="see-also"></a>Viz také

- [Pořadí](../workflow-designer/sequence-activity-designer.md)
- [ParallelForEach\<T>](../workflow-designer/parallelforeach-t-activity-designer.md)
- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)