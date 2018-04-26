---
title: Návrhář postupu provádění - vytvořit vazbu k aktivitě&#39;dialogové okno vlastností s (zastaralé)
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Workflow.ComponentModel.Design.ActivityBindForm.UI
helpviewer_keywords:
- Bind to an Activity's Property dialog box
ms.assetid: 19ebb207-e0a9-4642-8f5f-a5e31395c683
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8922864a32c08d8feaed11e530314176557a785f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="bind-to-an-activitys-property-dialog-box-legacy"></a>Vytvořit vazbu na dialogové okno vlastností aktivity (zastaralé)

Toto téma popisuje, jak používat **vazby pro vlastnost aktivity** dialogové okno v Návrháři pracovních postupů starší verze systému Windows. Pokud budete potřebovat cílit na rozhraní .NET Framework verze 3.5 nebo WinFX, použijte starší verzi návrháře pracovních postupů.

 Typ instance vlastnosti závislosti mohou být vázány na jiné aktivity veřejná vlastnost nebo událost. Další informace o vazbě aktivity najdete v tématu [pomocí vlastností závislostí](http://go.microsoft.com/fwlink?LinkID=65007).

 Vyberte vlastnost pro vazbu k použití **vazby pro vlastnost aktivity** dialogové okno. Toto dialogové okno otevřete kliknutím na tlačítko se třemi tečkami **[...]**  na konci textového pole vybranou vlastnost v **vlastnosti** okno, nebo kliknutím na ikonu vykřičník blue, který se zobrazí vedle názvu vlastnosti v prohlížeči vlastností.

 Následující tabulka popisuje prvky uživatelského rozhraní (UI) **vazby pro vlastnost aktivity** dialogové okno.

|Prvek uživatelského rozhraní (UI)|Popis|
|----------------|-----------------|
|**Vytvořit vazbu existujícího člena**|Vyberte člena, který chcete vytvořit vazbu na v podokně zobrazení stromu. V podokně pod stromovém zobrazení se zobrazí zprávu, která označuje, zda člen platný typ k vytvoření vazby, nebo ne. Klikněte na tlačítko **OK** k vytvoření vazby vybraných platný člen.|
|**Vytvořit vazbu na nového člena**|Vytvořte nové pole člen nebo vlastnost pro vazbu. Zadejte **nový název člena**. Zvolte, zda chcete vytvořit vlastnost závislosti nebo veřejné pole výběrem **vytvořit pole** nebo **vytvořit vlastnost**. Klikněte na tlačítko **OK** k vytvoření nového člena.|

## <a name="see-also"></a>Viz také

- [Pomocí vlastnosti aktivit](http://go.microsoft.com/fwlink?LinkID=65013)
- [Pomocí vlastností závislostí](http://go.microsoft.com/fwlink?LinkID=65007)
- [Nápověda k uživatelskému rozhraní návrháře pro programovací model Windows Workflow Foundation](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)