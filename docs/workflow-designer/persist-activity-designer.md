---
title: Návrhář postupu provádění - zachovat Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Persist.UI
ms.assetid: be8648dd-3eb9-4a50-8ec1-57a8be804692
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 04c7989f5cc37ec295f9fa778f2120dd372fd99a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="persist-activity-designer"></a>Zachovat Návrhář aktivity

**Zachovat** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Persist> aktivity.

## <a name="the-persist-activity"></a>Zachovat aktivity

<xref:System.Activities.Statements.Persist> Aktivity uloží pracovní postup na disk, pokud je to možné. <xref:System.Activities.Statements.Persist> Aktivitu nelze provést v zóně bez trvalost jako je například uvnitř <xref:System.Activities.Statements.TransactionScope> aktivity. Pokud použijete <xref:System.Activities.Statements.Persist> aktivity v jiných trvalost oboru, je vyvolána výjimka za běhu.

### <a name="using-the-persist-activity-designer"></a>Pomocí zachovat Návrhář aktivity

**Zachovat** Návrhář aktivity naleznete v **Runtime** kategorii **sada nástrojů**, který přistupuje kliknutím **sada nástrojů** Karta (případně vyberte možnost **sada nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

**Zachovat** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů bez ohledu na aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Persist> aktivitu výchozí **DisplayName** trvalého. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **zachovat** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-persist-properties"></a>Zachovat vlastnosti

Následující tabulce je zobrazena <xref:System.Activities.Statements.Persist> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravit v tabulce vlastností a některá z nich můžete upravit na plochu návrháře pracovních postupů.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.Persist> aktivity. Výchozí hodnota je zachovat. I když zobrazovaný název není nezbytně nutné, je osvědčeným postupem použít zobrazovaný název.|

## <a name="see-also"></a>Viz také

- [Modul runtime](../workflow-designer/runtime-activity-designers.md)
- [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)