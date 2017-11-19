---
title: "Kontext vyhodnocení výrazu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: expression evaluation, context
ms.assetid: a2fd3758-09bd-45ae-8ecc-2d276c0036ba
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1ac80a3fcf3a7f75be3f23dd1350da047ccbb393
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="expression-evaluation-context"></a>Kontext vyhodnocení výrazu
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění, **kontext vyhodnocení výrazu**:  
  
-   Představuje kontext pro vyhodnocení výrazu. Obecně platí kontextu vyhodnocení odpovídá lexikální oboru, ve kterém k vyhodnocení proměnné, parametry, funkce a metody. Například kontextu vyhodnocení výrazu přidružené rámce zásobníku poskytne kontext pro vyhodnocení lokální proměnné, parametry metody a členy třídy (pokud existuje).  
  
-   Existuje, když program byla zastavena v zarážky. Samotného výrazu je datová struktura představující Analyzovaná výraz, který je připraven pro vazby a vyhodnocení v daném kontextu.  
  
     Podrobněji, výrazy se vytvářejí pomocí [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) metoda. Při vyhodnocování výrazu generuje tisknutelná řetězec obsahující název a typ proměnné nebo argument a jeho hodnotu. V okně Sledování nebo v místní hodnoty – okno rozhraní IDE, zobrazí se tento řetězec.  
  
     Zadané `BSTR` a [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní, můžete vytvořit modul ladění (DE) [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) rozhraní analýzou výrazu. Vzhledem `IDebugExpression2` rozhraní, DE můžete získat hodnotu prostřednictvím vyhodnocení výrazu synchronní nebo asynchronní. Tato hodnota, společně s název a typ proměnné nebo argument, je odeslán rozhraní IDE pro zobrazení.  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní vyhodnocení výrazu](../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [Kontexty ladicí program](../../extensibility/debugger/debugger-contexts.md)