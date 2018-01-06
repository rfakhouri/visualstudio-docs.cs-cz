---
title: "Dialogové okno Definice CorrelatesOn | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: CorrelatesOnDefinition.UI
ms.assetid: 8b2b627a-f236-4479-aa09-525df65e3413
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 07e028a3ac5018c8a9866a6aee061d679cff74a9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="correlateson-definition-dialog-box"></a>Dialogové okno Definice CorrelatesOn
**CorrelatesOn** dialogové okno se používá v [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] upravit <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> vlastnost <xref:System.ServiceModel.Activities.Receive> aktivity. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Receive](../workflow-designer/receive-activity-designer.md) tématu.  
  
 Korelace mezi <xref:System.ServiceModel.Activities.Receive> aktivit Určuje, jak jinou službu, pro operace připojení mezi sebou v pracovním postupu.  
  
 Následující tabulka popisuje prvky uživatelského rozhraní (UI) **CorrelatesOn** dialogové okno.  
  
|Prvek uživatelského rozhraní (UI)|Popis|  
|----------------|-----------------|  
|**CorrelatesWith**|<xref:System.ServiceModel.Activities.CorrelationHandle> Sloužící k směrovat k instanci pracovního postupu příslušná zpráva.|  
|**Dotazy XPath**|Dvojice klíč/hodnota, která obsahuje dotazy použitou k extrakci korelace data z příchozí zprávy. To odpovídá <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> vlastnost. Dotazy XPath jsou součástí <xref:System.ServiceModel.MessageQuerySet> objektu.|  
  
## <a name="to-launch-the-correlateson-dialog-box"></a>Ke spuštění CorrelatesOn dialogových oken  
 **Receive** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kdekoli aktivity jsou obvykle umístěny. Tím se vytvoří <xref:System.ServiceModel.Activities.Receive> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> Receive. Vyberte **Receive** Návrhář aktivity a klikněte na tlačítko se třemi tečkami vedle textu (kolekce) pro **CorrelatesOn** v mřížce vlastnost pro vlastnost **CorrelatesOn definice**  dialogové okno se objeví.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.Activities.Receive>   
 [CorrelationInitializers dialogové okno Přidat](../workflow-designer/add-correlationinitializers-dialog-box.md)   
 [Korelace dialogové okno Přidat](http://msdn.microsoft.com/en-us/9e41a149-e8ab-41b1-8886-ea06a63041b6)   
 [Dialogové okno Inicializace korelace](../workflow-designer/initialize-correlation-dialog-box.md)