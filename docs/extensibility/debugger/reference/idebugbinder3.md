---
title: IDebugBinder3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugBinder3
helpviewer_keywords: IDebugBinder3 interface
ms.assetid: 92353a74-dc74-4f93-8762-61d6b220478c
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 43465f919806f16154b8f3328aad7496c83ec235
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugbinder3"></a>IDebugBinder3
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Toto rozhraní poskytuje přístup k typy, aliasy i vlastní vizualizér služby.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugBinder3 : IDebugBinder  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění implementuje toto rozhraní pro podporu aliasy, vlastní vizualizér služeb a přístup k informace o typu objektu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) rozhraní obdrží toto rozhraní pomocí [QueryInterface](/cpp/atl/queryinterface).  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod od [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) rozhraní, toto rozhraní implementuje následující:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetMemoryObject](../../../extensibility/debugger/reference/idebugbinder3-getmemoryobject.md)|Načte objekt paměti představující paměti, ke kterému je vázán tento objekt.|  
|[GetExceptionObjectAndType](../../../extensibility/debugger/reference/idebugbinder3-getexceptionobjectandtype.md)|Načte výjimka přidružené k tomuto objektu (pokud existuje)|  
|[FindAlias](../../../extensibility/debugger/reference/idebugbinder3-findalias.md)|Načte alias jeho název|  
|[GetAllAliases](../../../extensibility/debugger/reference/idebugbinder3-getallaliases.md)|Načte pole všechny aliasy pro tento objekt|  
|[Gettypeargumentcount –](../../../extensibility/debugger/reference/idebugbinder3-gettypeargumentcount.md)|Získá počet typy argumentů, které jsou přidružené k tomuto objektu|  
|[Gettypearguments –](../../../extensibility/debugger/reference/idebugbinder3-gettypearguments.md)|Načte seznam typů argument přidružené k tomuto objektu|  
|[GetEEService](../../../extensibility/debugger/reference/idebugbinder3-geteeservice.md)|Získá rozhraní službě vizualizér,|  
|[GetMemoryContext64](../../../extensibility/debugger/reference/idebugbinder3-getmemorycontext64.md)|Převede na objekt umístění nebo adresu paměti 64-bit paměti kontextu.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)