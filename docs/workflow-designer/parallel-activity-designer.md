---
title: "Paralelní Návrhář aktivity | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Parallel.UI
ms.assetid: 0306dc3b-075a-4091-ac3a-96486fbabed5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 2d40a016631632ace52257d7086d4b1dca87520f
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="parallel-activity-designer"></a>Návrhář paralelní aktivity
<xref:System.Activities.Statements.Parallel> Aktivita provede kolekce aktivit podřízené současně.

## <a name="the-parallel-activity"></a>Paralelní aktivita
 <xref:System.Activities.Statements.Parallel> Aktivity ukládá jejich podřízené aktivity v <xref:System.Activities.Statements.Parallel.Branches%2A> kolekce. Použití <xref:System.Activities.Statements.Parallel> aktivity místo <xref:System.Activities.Statements.Sequence> aktivitu, pokud některé podřízené aktivity, může se stát nečinnosti.

 <xref:System.Activities.Statements.Parallel> Aktivita má <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> vlastnost, která obsahuje uživatele zadaného [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] výraz. <xref:System.Activities.Statements.Parallel> Aktivita vyhodnotí tuto vlastnost po dokončení každé větve. Pokud je vyhodnocen jako **True**, pak se <xref:System.Activities.Statements.Parallel> bez provádění ostatní větve zůstanou dokončení aktivity. Pokud <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> není vyhodnocen **True**, pak se <xref:System.Activities.Statements.Parallel> dokončení aktivity, když byly dokončeny všechny jeho podřízené aktivity.

### <a name="using-the-parallel-activity-designer"></a>Pomocí návrháře paralelní aktivita
 **Paralelní** Návrhář aktivity naleznete v **tok řízení** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů**karty na levé straně [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **Paralelní** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli návrháře aktivit jsou obvykle umístěny, například uvnitř **Pořadí** Návrhář aktivity. Po vyřazení ji do [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], vytvoří <xref:System.Activities.Statements.Parallel> aktivity, který ve výchozím nastavení obsahuje <xref:System.Activities.Activity.DisplayName%2A> z **paralelní**

 Přidat aktivitu do <xref:System.Activities.Statements.Parallel.Branches%2A> kolekce paralelní aktivity, přetáhněte některé jiné Návrhář aktivity z **sada nástrojů** na trojúhelníček uvnitř **paralelní** Návrhář aktivity. Trojúhelníčky paždíku aktivity obsažené v větve. Opakováním tohoto postupu lze přidat další aktivity. Aktivity lze přeuspořádány přetahováním myší je v rámci **paralelní** Návrhář aktivity.

### <a name="parallel-activity-properties-in-the-workflow-designer"></a>Vlastnosti paralelní aktivity v Návrháři pracovních postupů
 Následující tabulka uvádí vlastnosti paralelních aktivit a popisuje, jak se používají v návrháři.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje popisný Zobrazovaný název Návrhář aktivity v hlavičce. Výchozí hodnota je **paralelní**. Hodnota může volitelně upravena v **vlastnosti** mřížky nebo přímo v hlavičce Návrhář aktivity.|
|<xref:System.Activities.Statements.Parallel.Branches%2A>|True|Obsahuje kolekci podřízené aktivity a provést.|
|<xref:System.Activities.Statements.Parallel.CompletionCondition%2A>|False|Vyhodnocení po dokončení větev. Pokud je vyhodnocen jako **True**, pak naplánované čekající na vyřízení větví došlo ke zrušení. Pokud tato vlastnost není nastaven, nebo se vyhodnocuje **False**, když byly dokončeny všechny jeho podřízené aktivity dokončení aktivity. Výchozí hodnota je **null**.|

## <a name="see-also"></a>Viz také

- [Pořadí](../workflow-designer/sequence-activity-designer.md)
- [ParallelForEach\<T>](../workflow-designer/parallelforeach-t-activity-designer.md)
- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)