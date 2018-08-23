---
title: Dodavatelé portů | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- port suppliers
- debugging [Debugging SDK], port suppliers
ms.assetid: a8f3db96-1a13-4e93-9ef6-0861880369e0
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3be95dfdb84f373730d087e9d6da1096891770af
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677683"
---
# <a name="port-suppliers"></a>Dodavatelé portů
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [dodavatelé portů](https://docs.microsoft.com/visualstudio/extensibility/debugger/port-suppliers).  
  
Z hlediska architektury ladicího programu **dodavatele portu**:  
  
-   Je obsažen podle serveru a poskytuje porty na požadavek na tomto serveru.  
  
-   Můžete přidávat a odebírat porty z nadřazeného serveru.  
  
-   Můžete zobrazit výčet všechny porty, který má zadaný na serveru.  
  
-   Je reprezentován [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md) rozhraní, která je registrována pomocí sady Visual Studio prostřednictvím registru. Toto rozhraní lze získat voláním [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md).  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] poskytuje výchozí dodavatele portu a výchozí port. Pokud je nutné implementovat port. Tento vlastní port, dodavatel port. Tento vlastní port také nutné implementovat zadat vlastní porty.  
  
## <a name="see-also"></a>Viz také  
 [Servery](../../extensibility/debugger/servers-visual-studio-sdk.md)   
 [Porty](../../extensibility/debugger/ports.md)   
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [GetPortSupplier](../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)

