---
title: Návrhář postupu provádění – dialogové okno definice vlastnosti CorrelatesOn
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CorrelatesOnDefinition.UI
ms.assetid: 8b2b627a-f236-4479-aa09-525df65e3413
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d7b7336a3f3b0c2725f4e52116d0add8bf13b90e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62949814"
---
# <a name="correlateson-definition-dialog-box"></a>Dialogové okno Definice vlastnosti CorrelatesOn

**Vlastnosti CorrelatesOn** dialogové okno se používá v Návrháři pracovních postupů k úpravě <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> vlastnost <xref:System.ServiceModel.Activities.Receive> aktivity. Další informace najdete v tématu [přijímat Návrhář aktivity](../workflow-designer/receive-activity-designer.md).

Korelace mezi <xref:System.ServiceModel.Activities.Receive> aktivit Určuje, jak různé služby operace připojení mezi sebou v pracovním postupu.

Následující tabulka popisuje prvky uživatelského rozhraní (UI) **vlastnosti CorrelatesOn** dialogové okno.

|Prvek uživatelského rozhraní (UI)|Popis|
|-|-----------------|
|**CorrelatesWith**|<xref:System.ServiceModel.Activities.CorrelationHandle> , Který slouží k zprávy směruje do instance odpovídající pracovního postupu.|
|**Dotazy XPath**|Dvojice klíč/hodnota, která obsahuje dotazy používané k extrakci korelace dat z příchozí zprávy. Tato hodnota odpovídá <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> vlastnost. Jsou součástí dotazy XPath <xref:System.ServiceModel.MessageQuerySet> objektu.|

## <a name="to-launch-the-correlateson-dialog-box"></a>Chcete-li spustit dialogové okno Vlastnosti CorrelatesOn

**Receive** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřadit na povrch návrháře postupu provádění, bez ohledu na to aktivity jsou obvykle umístěny. Návrhář aktivity vyřadit vytvoří <xref:System.ServiceModel.Activities.Receive> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> Receive. Chcete-li otevřít **definice vlastnosti CorrelatesOn** dialogovém okně **Receive** aktivity návrháře a poté v mřížce vlastností, vyberte tlačítko se třemi tečkami vedle textu kolekce pro  **Vlastnosti CorrelatesOn** vlastnost.

## <a name="see-also"></a>Viz také:

- <xref:System.ServiceModel.Activities.Receive>
- [Dialogové okno Přidat inicializátory korelace](../workflow-designer/add-correlationinitializers-dialog-box.md)
- [Dialogové okno Inicializace korelace](../workflow-designer/initialize-correlation-dialog-box.md)