---
title: "Potvrzení úprav v procesu na ovládací prvky vázané na data před uložením dat | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- commiting edited records
- data-bound controls, in-process edits
- DataBinding class, commiting edited records
- hierarchical update, commiting edited records
- BindingSource class, commiting edited records
- EndEdit method
ms.assetid: 61af4798-eef7-468c-b229-5e1497febb2f
caps.latest.revision: "13"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 191206e9cc16271e64abbeaba87d86ac0108924b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="commit-in-process-edits-on-data-bound-controls-before-saving-data"></a>Potvrzení úprav v procesu na ovládací prvky vázané na data před uložením dat
Při úpravě hodnoty v ovládacích prvcích vázaných na data, musí uživatelé přejít mimo potvrzení aktualizované hodnoty podkladové zdroje dat, který je ovládací prvek vázán na aktuální záznam. Při přetahování položek z [okno zdroje dat](add-new-data-sources.md) na formuláři, první položka, která je vyřadit generuje kód do **Uložit** tlačítko klikněte na události <xref:System.Windows.Forms.BindingNavigator>. Tento kód zavolá <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metodu <xref:System.Windows.Forms.BindingSource>. Proto volání <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metoda se vygeneruje pouze pro první <xref:System.Windows.Forms.BindingSource> přidaná do formuláře.  
  
 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> Volání potvrdí všechny změny, které jsou v procesu v všechny ovládací prvky vázané na data, které jsou aktuálně Upravovaný. Proto pokud stále má ovládací prvek vázané na data fokus a klikněte na tlačítko **Uložit** tlačítko všechna nevyřízená úpravy v tom, že jsou před skutečným uložit potvrzené ovládací prvek ( `TableAdapterManager.UpdateAll` metoda).  
  
 Vaše aplikace automaticky potvrzení změn, můžete nakonfigurovat, i když se uživatel pokusí o uložení dat bez potvrzení změn, jako součást uložení procesu.  
  
> [!NOTE]
>  Přidá návrháře `BindingSource.EndEdit` kódu pouze pro první položku umístění na formuláři. Proto je nutné přidat řádek kódu pro volání <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metoda pro každou <xref:System.Windows.Forms.BindingSource> na formuláři. Můžete ručně přidat řádek kódu pro volání <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metoda pro každou <xref:System.Windows.Forms.BindingSource>. Alternativně můžete přidat `EndEditOnAllBindingSources` metoda formuláře a pojmenujte ji před provedením uložení.  
  
 Následující kód používá [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/Library/a73c4aec-5d15-4e98-b962-1274021ea93d) dotaz pro všechny iterace <xref:System.Windows.Forms.BindingSource> součásti a volání <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metoda pro každou <xref:System.Windows.Forms.BindingSource> ve formuláři.  
  
## <a name="to-call-endedit-for-all-bindingsource-components-on-a-form"></a>K volání EndEdit – pro všechny součásti BindingSource ve formuláři  
  
1.  Přidejte následující kód pro formulář, který obsahuje <xref:System.Windows.Forms.BindingSource> součásti.  
  
     [!code-csharp[VSProDataOrcasEndEditOnAll#1](../data-tools/codesnippet/CSharp/commit-in-process-edits-on-data-bound-controls-before-saving-data_1.cs)]
     [!code-vb[VSProDataOrcasEndEditOnAll#1](../data-tools/codesnippet/VisualBasic/commit-in-process-edits-on-data-bound-controls-before-saving-data_1.vb)]  
  
2.  Přidejte následující řádek kódu bezprostředně před volání uložit data formuláře ( `TableAdapterManager.UpdateAll()` metoda):  
  
     [!code-csharp[VSProDataOrcasEndEditOnAll#2](../data-tools/codesnippet/CSharp/commit-in-process-edits-on-data-bound-controls-before-saving-data_2.cs)]
     [!code-vb[VSProDataOrcasEndEditOnAll#2](../data-tools/codesnippet/VisualBasic/commit-in-process-edits-on-data-bound-controls-before-saving-data_2.vb)]  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Hierarchická aktualizace](../data-tools/hierarchical-update.md)