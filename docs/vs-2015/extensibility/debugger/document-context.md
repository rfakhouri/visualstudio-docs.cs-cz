---
title: Kontext dokumentu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 8e8b5702-5c16-4988-953d-69dd807d8b84
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 3034c9ca02fca8e91eb1aa5e4d0eb5a2fe1f773f
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60080030"
---
# <a name="document-context"></a>Kontext dokumentu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

V [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladění, **kontext dokumentu**:  
  
- Představuje pozici ve zdrojovém souboru. Kontext dokumentu pro jazyky, kde nemusí být zdrojový soubor existuje, identifikuje pozici v dokumentu obvykle generovaných běhového prostředí. Například skriptovací stroj může generovat dokument ze skriptu. Další informace najdete v tématu [pozice dokumentu](../../extensibility/debugger/document-position.md).  
  
- Popisuje umístění ve zdrojovém dokumentu, který odpovídá kontext kódu. Obslužné rutiny symbolů mapuje na dokumentaci kontextu, pomocí informací generovaných kompilátor nebo překladač kontext kódu.  
  
- Je implementováno [IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Kontext kódu](../../extensibility/debugger/code-context.md)   
 [Poskytovatel symbolů](../../extensibility/debugger/symbol-provider.md)   
 [Rozhraní poskytovatele symbolů](../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)
