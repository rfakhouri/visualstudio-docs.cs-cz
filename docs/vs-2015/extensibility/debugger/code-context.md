---
title: Kontext kódu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 65e4d37a-086b-426e-9394-a3534967fd59
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d59a4c79cb21386fa6f6e7031404aeb0b435b3b9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68197377"
---
# <a name="code-context"></a>Kontext kódu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

V [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladění, **kontext kódu**:  
  
- Poskytuje abstrakci pozice v kódu, protože ví ladicí stroj (DE). Pro většinu za běhu architektury v současné době kontext kódu můžete představit jako adresa ve službě stream instrukce programu. Pro netradičních jazyky, ve kterém kód nemusí být reprezentována pokyny, může být reprezentována kontext kódu jiným způsobem.  
  
- Popisuje aktuální pozici v datovém proudu provádění programu, který se právě ladí.  
  
- Existuje pouze, když se program zastavení na zarážce.  
  
- Má objekt context přidružený dokument.  
  
- Je implementováno [IDebugCodeContext2](../../extensibility/debugger/reference/idebugcodecontext2.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Kontext dokumentu](../../extensibility/debugger/document-context.md)   
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)
