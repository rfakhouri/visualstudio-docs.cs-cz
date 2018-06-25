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
ms.openlocfilehash: e3d802000bede1a654b088fb80b134a36a0185be
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36758524"
---
# <a name="invokedelegate"></a>InvokeDelegate

**InvokeDelegate** designer se používá k vytvoření a konfigurace <xref:System.Activities.Statements.InvokeDelegate> aktivity.

## <a name="the-invokedelegate-activity"></a>InvokeDelegate aktivity

<xref:System.Activities.Statements.InvokeDelegate> Volá veřejný delegát.

### <a name="use-the-invokedelegate-activity-designer"></a>Použití návrháře InvokeDelegate aktivity

Přístup **InvokeDelegate** Návrhář aktivity v **primitiv** kategorii **sada nástrojů**. **InvokeDelegate** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů, kde ever aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Vyřazení Návrhář aktivity vytvoří <xref:System.Activities.Statements.InvokeDelegate> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z InvokeDelegate. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **InvokeDelegate** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-invokedelegate-properties"></a>Vlastnosti InvokeDelegate

Následující tabulce je zobrazena <xref:System.Activities.Statements.InvokeDelegate> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravit v tabulce vlastností a lze upravit některé na plochu návrháře pracovních postupů.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.InvokeDelegate> aktivity. Výchozí hodnota je InvokeDelegate.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je vhodné použít jednu.|
|<xref:System.Activities.Statements.InvokeDelegate.Delegate%2A>|Hodnota TRUE|Název <xref:System.Activities.ActivityDelegate> volána, když aktivita provede. Tuto vlastnost lze upravit na plochu návrháře a je povinný.|
|<xref:System.Activities.Statements.InvokeDelegate.DelegateArguments%2A>|False|Argument kolekce volaný delegát. Klíče jsou názvy objektů parametr na <xref:System.Activities.ActivityDelegate>, a hodnoty jsou argumenty, jejichž výrazy jsou vyhodnotit a přiřadit k objektům odpovídající parametr. Chcete-li zobrazit **DelegateArguments** dialogové okno, kde můžete nastavit tuto vlastnost, klikněte na tlačítko se třemi tečkami v **DelegateArguments** pole vlastnost mřížky. Klikněte **vytvořit Argument** pole, které chcete přidat argumenty.|

## <a name="see-also"></a>Viz také:

- [Postupy: Definování a použití delegátů aktivit v návrháři postupu provádění](../workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer.md)