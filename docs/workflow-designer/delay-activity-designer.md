---
title: Návrhář postupu provádění – Návrhář aktivity Delay
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
f1_keywords:
- System.Activities.Statements.Delay.UI
ms.assetid: f51742a8-2c9a-47d1-8a23-18459d03ae19
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6c793456cd32d6d5749bcda8c8d266f6cd939601
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53823659"
---
# <a name="delay-activity-designer"></a>Návrhář aktivity Delay

**Zpoždění** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Delay> aktivity.

## <a name="the-delay-activity"></a>Aktivitě Delay

<xref:System.Activities.Statements.Delay> Aktivity zpoždění spuštění pracovního postupu pro určenou dobu.

### <a name="use-the-delay-activity-designer"></a>Použijte Návrhář aktivity Delay

**Zpoždění** návrháře aktivit najdete v **primitiv** kategorii **nástrojů**, který přistupuje po kliknutí **nástrojů**kartu návrháře postupu provádění. Můžete také vybrat **nástrojů** z **zobrazení** nabídky nebo stisknutím klávesy **Ctrl**+**Alt** + **X**.

**Zpoždění** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřadit na povrch návrháře postupu provádění bez ohledu na to aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Vyřazení Návrhář aktivity vytvoří <xref:System.Activities.Statements.Delay> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> zpoždění. <xref:System.Activities.Activity.DisplayName%2A> Můžete upravovat v záhlaví **zpoždění** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.

### <a name="the-delay-properties"></a>Vlastnosti zpoždění

Následující tabulka ukazuje <xref:System.Activities.Statements.Delay> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti můžete upravit v mřížce vlastností a některé z nich můžete upravit na povrchu návrháře postupu provádění.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.Delay> aktivity. Výchozí hodnota je zpoždění. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|
|<xref:System.Activities.Statements.Delay.Duration%2A>|Pravda|Množství času zpoždění pracovní postup. Tato vlastnost je nastavena v mřížce vlastností. Zadejte buď literál <xref:System.TimeSpan> ve formátu 00:00:00 nebo výraz jazyka Visual Basic k určení časového intervalu.|

## <a name="see-also"></a>Viz také:

- [Primitiva](../workflow-designer/primitives-activity-designers.md)
- [Assign](../workflow-designer/assign-activity-designer.md)
- [Návrhář aktivity Delay](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)