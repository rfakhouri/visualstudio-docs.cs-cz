---
title: Kontext kódu | Dokumentace Microsoftu
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
- debugging [Debugging SDK], contexts
ms.assetid: 65e4d37a-086b-426e-9394-a3534967fd59
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4e9ff125a75731de5ca312e5417996f9c6dda764
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669820"
---
# <a name="code-context"></a>Kontext kódu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [kontext kódu](https://docs.microsoft.com/visualstudio/extensibility/debugger/code-context).  
  
V [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladění, **kontext kódu**:  
  
-   Poskytuje abstrakci pozice v kódu, protože ví ladicí stroj (DE). Pro většinu za běhu architektury v současné době kontext kódu můžete představit jako adresa ve službě stream instrukce programu. Pro netradičních jazyky, ve kterém kód nemusí být reprezentována pokyny, může být reprezentována kontext kódu jiným způsobem.  
  
-   Popisuje aktuální pozici v datovém proudu provádění programu, který se právě ladí.  
  
-   Existuje pouze, když se program zastavení na zarážce.  
  
-   Má objekt context přidružený dokument.  
  
-   Je implementováno [IDebugCodeContext2](../../extensibility/debugger/reference/idebugcodecontext2.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Kontext dokumentu](../../extensibility/debugger/document-context.md)   
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)

