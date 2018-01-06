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
ms.workload: vssdk
ms.openlocfilehash: ab4e57f500c2dfbfe673713c784cbc93ff52a73d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="expression-evaluation-context"></a>Kontext vyhodnocení výrazu
V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění, **kontext vyhodnocení výrazu**:  
  
-   Představuje kontext pro vyhodnocení výrazu. Obecně platí kontextu vyhodnocení odpovídá lexikální oboru, ve kterém k vyhodnocení proměnné, parametry, funkce a metody. Například kontextu vyhodnocení výrazu přidružené rámce zásobníku poskytne kontext pro vyhodnocení lokální proměnné, parametry metody a členy třídy (pokud existuje).  
  
-   Existuje, když program byla zastavena v zarážky. Samotného výrazu je datová struktura představující Analyzovaná výraz, který je připraven pro vazby a vyhodnocení v daném kontextu.  
  
     Podrobněji, výrazy se vytvářejí pomocí [ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md) metoda. Při vyhodnocování výrazu generuje tisknutelná řetězec obsahující název a typ proměnné nebo argument a jeho hodnotu. V okně Sledování nebo v místní hodnoty – okno rozhraní IDE, zobrazí se tento řetězec.  
  
     Zadané `BSTR` a [IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md) rozhraní, můžete vytvořit modul ladění (DE) [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) rozhraní analýzou výrazu. Vzhledem `IDebugExpression2` rozhraní, DE můžete získat hodnotu prostřednictvím vyhodnocení výrazu synchronní nebo asynchronní. Tato hodnota, společně s název a typ proměnné nebo argument, je odeslán rozhraní IDE pro zobrazení.  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní vyhodnocení výrazu](../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [Kontexty ladicího programu](../../extensibility/debugger/debugger-contexts.md)