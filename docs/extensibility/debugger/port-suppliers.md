---
title: Port dodavatelé | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- port suppliers
- debugging [Debugging SDK], port suppliers
ms.assetid: a8f3db96-1a13-4e93-9ef6-0861880369e0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1f1ba09c1802bdeb1c6a402e95a6de408b277532
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31099067"
---
# <a name="port-suppliers"></a>Port dodavatelů
Z hlediska architektuře ladicího programu **port dodavatele**:  
  
-   Je obsažený v serveru a poskytuje porty na požadavek na tomto serveru.  
  
-   Můžete přidávat a odebírat porty ze serveru obsahující.  
  
-   Můžete vytvořit výčet všech portů, který má zadaný na server.  
  
-   Je reprezentována [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) rozhraní, která je registrována pomocí sady Visual Studio prostřednictvím registru. Toto rozhraní je možné získat volání [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md).  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] poskytuje výchozí port dodavatele a výchozí port. Pokud vlastní port musí být implementována, dodavatele vlastní port také musí být implementována k poskytování těchto vlastní porty.  
  
## <a name="see-also"></a>Viz také  
 [Servery](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [Porty](../../extensibility/debugger/ports.md)   
 [Koncepty ladicí program](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)