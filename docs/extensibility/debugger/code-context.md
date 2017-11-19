---
title: "Kód kontextu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], contexts
ms.assetid: 65e4d37a-086b-426e-9394-a3534967fd59
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 92d6ed317bcf6ceead42db850ee61969409eb136
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [Kontexty ladicí program](../../extensibility/debugger/debugger-contexts.md)