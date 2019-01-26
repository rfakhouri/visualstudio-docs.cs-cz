---
title: Zarážky (Visual Studio SDK) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- breakpoints
ms.assetid: acfcabed-9f2f-436c-ad18-7ca2f45d631b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a2898a78971eaf20abe89274a1492afb343edfbb
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54919392"
---
# <a name="breakpoints-visual-studio-sdk"></a>Zarážky (Visual Studio SDK)
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
  
- Je abstrakcí pro popisující chybu při pokusu o čekající zarážkou svázat kontext kódu. K chybě zarážku popisuje buď chybu v umístění nebo samotný výraz zarážky. Další informace najdete v tématu [vytváření vazeb zarážek](../../extensibility/debugger/binding-breakpoints.md).  
  
   Chyba zarážky může být chyba nebo upozornění.  
  
- Je reprezentován [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) rozhraní.  
  
## <a name="see-also"></a>Viz také:  
 [Programy](../../extensibility/debugger/programs.md)   
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)   
 [Kontext kódu](../../extensibility/debugger/code-context.md)   
 [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)