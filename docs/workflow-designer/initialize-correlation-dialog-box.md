---
title: Inicializace dialogové okno korelace | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- InitializeCorrelation.UI
ms.assetid: 2a0a1cd3-7b9e-493e-9264-fcf85289ffcf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aac62d4439c2280e977ef929c79bb103348c170a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="initialize-correlation-dialog-box"></a>Inicializace dialogové okno korelace

**Inicializovat korelace** dialogové okno se používá v Návrháři pracovních postupů Windows upravit <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> vlastnost <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivity. Další informace najdete v tématu [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md) tématu.

 Následující tabulka popisuje prvky uživatelského rozhraní (UI) **inicializovat korelace** dialogové okno.

|Prvek uživatelského rozhraní (UI)|Popis|
|----------------|-----------------|
|**Korelace**|<xref:System.ServiceModel.Activities.CorrelationHandle> Korelace k chybě při inicializaci.|
|**Inicializace na**|Dvojice klíč/hodnota, která obsahuje data k chybě při inicializaci. To odpovídá <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> vlastnost. Příkladem dvojici klíč/hodnota platná by klíč s názvem "OrderID" spárovaný s proměnné s názvem OrderID.|

## <a name="to-launch-the-initialize-correlation-dialog-box"></a>Spusťte inicializaci korelace dialogových oken

-   Klikněte na tlačítko **zobrazení** na **InitializeCorrelation** aktivity návrháře nebo vyberte <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivity v [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] a pak klikněte tlačítko se třemi tečkami vedle <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> vlastnost v mřížku vlastností.

## <a name="see-also"></a>Viz také

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)