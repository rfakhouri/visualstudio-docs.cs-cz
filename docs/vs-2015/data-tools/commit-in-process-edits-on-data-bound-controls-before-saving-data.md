---
title: Potvrzení úprav v procesu v ovládacích prvcích vázaných na data před uložením dat | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- committing edited records
- data-bound controls, in-process edits
- DataBinding class, committing edited records
- hierarchical update, committing edited records
- BindingSource class, committing edited records
- EndEdit method
ms.assetid: 61af4798-eef7-468c-b229-5e1497febb2f
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2def3f3512e7a6ebc2e084f0bca4d6b1707ecd04
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65699484"
---
# <a name="commit-in-process-edits-on-data-bound-controls-before-saving-data"></a>Potvrzení úprav v procesu v ovládacích prvcích vázaných na data před uložením dat
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Při úpravě hodnoty v ovládacích prvcích vázaných na data, musí uživatelé přejít mimo aktuální záznam potvrdit aktualizovanou hodnotu do podkladového zdroje dat, který ovládací prvek vázán. Při přetažení položky z [okna zdroje dat](https://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992) do formuláře, první položka, která je vyřadit generuje kód do **Uložit** události kliknutí na tlačítko <xref:System.Windows.Forms.BindingNavigator>. Tento kód volá <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metodu <xref:System.Windows.Forms.BindingSource>. Proto volání <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metoda se vygeneruje pouze pro první <xref:System.Windows.Forms.BindingSource> , který je přidán do formuláře.  
  
 <xref:System.Windows.Forms.BindingSource.EndEdit%2A> Volání potvrzení změny, které jsou v procesu, ve všech ovládacích prvcích vázaných na data, které jsou právě upravována. Proto, pokud ovládací prvek vázaný na data stále má fokus a klikněte na tlačítko **Uložit** tlačítko všechny čekající změny v tom, že ovládací prvek usilujeme o to před skutečné uložit ( `TableAdapterManager.UpdateAll` metoda).  
  
 Vaše aplikace automaticky potvrzení změn, můžete nakonfigurovat i v případě, že uživatel pokusí uložit data bez potvrzení změn, uložení v rámci procesu.  
  
> [!NOTE]
> Návrhář přidá `BindingSource.EndEdit` vynechán kód jenom pro první položku do formuláře. Proto je nutné přidat řádek kódu pro volání <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metoda pro každou <xref:System.Windows.Forms.BindingSource> ve formuláři. Můžete ručně přidat řádek kódu pro volání <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metoda pro každou <xref:System.Windows.Forms.BindingSource>. Alternativně můžete přidat `EndEditOnAllBindingSources` metoda do formuláře a jeho volání před provedením uložení.  
  
 Následující kód používá [LINQ (Language-Integrated Query)](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) dotaz, který iterovat všechny <xref:System.Windows.Forms.BindingSource> komponenty a volání <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metoda pro každou <xref:System.Windows.Forms.BindingSource> ve formuláři.  
  
## <a name="to-call-endedit-for-all-bindingsource-components-on-a-form"></a>Chcete-li volat EndEdit – pro všechny součásti BindingSource ve formuláři  
  
1. Přidejte následující kód do formuláře, který obsahuje <xref:System.Windows.Forms.BindingSource> komponenty.  
  
     [!code-csharp[VSProDataOrcasEndEditOnAll#1](../snippets/csharp/VS_Snippets_VBCSharp/VSProDataOrcasEndEditOnAll/CS/Form1.cs#1)]
     [!code-vb[VSProDataOrcasEndEditOnAll#1](../snippets/visualbasic/VS_Snippets_VBCSharp/VSProDataOrcasEndEditOnAll/VB/Form1.vb#1)]  
  
2. Přidejte následující kód bezprostředně před všechna volání k uložení dat formuláře ( `TableAdapterManager.UpdateAll()` metoda):  
  
     [!code-csharp[VSProDataOrcasEndEditOnAll#2](../snippets/csharp/VS_Snippets_VBCSharp/VSProDataOrcasEndEditOnAll/CS/Form1.cs#2)]
     [!code-vb[VSProDataOrcasEndEditOnAll#2](../snippets/visualbasic/VS_Snippets_VBCSharp/VSProDataOrcasEndEditOnAll/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Hierarchická aktualizace](../data-tools/hierarchical-update.md)
