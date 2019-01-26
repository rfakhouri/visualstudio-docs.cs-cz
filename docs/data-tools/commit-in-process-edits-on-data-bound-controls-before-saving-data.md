---
title: Potvrzení úprav v procesu v ovládacích prvcích vázaných na data před uložením dat
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- committing edited records
- data-bound controls, in-process edits
- DataBinding class, committing edited records
- hierarchical update, committing edited records
- BindingSource class, committing edited records
- EndEdit method
ms.assetid: 61af4798-eef7-468c-b229-5e1497febb2f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 936fb3ea1a5faae942c2c0b614a27c0a037c9dd6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55001745"
---
# <a name="commit-in-process-edits-on-data-bound-controls-before-saving-data"></a>Potvrzení úprav v procesu v ovládacích prvcích vázaných na data před uložením dat

Při úpravě hodnoty v ovládacích prvcích vázaných na data, musí uživatelé přejít mimo aktuální záznam potvrdit aktualizovanou hodnotu do podkladového zdroje dat, který ovládací prvek vázán. Při přetažení položky z [okna zdroje dat](add-new-data-sources.md) do formuláře, první položka, která je vyřadit generuje kód do **Uložit** události kliknutí na tlačítko <xref:System.Windows.Forms.BindingNavigator>. Tento kód volá <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metodu <xref:System.Windows.Forms.BindingSource>. Proto volání <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metoda se vygeneruje pouze pro první <xref:System.Windows.Forms.BindingSource> , který je přidán do formuláře.

<xref:System.Windows.Forms.BindingSource.EndEdit%2A> Volání potvrzení změny, které jsou v procesu, ve všech ovládacích prvcích vázaných na data, které jsou právě upravována. Proto, pokud ovládací prvek vázaný na data stále má fokus a klikněte na tlačítko **Uložit** tlačítko všechny čekající změny v tom, že ovládací prvek usilujeme o to před skutečné uložit ( `TableAdapterManager.UpdateAll` metoda).

Vaše aplikace automaticky potvrzení změn, můžete nakonfigurovat i v případě, že uživatel pokusí uložit data bez potvrzení změn, uložení v rámci procesu.

> [!NOTE]
> Návrhář přidá `BindingSource.EndEdit` vynechán kód jenom pro první položku do formuláře. Proto je nutné přidat řádek kódu pro volání <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metoda pro každou <xref:System.Windows.Forms.BindingSource> ve formuláři. Můžete ručně přidat řádek kódu pro volání <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metoda pro každou <xref:System.Windows.Forms.BindingSource>. Alternativně můžete přidat `EndEditOnAllBindingSources` metoda do formuláře a jeho volání před provedením uložení.

Následující kód používá [LINQ (Language-Integrated Query)](/dotnet/csharp/linq/) dotaz, který iterovat všechny <xref:System.Windows.Forms.BindingSource> komponenty a volání <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metoda pro každou <xref:System.Windows.Forms.BindingSource> ve formuláři.

## <a name="to-call-endedit-for-all-bindingsource-components-on-a-form"></a>Chcete-li volat EndEdit – pro všechny součásti BindingSource ve formuláři

1.  Přidejte následující kód do formuláře, který obsahuje <xref:System.Windows.Forms.BindingSource> komponenty.

     [!code-csharp[VSProDataOrcasEndEditOnAll#1](../data-tools/codesnippet/CSharp/commit-in-process-edits-on-data-bound-controls-before-saving-data_1.cs)]
     [!code-vb[VSProDataOrcasEndEditOnAll#1](../data-tools/codesnippet/VisualBasic/commit-in-process-edits-on-data-bound-controls-before-saving-data_1.vb)]

2.  Přidejte následující kód bezprostředně před všechna volání k uložení dat formuláře ( `TableAdapterManager.UpdateAll()` metoda):

     [!code-csharp[VSProDataOrcasEndEditOnAll#2](../data-tools/codesnippet/CSharp/commit-in-process-edits-on-data-bound-controls-before-saving-data_2.cs)]
     [!code-vb[VSProDataOrcasEndEditOnAll#2](../data-tools/codesnippet/VisualBasic/commit-in-process-edits-on-data-bound-controls-before-saving-data_2.vb)]

## <a name="see-also"></a>Viz také:

- [Vytvoření vazby ovládacích prvků modelu Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [Hierarchická aktualizace](../data-tools/hierarchical-update.md)