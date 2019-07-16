---
title: Dodavatelé portů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- port suppliers
- debugging [Debugging SDK], port suppliers
ms.assetid: a8f3db96-1a13-4e93-9ef6-0861880369e0
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e90871927c30399dea4691381baa749db2b3e8bf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68153709"
---
# <a name="port-suppliers"></a>Dodavatelé portů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Z hlediska architektury ladicího programu **dodavatele portu**:  
  
- Je obsažen podle serveru a poskytuje porty na požadavek na tomto serveru.  
  
- Můžete přidávat a odebírat porty z nadřazeného serveru.  
  
- Můžete zobrazit výčet všechny porty, který má zadaný na serveru.  
  
- Je reprezentován [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) rozhraní, která je registrována pomocí sady Visual Studio prostřednictvím registru. Toto rozhraní lze získat voláním [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md).  
  
  [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] poskytuje výchozí dodavatele portu a výchozí port. Pokud je nutné implementovat port. Tento vlastní port, dodavatel port. Tento vlastní port také nutné implementovat zadat vlastní porty.  
  
## <a name="see-also"></a>Viz také  
 [Servery](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [Porty](../../extensibility/debugger/ports.md)   
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)
