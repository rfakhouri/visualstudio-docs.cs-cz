---
title: Kontext vyhodnocení výrazu | Dokumentace Microsoftu
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
- expression evaluation, context
ms.assetid: a2fd3758-09bd-45ae-8ecc-2d276c0036ba
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fc2c2ecc4f7867c2ad39ba72f9edcb72c0935ce5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666605"
---
# <a name="expression-evaluation-context"></a>Kontext vyhodnocení výrazu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [kontext vyhodnocení výrazu](https://docs.microsoft.com/visualstudio/extensibility/debugger/expression-evaluation-context).  
  
V [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladění, **kontext vyhodnocení výrazu**:  
  
-   Představuje kontext pro vyhodnocení výrazu. Obecně platí objekt context hodnocení odpovídá lexikálním rozsahu, ve kterém se mají vyhodnocovat proměnné, parametry, funkce a metody. Třeba kontextu vyhodnocení výrazu přidružený blok zásobníku obsahují souvislosti za vaše rozhodnutí vyzkoušet lokální proměnné, parametry metody a členy třídy (pokud existuje).  
  
-   Existuje, když program byl zastaven na zarážce. Samotný výraz je datová struktura představující analyzovaný výraz, který je připravený pro vytvoření vazby a hodnocení v daném kontextu.  
  
     Podrobněji se vytvoří pomocí výrazů [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) metoda. Při vyhodnocování výrazu generuje tisknutelný řetězec obsahující název a typ proměnné nebo argumentu a jeho hodnotu. Tento řetězec se zobrazí v okně kukátka nebo v okně místních hodnot rozhraní IDE.  
  
     Zadaný `BSTR` a [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní, můžete vytvořit ladicí stroj (DE) [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) rozhraní analýzou výrazu. Vzhledem `IDebugExpression2` rozhraní, DE můžete získat hodnotu prostřednictvím vyhodnocení výrazu synchronní nebo asynchronní. Tuto hodnotu, spolu s názvem a typem proměnné nebo argumentu, je odeslána do integrovaného vývojového prostředí pro zobrazení.  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní pro vyhodnocení výrazu](../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)

