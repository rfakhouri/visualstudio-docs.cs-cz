---
title: Návrhář postupu provádění - InvokeDelegate
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- InvokeDelegate Designer
- System.Activities.Statements.InvokeDelegate.UI
ms.assetid: 289a7498-5127-453f-beb5-05f05b80d26f
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 3d68fa1b777663ff8975f8ce99100d8eddc5f05d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="invokedelegate"></a>InvokeDelegate

**InvokeDelegate** designer se používá k vytvoření a konfigurace <xref:System.Activities.Statements.InvokeDelegate> aktivity.

## <a name="the-invokedelegate-activity"></a>InvokeDelegate aktivity

<xref:System.Activities.Statements.InvokeDelegate> Volá veřejný delegát.

### <a name="using-the-invokedelegate-activity-designer"></a>Pomocí návrháře InvokeDelegate aktivity

**InvokeDelegate** Návrhář aktivity naleznete v **primitiv** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů** kartě v Návrháři pracovních postupů (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CRTL + ALT + X.)

**InvokeDelegate** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů, kde ever aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.InvokeDelegate> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z InvokeDelegate. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **InvokeDelegate** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-invokedelegate-properties"></a>Vlastnosti InvokeDelegate

Následující tabulce je zobrazena <xref:System.Activities.Statements.InvokeDelegate> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravit v tabulce vlastností a některé můžete upravit na povrchu Designerdesigner pracovního postupu.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.InvokeDelegate> aktivity. Výchozí hodnota je InvokeDelegate.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.InvokeDelegate.Delegate%2A>|Hodnota TRUE|Název <xref:System.Activities.ActivityDelegate> volána, když aktivita provede. Tuto vlastnost lze upravit na plochu návrháře. Toto je povinná vlastnost.|
|<xref:System.Activities.Statements.InvokeDelegate.DelegateArguments%2A>|False|Argument kolekce volaný delegát. Klíče jsou názvy objektů parametr na <xref:System.Activities.ActivityDelegate> a hodnoty jsou argumenty, jejichž výrazy jsou vyhodnotit a přiřadit k objektům odpovídající parametr. V tabulce vlastností klikněte na tlačítko se třemi tečkami v **DelegateArguments** pole, zobrazuje **DelegateArguments** dialogové okno, abyste mohli tuto vlastnost nastavit. Klikněte **vytvořit Argument** pole, které chcete přidat argumenty.|

## <a name="see-also"></a>Viz také

- [Postupy: Definování a použití delegátů aktivit v návrháři postupu provádění](../workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer.md)