---
title: Návrhář postupu provádění – Návrhář aktivity Interop
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Interop.UI
ms.assetid: 800a3403-ba86-41c4-8de1-c4fee9703eb1
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 688ef92fae5bd0cbaa5ddc653bbaab5692f4827f
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66747139"
---
# <a name="interop-activity-designer"></a>Návrhář aktivity Interop

**Interop** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Interop> aktivity.

## <a name="the-interop-activity"></a>Aktivity interoperability

<xref:System.Activities.Statements.Interop> Aktivita řídí spuštění typy, které jsou odvozeny z <xref:System.Workflow.ComponentModel.Activity?displayProperty=fullName> v rámci pracovního postupu.

### <a name="use-the-interop-activity-designer"></a>Použijte Návrhář aktivity Interop

**Zprostředkovatele komunikace s objekty** návrháře aktivit najdete v **migrace** kategorii **nástrojů**, který přistupuje po kliknutí **nástrojů**kartu. Můžete také vybrat **nástrojů** z **zobrazení** nabídky nebo stisknutím klávesy **Ctrl**+**Alt** + **X**.

[Migrace](../workflow-designer/migration-activity-designers.md) kategorii, která obsahuje <xref:System.Activities.Statements.Interop> aktivity se zobrazí jenom v **nástrojů** Pokud váš projekt cílí na rozhraní .NET Framework 4 (úplné) nebo novější. Pokud třeba, můžete změnit verzi rozhraní framework, který váš projekt cílí.

**Interop** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřadit na plochu návrháře postupu provádění bez ohledu na to aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Vyřazení **zprostředkovatele komunikace s objekty** vytvoří Návrhář aktivity <xref:System.Activities.Statements.Interop> aktivity s výchozím **DisplayName** ze zprostředkovatele komunikace s objekty. Můžete upravit <xref:System.Activities.Activity.DisplayName%2A> v záhlaví **zprostředkovatele komunikace s objekty** návrháře aktivit, nebo **DisplayName** pole mřížku vlastností.

Klikněte na tlačítko **kliknutím Procházet** textu v **ActivityType** pole na **zprostředkovatele komunikace s objekty** aktivity návrháře nebo v mřížce vlastností, chcete-li otevřít **Procházet a Vyberte .net typ** dialogové okno. Jsou zobrazeny pouze typů pro pracovní postup 3.0 nebo 3.5 pracovního postupu aktivity. To znamená, že pouze typy odvozené z <xref:System.Workflow.ComponentModel.Activity> jsou uvedeny. Další informace o použití tohoto pole zadat typ najdete v tématu [Procházet a vybrat typ dialogovému oknu rozhraní .NET](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box.md).

### <a name="the-interop-properties"></a>Vlastnosti definiční

Následující tabulka ukazuje <xref:System.Activities.Statements.Interop> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti můžete upravit v mřížce vlastností nebo na povrchu návrháře postupu provádění.

|Název vlastnosti|Požadováno|Použití|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.Interop> aktivity. Výchozí hodnota je **Interop**. I když není potřeba zobrazovaného názvu, doporučujeme poskytnout.|
|<xref:System.Activities.Statements.Interop.ActivityType%2A>|Pravda|Určuje typ aktivity obsažených <xref:System.Activities.Statements.Interop> aktivity. Tento typ zadán musí být odvozen od <xref:System.Workflow.ComponentModel.Activity>.|

## <a name="see-also"></a>Viz také:

- [Migrace](../workflow-designer/migration-activity-designers.md)