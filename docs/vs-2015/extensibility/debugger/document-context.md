---
title: Kontext dokumentu | Dokumentace Microsoftu
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
ms.assetid: 8e8b5702-5c16-4988-953d-69dd807d8b84
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7a9e92976af5e098dca0d1a4bb81c777eb38a9f5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668891"
---
# <a name="document-context"></a>Kontext dokumentu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [kontext dokumentu](https://docs.microsoft.com/visualstudio/extensibility/debugger/document-context).  
  
V [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladění, **kontext dokumentu**:  
  
-   Představuje pozici ve zdrojovém souboru. Kontext dokumentu pro jazyky, kde nemusí být zdrojový soubor existuje, identifikuje pozici v dokumentu obvykle generovaných běhového prostředí. Například skriptovací stroj může generovat dokument ze skriptu. Další informace najdete v tématu [pozice dokumentu](../../extensibility/debugger/document-position.md).  
  
-   Popisuje umístění ve zdrojovém dokumentu, který odpovídá kontext kódu. Obslužné rutiny symbolů mapuje na dokumentaci kontextu, pomocí informací generovaných kompilátor nebo překladač kontext kódu.  
  
-   Je implementováno [IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Kontext kódu](../../extensibility/debugger/code-context.md)   
 [Poskytovatel symbolů](../../extensibility/debugger/symbol-provider.md)   
 [Rozhraní poskytovatele symbolů](../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)

