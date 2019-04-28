---
title: InvokeDelegate | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- InvokeDelegate Designer
- System.Activities.Statements.InvokeDelegate.UI
ms.assetid: 289a7498-5127-453f-beb5-05f05b80d26f
caps.latest.revision: 3
author: steved0x
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 30281d8cd5d5ed94ed89a980006f9618292a778d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62951967"
---
# <a name="invokedelegate"></a>InvokeDelegate

**InvokeDelegate** Návrhář slouží k vytvoření a konfigurace <xref:System.Activities.Statements.InvokeDelegate> aktivity.

## <a name="the-invokedelegate-activity"></a>Aktivita InvokeDelegate

<xref:System.Activities.Statements.InvokeDelegate> Volá veřejný delegát.

### <a name="using-the-invokedelegate-activity-designer"></a>Pomocí návrháře aktivit InvokeDelegate

**InvokeDelegate** návrháře aktivit najdete v **primitiv** kategorii **nástrojů**, který přistupuje po kliknutí **nástrojů** kartu [!INCLUDE[wfd2](../includes/wfd2-md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CRTL + ALT + X.)

**InvokeDelegate** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřazené k [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface kde někdy aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.InvokeDelegate> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> z InvokeDelegate. <xref:System.Activities.Activity.DisplayName%2A> Můžete upravovat v záhlaví **InvokeDelegate** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-invokedelegate-properties"></a>Vlastnosti InvokeDelegate

Následující tabulka ukazuje <xref:System.Activities.Statements.InvokeDelegate> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti můžete upravit v mřížce vlastností a některé možné upravovat ve [!INCLUDE[wfd2](../includes/wfd2-md.md)]návrhové ploše.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.InvokeDelegate> aktivity. Výchozí hodnota je InvokeDelegate.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|
|<xref:System.Activities.Statements.InvokeDelegate.Delegate%2A>|Pravda|Název <xref:System.Activities.ActivityDelegate> se volá, když tato aktivity spustí. Tato vlastnost se dá upravit na plochu návrháře. Toto je povinná.|
|<<xref:System.Activities.Statements.InvokeDelegate.DelegateArguments%2A>|False|Argument kolekce volaný delegát. Klíče jsou názvy <xref:System.Activities.DelegateArgument> objektů <xref:System.Activities.ActivityDelegate> a hodnoty jsou argumenty, jejíž výrazy jsou vyhodnoceny a přiřadili odpovídající <xref:System.Activities.DelegateArgument> objekty. V mřížce vlastností klikněte na tlačítko se třemi tečkami v **DelegateArguments** pole, zobrazí **DelegateArguments** dialogové okno umožňuje tuto vlastnost nastavit. Klikněte na tlačítko **vytvořit Argument** pole, které chcete přidat argumenty.|

## <a name="see-also"></a>Viz také:

- [Postupy: Definování a použití delegátů aktivit v návrháři postupu provádění](../workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer.md)