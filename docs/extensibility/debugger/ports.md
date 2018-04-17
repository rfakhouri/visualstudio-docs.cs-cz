---
title: Porty | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- ports
- debugging [Debugging SDK], ports
ms.assetid: 1d7f3aa7-7eff-4cab-bc53-0a566b1a9363
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a350e0579f7e60d8a7ffc3e879d79364cfdf0317
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ports"></a>Porty
Z hlediska architektuře ladicího programu **port**:  
  
-   Je kontejner pro sadu procesy spuštěna na serveru. Port mohou například představovat připojení na zařízení se systémem Windows CE podle sériový kabel nebo k síti bez DCOM počítače. Jeden speciální port názvem místního portu obsahuje všechny procesy spuštěné v místním počítači.  
  
-   Lze identifikovat podle názvu nebo identifikátor.  
  
-   Můžete vytvořit výčet všech procesů spuštěných na port a spusťte a ukončete tyto procesy.  
  
-   Je reprezentována [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md) rozhraní, která je vytvořena pomocí předání [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md) argument [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md).  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] poskytuje výchozí port, který zpracovává všechny založené na Windows procesy, nativní a spravovaná. Vlastní port musí být implementované připojení s externí zařízení, které nejsou založené na systému Windows. K poskytování těchto vlastní porty, vlastní port dodavatele také musí být implementována.  
  
## <a name="see-also"></a>Viz také  
 [Servery](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [Procesy](../../extensibility/debugger/processes.md)   
 [Koncepty ladicí program](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugPortRequest2](../../extensibility/debugger/reference/idebugportrequest2.md)   
 [AddPort](../../extensibility/debugger/reference/idebugportsupplier2-addport.md)