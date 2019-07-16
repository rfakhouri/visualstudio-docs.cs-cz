---
title: Zarážky (Visual Studio SDK) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- breakpoints
ms.assetid: acfcabed-9f2f-436c-ad18-7ca2f45d631b
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 39c13271bad984291f609ef45505549855bee99f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68146421"
---
# <a name="breakpoints-visual-studio-sdk"></a>Zarážky (Visual Studio SDK)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Existují tři typy zarážky: čekající mez a chyba.  
  
 **A až do zarážky:**  
  
- Je abstrakcí, který obsahuje všechny informace potřebné k vytvoření vazby zarážky na jeden nebo více kontexty kódu v jedné nebo více programů. Pokaždé, když aplikaci právě laděny PŘÍČINA kód pro načtení, ladicí stroj kontroluje všech čekajících zarážek, pokud chcete zobrazit, pokud může být vázána.  
  
   Čekající zarážkou, samotný nikdy váže na kód, ale spíše shromažďuje a se říká, že obsahuje všechny vazby zarážek, které generuje.  
  
- Je reprezentován [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) rozhraní.  
  
  **Vázaná zarážka:**  
  
- Je abstrakcí pro zarážku přidružené nebo svázány s kontextem jeden kód. Každý vázaná zarážka se vygeneruje v reakci na čekající zarážkou. Čekající zarážkou však můžete generovat více než jeden vázaná zarážka.  
  
   Pokud kód je uvolněna, vázaná zarážka může nevázaných a zahodí.  
  
- Je reprezentován [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md) rozhraní.  
  
  **Zarážka k chybě:**  
  
- Je abstrakcí pro popisující chybu při pokusu o čekající zarážkou svázat kontext kódu. K chybě zarážku popisuje buď chybu v umístění nebo samotný výraz zarážky. Další informace najdete v tématu [vazby zarážky](../../extensibility/debugger/binding-breakpoints.md).  
  
   Chyba zarážky může být chyba nebo upozornění.  
  
- Je reprezentován [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Programy](../../extensibility/debugger/programs.md)   
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)   
 [Kontext kódu](../../extensibility/debugger/code-context.md)   
 [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)
