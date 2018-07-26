---
title: Dodavatelé portů | Dokumentace Microsoftu
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
ms.openlocfilehash: 5385e006bcd2f79ab7b1c2e723e696b833991f36
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/25/2018
ms.locfileid: "39252346"
---
# <a name="port-suppliers"></a>Dodavatelé portů
V architektuře ladicího programu *dodavatele portu*:  
  
-   Je obsažen podle serveru a poskytuje porty na požadavek na tomto serveru.  
  
-   Můžete přidávat a odebírat porty z nadřazeného serveru.  
  
-   Můžete zobrazit výčet všechny porty, který má zadaný na serveru.  
  
-   Je reprezentován [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) rozhraní, která je registrována pomocí sady Visual Studio prostřednictvím registru. Toto rozhraní lze získat voláním [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md).  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] poskytuje výchozí dodavatele portu a výchozí port. Pokud je nutné implementovat port. Tento vlastní port, dodavatel port. Tento vlastní port také nutné implementovat zadat vlastní porty.  
  
## <a name="see-also"></a>Viz také:  
 [Servery](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [Porty](../../extensibility/debugger/ports.md)   
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)