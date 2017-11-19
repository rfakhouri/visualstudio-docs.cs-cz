---
title: "Kontext vyhodnocení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, context
ms.assetid: 008a20c7-1b27-4013-bf96-d6a3f510da02
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5a44d7ce7cffa2afc40971b0ea6f88a6f62617f3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="evaluation-context"></a>Kontext vyhodnocení
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Když modul ladění (DE) volá vyhodnocovací filtr výrazů (EE), tři argumenty předaný [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) zjistit kontext pro hledání a vyhodnocení symboly, jak je znázorněno v následující tabulce.  
  
## <a name="arguments"></a>Arguments  
  
|Argument|Popis|  
|--------------|-----------------|  
|`pSymbolProvider`|[IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md) rozhraní, které obslužná rutina symbol (SH) určuje, který se má použít k určení symbolu.|  
|`pAddress`|[IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md) rozhraní, které určuje aktuálního bodu provádění. To můžete použít k vyhledání metodu, která obsahuje kód spouštěna.|  
|`pBinder`|[IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) rozhraní, které můžete použít k vyhledání hodnoty a typ symbolu, jeho název.|  
  
 `IDebugParsedExpression::EvaluateSync`Vrátí [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) rozhraní představující výsledná hodnota a jeho typu.  
  
## <a name="see-also"></a>Viz také  
 [Výraz klíče vyhodnocování rozhraní](../../extensibility/debugger/key-expression-evaluator-interfaces.md)   
 [Zobrazení místní hodnoty](../../extensibility/debugger/displaying-locals.md)   
 [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)   
 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)