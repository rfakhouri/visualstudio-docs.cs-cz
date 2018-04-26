---
title: Návrhář postupu provádění – dialogové okno inicializovat korelace
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- InitializeCorrelation.UI
ms.assetid: 2a0a1cd3-7b9e-493e-9264-fcf85289ffcf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 93ce95c7a821d243af842170ba30ec82647933ab
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="initialize-correlation-dialog-box"></a>Inicializace dialogové okno korelace

**Inicializovat korelace** dialogové okno se používá v Návrháři pracovních postupů Windows upravit <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> vlastnost <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivity. Další informace najdete v tématu [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md) tématu.

 Následující tabulka popisuje prvky uživatelského rozhraní (UI) **inicializovat korelace** dialogové okno.

|Prvek uživatelského rozhraní (UI)|Popis|
|----------------|-----------------|
|**Korelace**|<xref:System.ServiceModel.Activities.CorrelationHandle> Korelace k chybě při inicializaci.|
|**Inicializace na**|Dvojice klíč/hodnota, která obsahuje data k chybě při inicializaci. To odpovídá <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> vlastnost. Příkladem dvojici klíč/hodnota platná by klíč s názvem "OrderID" spárovaný s proměnné s názvem OrderID.|

## <a name="to-launch-the-initialize-correlation-dialog-box"></a>Spusťte inicializaci korelace dialogových oken

-   Klikněte na tlačítko **zobrazení** na **InitializeCorrelation** aktivity návrháře nebo vyberte <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivity v Návrháři pracovních postupů a pak klikněte na tlačítko se třemi tečkami vedle <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> vlastnost v Vlastnost mřížky.

## <a name="see-also"></a>Viz také

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)