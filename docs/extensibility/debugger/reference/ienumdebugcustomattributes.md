---
title: IEnumDebugCustomAttributes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumCustomAttributes
helpviewer_keywords: IEnumDebugCustomAttributes interface
ms.assetid: 11aa768d-1852-44d6-9de3-17f9bafaded2
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 90f4ccbe56b57a963afaa02a5e07ded4ec5b6933
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugcustomattributes"></a>IEnumDebugCustomAttributes
Vytvoří výčet vlastní atributy.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumCustomAttributes : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Symbol zprostředkovatele implementuje toto rozhraní pro podporu vlastních atributů (prostřednictvím [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md) rozhraní).  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 [Enumcustomattributes –](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md) vrátí toto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IEnumDebugCustomAttributes`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugcustomattributes-next.md)|Načte zadaný počet vlastních atributů v posloupnosti výčtu.|  
|[Přeskočit](../../../extensibility/debugger/reference/ienumdebugcustomattributes-skip.md)|Přeskočí zadaný počet vlastních atributů v posloupnosti výčtu.|  
|[Resetování](../../../extensibility/debugger/reference/ienumdebugcustomattributes-reset.md)|Návrat na začátek v sekvenci výčtu.|  
|[Klonování](../../../extensibility/debugger/reference/ienumdebugcustomattributes-clone.md)|Vytvoří enumerátor, který obsahuje stav výčtu jako aktuální enumerátor.|  
|[GetCount –](../../../extensibility/debugger/reference/ienumdebugcustomattributes-getcount.md)|Získá počet vlastních atributů v enumerátor.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Zprostředkovatel rozhraní symbol](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [Enumcustomattributes –](../../../extensibility/debugger/reference/idebugcustomattributequery2-enumcustomattributes.md)   
 [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)