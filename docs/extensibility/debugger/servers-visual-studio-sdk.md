---
title: Servery (Visual Studio SDK) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- servers, debugging
- debugging [Debugging SDK], servers
ms.assetid: 62236d64-7956-448c-9ac3-5528f3edac1d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2904641e8188abc6ef2382b2da272a9f96fd0f81
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31125489"
---
# <a name="servers-visual-studio-sdk"></a>Servery (Visual Studio SDK)
Z hlediska architektuře ladicího programu **server**:  
  
-   Je kontejnerem porty a všichni dodavatelé port a slouží ke komunikaci porty a všichni dodavatelé port pro relaci ladění správce (SDM) a ladění moduly.  
  
-   Můžete identifikovat podle názvu a výčet jeho porty a všichni dodavatelé portu.  
  
-   Je reprezentována [IDebugCoreServer2](../../extensibility/debugger/reference/idebugcoreserver2.md) rozhraní, což je pouze realizován pomocí sady Visual Studio (jedna instance serveru pro každou instanci sady Visual Studio spuštěná).  
  
## <a name="see-also"></a>Viz také  
 [Porty](../../extensibility/debugger/ports.md)   
 [Port dodavatelů](../../extensibility/debugger/port-suppliers.md)   
 [Koncepty ladicí program](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugCoreServer2](../../extensibility/debugger/reference/idebugcoreserver2.md)