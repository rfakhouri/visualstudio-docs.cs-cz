---
title: "Inicializace dialogové okno korelace | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- InitializeCorrelation.UI
ms.assetid: 2a0a1cd3-7b9e-493e-9264-fcf85289ffcf
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 641526a0577c74ff590d701560e5266c85fa60dc
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
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