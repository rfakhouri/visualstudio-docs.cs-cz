---
title: Idebugstackframe – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugStackFrame interface
ms.assetid: e95c1b4f-17c1-490c-a56b-c25fa45d4822
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d8f645d6460ff15734348267b5138b1b6edea071
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58149546"
---
# <a name="idebugstackframe-interface"></a>IDebugStackFrame – rozhraní
Představuje rámec zásobníku logického zásobníku vlákna. Volání `IDebugStackFrame::QueryInterface` metodu k získání `IDebugExpressionContext` rozhraní, které umožňuje výraz hodnocení a sledovat.  
  
 Kromě metod zděděných z `IUnknown`, `IDebugStackFrame` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugStackFrame::GetCodeContext](../../winscript/reference/idebugstackframe-getcodecontext.md)|Vrátí aktuální kontext kódu přidružené k rámce zásobníku.|  
|[IDebugStackFrame::GetDescriptionString](../../winscript/reference/idebugstackframe-getdescriptionstring.md)|Vrátí krátký nebo long textový popis rámce zásobníku.|  
|[IDebugStackFrame::GetLanguageString](../../winscript/reference/idebugstackframe-getlanguagestring.md)|Vrátí krátký nebo long textový popis jazyka.|  
|[IDebugStackFrame::GetThread](../../winscript/reference/idebugstackframe-getthread.md)|Vrátí vlákno přidružené k tento rámec zásobníku.|  
|[IDebugStackFrame::GetDebugProperty](../../winscript/reference/idebugstackframe-getdebugproperty.md)|Vrátí prohlížeč vlastnost pro aktuální rámec.|