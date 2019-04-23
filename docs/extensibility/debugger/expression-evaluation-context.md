---
title: Kontext vyhodnocení výrazu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- expression evaluation, context
ms.assetid: a2fd3758-09bd-45ae-8ecc-2d276c0036ba
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6f8e2347595a5bf7723c4a72b1f57a3f42a2ab5a
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60069704"
---
# <a name="expression-evaluation-context"></a>Kontext vyhodnocení výrazu
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění, **kontext vyhodnocení výrazu**:

- Představuje kontext pro vyhodnocení výrazu. Obecně platí objekt context hodnocení odpovídá lexikálním rozsahu, ve kterém se mají vyhodnocovat proměnné, parametry, funkce a metody. Třeba kontextu vyhodnocení výrazu přidružený blok zásobníku obsahují souvislosti za vaše rozhodnutí vyzkoušet lokální proměnné, parametry metody a členy třídy (pokud existuje).

- Existuje, když program byl zastaven na zarážce. Samotný výraz je datová struktura představující analyzovaný výraz, který je připravený pro vytvoření vazby a hodnocení v daném kontextu.

     Podrobněji se vytvoří pomocí výrazů [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) metoda. Při vyhodnocování výrazu generuje tisknutelný řetězec obsahující název a typ proměnné nebo argumentu a jeho hodnotu. Tento řetězec se zobrazí v okně kukátka nebo v okně místních hodnot rozhraní IDE.

     Zadaný `BSTR` a [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní, můžete vytvořit ladicí stroj (DE) [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) rozhraní analýzou výrazu. Vzhledem `IDebugExpression2` rozhraní, DE můžete získat hodnotu prostřednictvím vyhodnocení výrazu synchronní nebo asynchronní. Tuto hodnotu, spolu s názvem a typem proměnné nebo argumentu, je odeslána do integrovaného vývojového prostředí pro zobrazení.

## <a name="see-also"></a>Viz také:
- [Rozhraní pro vyhodnocení výrazu](../../extensibility/debugger/reference/expression-evaluation-interfaces.md)
- [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)