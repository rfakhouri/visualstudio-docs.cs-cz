---
title: Dialogové okno Definice CorrelatesOn | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CorrelatesOnDefinition.UI
ms.assetid: 8b2b627a-f236-4479-aa09-525df65e3413
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 930f291f68e62e70c4d2a03f490f84fd8d36f657
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="correlateson-definition-dialog-box"></a>Dialogové okno Definice CorrelatesOn
**CorrelatesOn** dialogové okno se používá v Návrháři pracovních postupů Windows upravit <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> vlastnost <xref:System.ServiceModel.Activities.Receive> aktivity. Další informace najdete v tématu [Receive](../workflow-designer/receive-activity-designer.md) tématu.

 Korelace mezi <xref:System.ServiceModel.Activities.Receive> aktivit Určuje, jak jinou službu, pro operace připojení mezi sebou v pracovním postupu.

 Následující tabulka popisuje prvky uživatelského rozhraní (UI) **CorrelatesOn** dialogové okno.

|Prvek uživatelského rozhraní (UI)|Popis|
|----------------|-----------------|
|**CorrelatesWith**|<xref:System.ServiceModel.Activities.CorrelationHandle> Sloužící k směrovat k instanci pracovního postupu příslušná zpráva.|
|**Dotazy XPath**|Dvojice klíč/hodnota, která obsahuje dotazy použitou k extrakci korelace data z příchozí zprávy. To odpovídá <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> vlastnost. Dotazy XPath jsou součástí <xref:System.ServiceModel.MessageQuerySet> objektu.|

## <a name="to-launch-the-correlateson-dialog-box"></a>Ke spuštění CorrelatesOn dialogových oken
 **Receive** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny. Tím se vytvoří <xref:System.ServiceModel.Activities.Receive> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> Receive. Vyberte **Receive** Návrhář aktivity a klikněte na tlačítko se třemi tečkami vedle textu (kolekce) pro **CorrelatesOn** v mřížce vlastnost pro vlastnost **CorrelatesOn definice**  dialogové okno se objeví.

## <a name="see-also"></a>Viz také

- <xref:System.ServiceModel.Activities.Receive>
- [Dialogové okno Přidat inicializátory korelace](../workflow-designer/add-correlationinitializers-dialog-box.md)
- [Korelace dialogové okno Přidat](http://msdn.microsoft.com/en-us/9e41a149-e8ab-41b1-8886-ea06a63041b6)
- [Dialogové okno Inicializace korelace](../workflow-designer/initialize-correlation-dialog-box.md)