---
title: Návrhář postupu provádění – Návrhář aktivity Rethrow
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
f1_keywords:
- System.Activities.Statements.Rethrow.UI
ms.assetid: 9cfa2eda-395f-4cf3-9154-83fadd4f7452
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9232244c7e8bc2801d9db1d3f2bad995a70ed63c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55000000"
---
# <a name="rethrow-activity-designer"></a>Návrhář aktivity Rethrow

**Znovu vyvolejte** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Rethrow> aktivity.

## <a name="the-rethrow-activity"></a>Aktivita Přegenerování

<xref:System.Activities.Statements.Rethrow> Aktivita vyvolá dříve vyvolané výjimky. Tato aktivita se dá použít jenom v <xref:System.Activities.Statements.Catch> obslužné rutiny v <xref:System.Activities.Statements.TryCatch> aktivity.

### <a name="use-the-rethrow-activity-designer"></a>Použijte Návrhář aktivity ReThrow

Přístup **znovu vyvolejte** návrháře aktivit v **zpracování chyb** kategorii **nástrojů**. **Znovu vyvolejte** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřadit na povrch návrháře postupu provádění bez ohledu na to aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Vyřazení Návrhář aktivity vytvoří <xref:System.Activities.Statements.Rethrow> aktivity s výchozím **DisplayName** o vyvolání výjimky. <xref:System.Activities.Activity.DisplayName%2A> Hodnota se dá upravit v záhlaví **znovu vyvolejte** návrháře aktivit, nebo **DisplayName** pole mřížku vlastností.

### <a name="the-rethrow-properties"></a>Vlastnosti Rethrow

Následující tabulka ukazuje <xref:System.Activities.Statements.Rethrow> vlastnosti a popisuje, jak se používají v Návrháři:

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje volitelný popisný název <xref:System.Activities.Statements.Rethrow> aktivity. Výchozí hodnota je Přegenerování.|

## <a name="see-also"></a>Viz také:

- [Kolekce](../workflow-designer/collection-activity-designers.md)
- [Throw](../workflow-designer/throw-activity-designer.md)
- [TryCatch](../workflow-designer/trycatch-activity-designer.md)