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
ms.openlocfilehash: 96d5e3e34a6827e7871b053501c61e9c4c98ae26
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54764266"
---
# <a name="document-context"></a>Kontext dokumentu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

V [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladění, **kontext dokumentu**:  
  
-   Představuje pozici ve zdrojovém souboru. Kontext dokumentu pro jazyky, kde nemusí být zdrojový soubor existuje, identifikuje pozici v dokumentu obvykle generovaných běhového prostředí. Například skriptovací stroj může generovat dokument ze skriptu. Další informace najdete v tématu [pozice dokumentu](../../extensibility/debugger/document-position.md).  
  
-   Popisuje umístění ve zdrojovém dokumentu, který odpovídá kontext kódu. Obslužné rutiny symbolů mapuje na dokumentaci kontextu, pomocí informací generovaných kompilátor nebo překladač kontext kódu.  
  
-   Je implementováno [IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Kontext kódu](../../extensibility/debugger/code-context.md)   
 [Poskytovatel symbolů](../../extensibility/debugger/symbol-provider.md)   
 [Rozhraní poskytovatele symbolů](../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)
