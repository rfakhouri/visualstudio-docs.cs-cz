---
title: IDebugExpressionEvaluator2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugExpressionEvaluator2 interface
ms.assetid: cebe649f-1c77-4d33-854f-30d4f00eceb4
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 840f9be067d591b27bda6a01b6469699524787d1
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63426440"
---
# <a name="idebugexpressionevaluator2"></a>IDebugExpressionEvaluator2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

> [!IMPORTANT]
> V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Představuje rozšířenou verzi vyhodnocovače výrazů (EE).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugExpressionEvaluator2 : IDebugExpressionEvaluator  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní je implementováno vyhodnocovače výrazů.  
  
## <a name="methods"></a>Metody  
 Kromě metod na [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md) rozhraní, toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetService](../../../extensibility/debugger/reference/idebugexpressionevaluator2-getservice.md)|Načte službu objekt dle jejich jedinečného identifikátoru.|  
|[PreloadModules](../../../extensibility/debugger/reference/idebugexpressionevaluator2-preloadmodules.md)|Automaticky načte moduly určený zprostředkovatel zadaný symbol.|  
|[SetCallback](../../../extensibility/debugger/reference/idebugexpressionevaluator2-setcallback.md)|Umožňuje vyhodnocovací filtr výrazů (EE) k určení rozhraní zpětného volání, které modul ladicího programu (DE) bude používat ke čtení nastavení metriky.|  
|[SetCorPath](../../../extensibility/debugger/reference/idebugexpressionevaluator2-setcorpath.md)|Nastavuje cestu ke common language runtime (CLR) načten v ladicím programu.|  
|[SetIDebugIDECallback](../../../extensibility/debugger/reference/idebugexpressionevaluator2-setidebugidecallback.md)|Umožňuje ladicího stroje lze předat zpětné volání pro vyhodnocovací filtr výrazů během inicializace.|  
|[Terminate](../../../extensibility/debugger/reference/idebugexpressionevaluator2-terminate.md)|Zastaví a vyčistí vyhodnocovací filtr výrazů.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: EE.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll
