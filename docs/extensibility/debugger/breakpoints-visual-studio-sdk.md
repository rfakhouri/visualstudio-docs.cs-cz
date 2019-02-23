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
ms.openlocfilehash: 4c353ca11df1a897ec5dc8acecd822c1c1f44e92
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56707026"
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
- [Programy](../../extensibility/debugger/programs.md)
- [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md)
- [Kontext kódu](../../extensibility/debugger/code-context.md)
- [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md)
- [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)
- [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)