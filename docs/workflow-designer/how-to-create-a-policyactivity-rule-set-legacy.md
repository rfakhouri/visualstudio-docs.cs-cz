---
title: "Postupy: vytvoření sadu pravidel aktivitě PolicyActivity (zastaralé) | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- PolicyActivity activity, creating rule sets
- Rule Set Editor dialog box
- PolicyActivity activity, selecting rule sets
- Select Rule Set dialog box
- rule sets, creating for PolicyActivity
ms.assetid: f272489d-3342-4511-8b59-6a0fd7a42d70
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 96fcb8dd8e1255863840cae8edd90759af605f1d
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-create-a-policyactivity-rule-set-legacy"></a>Postupy: vytvoření sadu pravidel aktivitě PolicyActivity (zastaralé)

Toto téma popisuje, jak vytvořit pravidlo zásad aktivity, nastavit pomocí návrháře pracovních postupů starší verze Windows s cílem [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

 Po přetažení **zásad** aktivity položku z **sada nástrojů** na plochu návrháře pracovního postupu můžete vybrat existující pravidlo nebo vytvořit nové pravidlo, nastavte pro [aktivitě PolicyActivity ](http://go.microsoft.com/fwlink?LinkID=65019) aktivity. Vyberte existující pravidlo nastavit pomocí [vyberte pravidlo nastavte dialogové okno (zastaralé)](../workflow-designer/select-rule-set-dialog-box-legacy.md) a vytvoříte pomocí sady pravidel [pravidlo nastavte dialogové okno Editor (zastaralé)](../workflow-designer/rule-set-editor-dialog-box-legacy.md).

> [!NOTE]
> Můžete otevřít [pravidlo nastavte dialogové okno Editor (zastaralé)](../workflow-designer/rule-set-editor-dialog-box-legacy.md) dialogové okno přímo poklepáním na [aktivitě PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019) aktivity, který je na návrhovou plochu pracovního postupu.

### <a name="to-select-or-create-a-rule-set-for-a-policyactivity-activity"></a>Vybrat nebo vytvořit sadu pravidel pro aktivitu aktivitě PolicyActivity

1.  Klikněte pravým tlačítkem myši [aktivitě PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)a potom klikněte na **vlastnosti** otevřete **vlastnosti** okno.

2.  Klikněte **RuleSetReference** vlastnost.

3.  Proveďte jednu z těchto akcí:

    -   Klikněte **RuleSetReference** třemi tečkami **[...]** a potom vyberte existující pravidlo nastavit [vyberte pravidlo nastavte dialogové okno (zastaralé)](../workflow-designer/select-rule-set-dialog-box-legacy.md). Přejděte ke kroku 10.

         -nebo-

    -   Zadejte název pro sadu pravidel. Klikněte **RuleSetReference** třemi tečkami **[...]** a potom vyberte **upravit** v [vyberte pravidlo nastavte dialogové okno (zastaralé)](../workflow-designer/select-rule-set-dialog-box-legacy.md).

         -nebo-

    -   Zadejte název pro sadu pravidel. Rozbalte **RuleSetReference** vlastnost a vyberte se třemi tečkami **[...]**  v **RuleSet definice** vlastnost.

         [Pravidlo nastavte dialogové okno Editor (zastaralé)](../workflow-designer/rule-set-editor-dialog-box-legacy.md) otevře.

4.  V [pravidlo nastavte dialogové okno Editor (zastaralé)](../workflow-designer/rule-set-editor-dialog-box-legacy.md), klikněte na tlačítko **přidat pravidlo** přidat nové pravidlo sady pravidel.

5.  Zadejte **název**, **s prioritou**, a **přehodnocení** vlastnosti, nebo ponechte výchozí hodnoty.

6.  Zadejte text pro **podmínku**.

7.  Zadejte text pro **pak akce** a **Else akce**.

8.  Klikněte na tlačítko **přidat pravidlo** přidat jiné pravidlo.

9. Až budete hotovi, klikněte na tlačítko **OK**.

## <a name="see-also"></a>Viz také

- [Aktivitě PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)
- [Dialogové okno Vybrat sadu pravidel (starší verze)](../workflow-designer/select-rule-set-dialog-box-legacy.md)
- [Dialogové okno Editor sad pravidel (starší verze)](../workflow-designer/rule-set-editor-dialog-box-legacy.md)
- [Pomocí zásad aktivity](http://go.microsoft.com/fwlink?LinkID=65004)
- [Aktivity starších verzí pracovních postupů](../workflow-designer/legacy-workflow-activities.md)