---
title: Dialogové okno definice vlastnosti CorrelatesOn | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- CorrelatesOnDefinition.UI
ms.assetid: 8b2b627a-f236-4479-aa09-525df65e3413
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: fd03e1a8615e75d3f00f79eb10b7a7ff97f0eb33
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62977377"
---
# <a name="correlateson-definition-dialog-box"></a>Dialogové okno Definice vlastnosti CorrelatesOn
**Vlastnosti CorrelatesOn** dialogové okno se používá v [!INCLUDE[wfd1](../includes/wfd1-md.md)] upravit <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> vlastnost <xref:System.ServiceModel.Activities.Receive> aktivity. [!INCLUDE[crdefault](../includes/crdefault-md.md)] [Receive](../workflow-designer/receive-activity-designer.md) tématu.  
  
 Korelace mezi <xref:System.ServiceModel.Activities.Receive> aktivit Určuje, jak různé služby operace připojení mezi sebou v pracovním postupu.  
  
 Následující tabulka popisuje prvky uživatelského rozhraní (UI) **vlastnosti CorrelatesOn** dialogové okno.  
  
|Prvek uživatelského rozhraní (UI)|Popis|  
|----------------|-----------------|  
|**CorrelatesWith**|<xref:System.ServiceModel.Activities.CorrelationHandle> , Který slouží k zprávy směruje do instance odpovídající pracovního postupu.|  
|**Dotazy XPath**|Dvojice klíč/hodnota, která obsahuje dotazy používané k extrakci korelace dat z příchozí zprávy. To odpovídá <xref:System.ServiceModel.Activities.Receive.CorrelatesOn%2A> vlastnost. Jsou součástí dotazy XPath <xref:System.ServiceModel.MessageQuerySet> objektu.|  
  
## <a name="to-launch-the-correlateson-dialog-box"></a>Chcete-li spustit dialogové okno Vlastnosti CorrelatesOn  
 **Receive** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřazené k [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface všude, kde aktivity jsou obvykle umístěny. Tím se vytvoří <xref:System.ServiceModel.Activities.Receive> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> Receive. Vyberte **Receive** návrháře aktivit a klikněte na tlačítko se třemi tečkami vedle textu (kolekce) pro **vlastnosti CorrelatesOn** v mřížce vlastností pro vlastnost **definice vlastnosti CorrelatesOn**  dialogového okna.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ServiceModel.Activities.Receive>   
 [Přidat inicializátory korelace dialogové okno](../workflow-designer/add-correlationinitializers-dialog-box.md)   
 [Dialogové okno Inicializace korelace](../workflow-designer/initialize-correlation-dialog-box.md)