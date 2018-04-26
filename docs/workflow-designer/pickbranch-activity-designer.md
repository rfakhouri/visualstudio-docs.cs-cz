---
title: Návrhář postupu provádění - PickBranch Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.PickBranch.UI
ms.assetid: f523ad47-bbc0-4cda-a35c-41e67c4ba081
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7ea106a96a5d6b81ee0b0b898c881eb752582f8d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="pickbranch-activity-designer"></a>Návrhář aktivity PickBranch

<xref:System.Activities.Statements.PickBranch> Poskytuje cestu na základě událostí provádění v rámci <xref:System.Activities.Statements.Pick> aktivity, která se aktivuje příchozí události.

## <a name="pickbranch"></a>PickBranch

<xref:System.Activities.Statements.PickBranch> objekty jsou součástí <xref:System.Activities.Statements.Pick.Branches%2A> kolekce <xref:System.Activities.Statements.Pick> aktivity. Každý <xref:System.Activities.Statements.PickBranch> je obsažen ve větvi <xref:System.Activities.Statements.Pick> aktivity a mohou být provedeny z důvodu některých příchozí události, která slouží jako aktivační událost. Tímto způsobem návrháře pracovních postupů Windows poskytuje modelování toku řízení na základě událostí. Každý <xref:System.Activities.Statements.PickBranch> obsahuje <xref:System.Activities.Statements.PickBranch.Trigger%2A> a <xref:System.Activities.Statements.PickBranch.Action%2A>.

### <a name="how-to-use-the-pick-activity-designer"></a>Jak používat návrháře vyberte aktivity

**PickBranch** designer naleznete v **tok řízení** kategorii **sada nástrojů**, který přistupuje kliknutím **sada nástrojů** Karta v Návrháři pracovních postupů (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X).

Dva prázdné <xref:System.Activities.Statements.PickBranch> objekty se zobrazí názvy **pobočka1** a **Branch2** jsou vytvořeny ve výchozím nastavení jako elementy <xref:System.Activities.Statements.Pick> aktivity při **vyberte** Návrhář aktivity se původně ukončí k návrháře pracovních postupů. Tyto příslušných <xref:System.Activities.Statements.PickBranch.DisplayName%2A> hodnoty vlastností lze upravit v **PickBranch** návrháře záhlaví nebo uvnitř **vlastnosti** okna pro každou větev.

Existují dva způsoby, jak přidat <xref:System.Activities.Statements.PickBranch> objekty do kolekce <xref:System.Activities.Statements.Pick> objektu: přetahování a vkládání **PickBranch** návrháře z **sada nástrojů** nebo pomocí místní nabídky z v rámci **vyberte** návrhová plocha:

1.  **PickBranch** Návrhář vytvoří <xref:System.Activities.Statements.PickBranch> při přetažení z **sada nástrojů** a vyřadit do jedné poboček **vyberte** Návrhář aktivity na Prostor Návrháře pracovního postupu. Nové <xref:System.Activities.Statements.PickBranch> objekty může být umístěna uvnitř <xref:System.Activities.Statements.Pick> návrháře vlevo nebo vpravo od všechny existující <xref:System.Activities.Statements.PickBranch> elementy, které jsou již v kolekci obsažena. Při přetažení **PickBranch** návrháře na **vyberte** návrháře myší, **vyberte** Návrhář pomocí svislé vzdálené blue šedá označuje, kde <xref:System.Activities.Statements.PickBranch> Přidá se pro danou myši umístění.

2.  Klikněte pravým tlačítkem na **vyberte** Návrhář aktivity (ale není uvnitř **PickBranch** designer) získat z kontextové nabídky a vyberte **vytvoření větve** přidat nový <xref:System.Activities.Statements.PickBranch>. Všimněte si, že nové <xref:System.Activities.Statements.PickBranch> se přidá napravo od existující <xref:System.Activities.Statements.PickBranch> objekty v **vyberte** designer.

 **PickBranch** designer můžete rozšířit tak, aby odhalit **aktivační událost** a **akce** oknech nebo sbalené kliknutím na dvojitou carets na pravé straně jejich hlaviček. Upravit <xref:System.Activities.Statements.PickBranch.Trigger%2A> a <xref:System.Activities.Statements.PickBranch.Action%2A> jednotlivých <xref:System.Activities.Statements.PickBranch> umístěním aktivit do **aktivační událost** a **akce** polí jejich designeru.

 <xref:System.Activities.Statements.PickBranch> Objekty v <xref:System.Activities.Statements.Pick.Branches%2A> kolekce <xref:System.Activities.Statements.Pick> objektu, může být přeuspořádány přetahováním myší je do nového umístění v rámci **vyberte** designer. **Vyberte** Návrhář pomocí svislé vzdálené blue šedá označuje, kde <xref:System.Activities.Statements.PickBranch> se přidá k myši daného umístění.

 Existují dva způsoby, jak odstranit <xref:System.Activities.Statements.PickBranch>:

1.  Vyberte **PickBranch** designer a jej odstraňte.

2.  Vyberte **PickBranch** návrháře, klikněte pravým tlačítkem a získat v místní nabídce vyberte **odstranit**.

 Je nutné vybrat **PickBranch** návrháře jako výběrem jedné z aktivity uvnitř jeho **aktivační událost** nebo **akce** polí omylem odstraní jednu z těchto aktivit a ne <xref:System.Activities.Statements.PickBranch> objektu.

### <a name="pickbranch-properties-in-the-workflow-designer"></a>Vlastnosti PickBranch v Návrháři pracovních postupů
 V následující tabulce jsou velmi užitečné <xref:System.Activities.Statements.PickBranch> vlastnosti a popisuje, jak je používat v Návrháři pracovních postupů.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Statements.PickBranch.DisplayName%2A>|False|Popisný název zobrazovaný v záhlaví **PickBranch** designer. Výchozí hodnota je firemní pobočky.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|
|<xref:System.Activities.Statements.PickBranch.Trigger%2A>|Hodnota TRUE|Každý <xref:System.Activities.Statements.PickBranch> obsahuje <xref:System.Activities.Statements.PickBranch.Trigger%2A> akce, který lze vyvolat <xref:System.Activities.Statements.PickBranch.Action%2A>.|
|<xref:System.Activities.Statements.PickBranch.Action%2A>|False|Každý <xref:System.Activities.Statements.PickBranch> obsahuje <xref:System.Activities.Statements.PickBranch.Action%2A> který je proveden, pokud je spuštěno.|

## <a name="see-also"></a>Viz také

- [Tok řízení](../workflow-designer/control-flow-activity-designers.md)
- [Výběr aktivity](/dotnet/framework/windows-workflow-foundation/pick-activity)
- [Použití aktivity Pick](/dotnet/framework/windows-workflow-foundation/samples/using-the-pick-activity)