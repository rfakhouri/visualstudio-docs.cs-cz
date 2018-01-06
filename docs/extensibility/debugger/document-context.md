---
title: Zdokumentujte kontextu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], contexts
ms.assetid: 8e8b5702-5c16-4988-953d-69dd807d8b84
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: b121259f9be23d235386d7156ca8d326c5847f87
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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