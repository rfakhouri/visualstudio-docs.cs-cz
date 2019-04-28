---
title: Návrhář postupu provádění – dialogové okno Inicializace korelace
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- InitializeCorrelation.UI
ms.assetid: 2a0a1cd3-7b9e-493e-9264-fcf85289ffcf
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8fab86b39cd927d516bc627630a29feee1698daa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62536813"
---
# <a name="initialize-correlation-dialog-box"></a>Dialogové okno Inicializace korelace

**Inicializace korelace** dialogové okno se používá v Návrháři pracovních postupů k úpravě <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> vlastnost <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivity. Další informace najdete v tématu [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md).

Následující tabulka popisuje prvky uživatelského rozhraní (UI) **inicializace korelace** dialogové okno:

|Prvek uživatelského rozhraní (UI)|Popis|
|-|-----------------|
|**Korelace**|<xref:System.ServiceModel.Activities.CorrelationHandle> Korelace inicializace.|
|**Inicializovat na**|Dvojice klíč/hodnota, která obsahuje data k inicializaci. Tato hodnota odpovídá <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> vlastnost. Příklad dvojici klíč/hodnota platná je klíč s názvem "OrderID" párována s proměnnou s názvem OrderID.|

## <a name="to-launch-the-initialize-correlation-dialog-box"></a>Chcete-li spustit dialogové okno Inicializace korelace

Klikněte na tlačítko **zobrazení** na **InitializeCorrelation** aktivity návrháře nebo vyberte <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivity v Návrháři pracovních postupů. Klikněte tlačítko se třemi tečkami vedle <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> vlastnost v mřížce vlastností.

## <a name="see-also"></a>Viz také:

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)