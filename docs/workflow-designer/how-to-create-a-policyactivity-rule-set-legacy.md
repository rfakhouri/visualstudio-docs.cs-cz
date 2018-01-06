---
title: "Postupy: vytvoření sadu pravidel aktivitě PolicyActivity (zastaralé) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- PolicyActivity activity, creating rule sets
- Rule Set Editor dialog box
- PolicyActivity activity, selecting rule sets
- Select Rule Set dialog box
- rule sets, creating for PolicyActivity
ms.assetid: f272489d-3342-4511-8b59-6a0fd7a42d70
caps.latest.revision: "4"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 1b57fe5f33bdbc4dfb7ab76856bdd80a3246ea9e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-policyactivity-rule-set-legacy"></a>Postupy: vytvoření sadu pravidel aktivitě PolicyActivity (zastaralé)
Toto téma popisuje, jak vytvořit pravidlo zásad aktivity, nastavit pomocí starší verze [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] s cílem [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 Po přetažení **zásad** aktivity položku z **sada nástrojů** na plochu návrháře pracovního postupu můžete vybrat existující pravidlo nebo vytvořit nové pravidlo, nastavte pro [aktivitě PolicyActivity ](http://go.microsoft.com/fwlink?LinkID=65019) aktivity. Vyberte existující pravidlo nastavit pomocí [vyberte pravidlo nastavte dialogové okno (zastaralé)](../workflow-designer/select-rule-set-dialog-box-legacy.md) a vytvoříte pomocí sady pravidel [pravidlo nastavte dialogové okno Editor (zastaralé)](../workflow-designer/rule-set-editor-dialog-box-legacy.md).  
  
> [!NOTE]
>  Můžete otevřít [pravidlo nastavte dialogové okno Editor (zastaralé)](../workflow-designer/rule-set-editor-dialog-box-legacy.md) dialogové okno přímo poklepáním na [aktivitě PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019) aktivity, který je na návrhovou plochu pracovního postupu.  
  
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
 [Aktivitě PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)   
 [Dialogové okno nastavit vyberte pravidlo (zastaralé)](../workflow-designer/select-rule-set-dialog-box-legacy.md)   
 [Pravidlo nastavte dialogové okno Editor (zastaralé)](../workflow-designer/rule-set-editor-dialog-box-legacy.md)   
 [Pomocí zásad aktivity](http://go.microsoft.com/fwlink?LinkID=65004)   
 [Aktivity starších verzí pracovních postupů](../workflow-designer/legacy-workflow-activities.md)