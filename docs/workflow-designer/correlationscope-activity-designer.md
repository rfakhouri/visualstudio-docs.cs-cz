---
title: Návrhář postupu provádění - CorrelationScope Návrhář aktivity
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.ServiceModel.Activities.CorrelationScope.UI
ms.assetid: 75f20664-9042-464d-8e2b-148d365a2286
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b4b7eb7586eeb746bdeb3d28dfcc5fb14fe7bd6f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="correlationscope-activity-designer"></a>Návrhář aktivity CorrelationScope

**CorrelationScope** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.ServiceModel.Activities.CorrelationScope> aktivity, která nabízí implicitní správu podřízené aktivity zasílání zpráv pomocí <xref:System.ServiceModel.Activities.CorrelationHandle> objektu.

## <a name="the-correlationscope-activity"></a>CorrelationScope aktivity

<xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A> Určuje vlastnost <xref:System.ServiceModel.Activities.CorrelationHandle> používat ke správě podřízené aktivity zasílání zpráv. <xref:System.ServiceModel.Activities.Send> a <xref:System.ServiceModel.Activities.Receive> aktivity obsažené v <xref:System.ServiceModel.Activities.CorrelationScope.Body%2A> jsou nakonfigurovány pro použití <xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A> vlastnost obsahující <xref:System.ServiceModel.Activities.CorrelationScope> aktivita k provedení korelace.

### <a name="using-the-correlationscope-activity-designer"></a>Pomocí návrháře CorrelationScope aktivity
 **CorrelationScope** Návrhář aktivity naleznete v **zasílání zpráv** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů** karty na levé straně návrháře pracovních postupů (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)

 **CorrelationScope** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vyřadit na povrch návrháře pracovních postupů. Tím se vytvoří <xref:System.ServiceModel.Activities.CorrelationScope> aktivitu výchozí **DisplayName** z CorrelationScope. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **CorrelationScope** Návrhář aktivity nebo v **DisplayName** pole **vlastnosti** okno.

 K určení <xref:System.ServiceModel.Activities.CorrelationHandle> používá podřízené aktivity zasílání zpráv, klikněte na tlačítko se třemi tečkami vedle položky **CorrelatesWith** pole **vlastnosti** okna zobrazte **Editor výrazů**  dialogové okno. Tuto vlastnost lze nastavit také na plochu návrháře aktivit.

 Vyřazení jejich designeru v rámci aktivity obor v korelaci jsou určené **textu** pole v rámci **CorrelationScope** designer.

### <a name="the-correlationscope-properties"></a>Vlastnosti CorrelationScope
 Následující tabulce je zobrazena <xref:System.ServiceModel.Activities.CorrelationScope> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravit buď v **vlastnosti** okno nebo na plochu návrháře návrháře pracovních postupů a často v obou.

|Název vlastnosti|Požadováno|Použití|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|Volitelné popisný název <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivity.|
|<xref:System.ServiceModel.Activities.CorrelationScope.CorrelatesWith%2A>|False|Určuje, <xref:System.ServiceModel.Activities.CorrelationHandle> používat ke správě podřízené aktivity zasílání zpráv. Pokud není nastavena tato vlastnost <xref:System.ServiceModel.Activities.CorrelationScope> vytvoří implicitní <xref:System.ServiceModel.Activities.CorrelationHandle> automaticky.|
|<xref:System.ServiceModel.Activities.CorrelationScope.Body%2A>|False|Určuje aktivity v rámci oboru korelaci.|

## <a name="see-also"></a>Viz také

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)
- [Přijímat](../workflow-designer/receive-activity-designer.md)
- [ReceiveAndSendReply](../workflow-designer/receiveandsendreply-template-designer.md)
- [Odeslat](../workflow-designer/send-activity-designer.md)
- [SendAndReceiveReply](../workflow-designer/sendandreceivereply-template-designer.md)
- [TransactedReceiveScope](../workflow-designer/transactedreceivescope-activity-designer.md)