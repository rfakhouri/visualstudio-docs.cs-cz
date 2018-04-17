---
title: Zdokumentujte kontextu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 8e8b5702-5c16-4988-953d-69dd807d8b84
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8f97df9bc3c0a40a44379ba37f1b36d79cffb74e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="document-context"></a>Kontext dokumentu
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění, **kontextu dokumentu**:  
  
-   Představuje pozici ve zdrojovém souboru. Pro jazyky, kde nemusí být zdrojový soubor existuje identifikuje kontextu dokumentu pozici v dokumentu obvykle generované běhové prostředí. Například skriptovací stroj může vygenerovat dokumentu ze skriptu. Další informace najdete v tématu [dokumentu pozice](../../extensibility/debugger/document-position.md).  
  
-   Popisuje pozici ve zdrojovém dokumentu, která odpovídá kódu kontextu. Obslužná rutina symbol mapuje kontext kódu na dokumentaci kontextu, pomocí informací o generovaných kompilátoru nebo překladač.  
  
-   Je implementováno modulem [IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Kontext kódu](../../extensibility/debugger/code-context.md)   
 [Symbol zprostředkovatele](../../extensibility/debugger/symbol-provider.md)   
 [Zprostředkovatel rozhraní symbol](../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)