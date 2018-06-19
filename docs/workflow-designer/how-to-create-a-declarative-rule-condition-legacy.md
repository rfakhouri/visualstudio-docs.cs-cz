---
title: 'Návrhář postupu provádění - postupy: vytvoření podmínky deklarativní pravidla (zastaralé)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- declarative rule conditions
- condition statements, declarative rule conditions
- Rule Condition Editor dialog box
ms.assetid: 804b6129-c433-408f-a424-46987967730c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 43b359040256788db240274f43f706b41f01d021
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31977940"
---
# <a name="how-to-create-a-declarative-rule-condition-legacy"></a>Postupy: vytvoření podmínky deklarativní pravidla (zastaralé)

Toto téma popisuje, jak deklarace podmínku pravidla pomocí návrháře pracovních postupů starší verze Windows s cílem rozhraní .NET Framework verze 3.5 nebo WinFX.

Příkaz podmínky se vyhodnocuje **True** nebo **False**. Deklarativní pravidlo podmínku je příkaz podmínky, která je vytvořená pomocí [dialogové okno pravidla podmínku Editor (zastaralé)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md) a uložit jako XML s pracovním postupem. Může zahrnovat predikáty, které porovnávají stav pracovního postupu a algebra logická hodnota, které se kombinuje několik predikáty.

Podmínky deklarativní pravidla se používají v níže uvedených aktivit out-of-box modelu Windows Workflow Foundation:

-   [Skupina ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)

-   [IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65034)

-   [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)

-   [Aktivita typu WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)

-   [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040)

-   [StateMachineWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65045)

## <a name="to-create-a-declarative-rule-condition-using-the-rule-condition-editor"></a>Chcete-li vytvořit podmínku deklarativní pravidla pomocí Editor podmínek pravidla

1.  V rámci aktivity **vlastnosti** okně klikněte na tlačítko **podmínku** vlastnost nebo **UntilCondition** vlastnost, v závislosti na aktivity.

2.  Vyberte **deklarativní podmínku pravidla** ze seznamu pro vlastnost.

3.  Rozbalte **podmínku** nebo **UntilCondition** vlastnost.

4.  Klikněte **ConditionName** vlastnost.

5.  Klikněte **ConditionName** třemi tečkami **[...]**  otevřete **vyberte podmínku** dialogové okno.

6.  Klikněte na tlačítko **novou podmínku** otevřete **Editor podmínek pravidla** dialogové okno.

7.  Zadejte výraz pro stav v **podmínku** textové pole.

     Informace o tom, jak vytvořit podmínku výrazy najdete v tématu [dialogové okno pravidla podmínku Editor (zastaralé)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md).

8.  Až budete hotovi, vytváření výraz podmínky, klikněte na tlačítko **OK** a zavřete dialogové okno Vytvořit podmínka pro pravidlo s názvem přiřazené.

     **Vyberte podmínku** otevře se dialogové okno.

     Informace o tom, jak používat **vyberte podmínku** dialogové okno, najdete v části [vyberte podmínku dialogové okno (zastaralé)](../workflow-designer/select-condition-dialog-box-legacy.md).

## <a name="see-also"></a>Viz také

- [Aktivity starších verzí pracovních postupů](../workflow-designer/legacy-workflow-activities.md)
- [Pomocí skupiny ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65066)
- [Pomocí aktivity IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65075)
- [Pomocí aktivity replikátoru](http://go.microsoft.com/fwlink?LinkID=65080)
- [Pomocí když aktivita](http://go.microsoft.com/fwlink?LinkID=65091)
- [Dialogové okno Editor podmínek pravidla (starší verze)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)
- [Dialogové okno Vybrat podmínku (starší verze)](../workflow-designer/select-condition-dialog-box-legacy.md)
- [Pomocí podmínek v pracovních postupech](http://go.microsoft.com/fwlink?LinkID=65009)