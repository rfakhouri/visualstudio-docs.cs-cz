---
title: Kód kontextu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 65e4d37a-086b-426e-9394-a3534967fd59
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9a84596246ae930cdffc0265f2f2e09652661819
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="code-context"></a>Kontext kódu
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění, **kontext kódu**:  
  
-   Poskytuje abstrakci pozice v kódu, protože znám modul ladění (DE). Pro většinu architektury Runtime v současné době kontext kódu může považovat za adresu v datovém proudu instrukce programu. Pro netradičních jazyky, kde nemusí být reprezentován kód podle pokynů, může být reprezentován kontext kódu jiným způsobem.  
  
-   Popisuje aktuální pozici v datovém proudu provádění programu laděné.  
  
-   Existuje, pouze když program přestal na zarážce.  
  
-   Má kontextu přidružené dokumentu.  
  
-   Je implementováno modulem [IDebugCodeContext2](../../extensibility/debugger/reference/idebugcodecontext2.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Kontext dokumentu](../../extensibility/debugger/document-context.md)   
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)