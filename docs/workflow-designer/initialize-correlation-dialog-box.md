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
ms.openlocfilehash: c3525eb8964ed603e40ba74f0c06b17b494390c7
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36755837"
---
# <a name="initialize-correlation-dialog-box"></a>Dialogové okno Inicializace korelace

**Inicializovat korelace** dialogové okno se používá v Návrháři pracovních postupů, chcete-li upravit <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> vlastnost <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivity. Další informace najdete v tématu [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md).

Následující tabulka popisuje prvky uživatelského rozhraní (UI) **inicializovat korelace** dialogové okno:

|Prvek uživatelského rozhraní (UI)|Popis|
|----------------|-----------------|
|**Korelace**|<xref:System.ServiceModel.Activities.CorrelationHandle> Korelace k chybě při inicializaci.|
|**Inicializace na**|Dvojice klíč/hodnota, která obsahuje data k chybě při inicializaci. Tato hodnota odpovídá <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> vlastnost. Příkladem dvojici platný klíč/hodnota je klíč s názvem "OrderID" spárovaný s proměnné s názvem OrderID.|

## <a name="to-launch-the-initialize-correlation-dialog-box"></a>Spusťte inicializaci korelace dialogových oken

Klikněte na tlačítko **zobrazení** na **InitializeCorrelation** aktivity návrháře nebo vyberte <xref:System.ServiceModel.Activities.InitializeCorrelation> aktivity v Návrháři pracovních postupů. Potom klikněte na tlačítko se třemi tečkami vedle <xref:System.ServiceModel.Activities.InitializeCorrelation.CorrelationData%2A> vlastnost v tabulce vlastností.

## <a name="see-also"></a>Viz také:

- [InitializeCorrelation](../workflow-designer/initializecorrelation-activity-designer.md)