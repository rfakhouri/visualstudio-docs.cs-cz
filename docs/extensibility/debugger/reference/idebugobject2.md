---
title: IDebugObject2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugObject2
helpviewer_keywords:
- IDebugObject2 interface
ms.assetid: ef640967-8adb-4793-994d-ae1736510891
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 40b52cf5c36db3bf4fa07004df9a171e77c2520e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugobject2"></a>IDebugObject2
> [!IMPORTANT]
>  V sadě Visual Studio 2015 se již nepoužívá tímto způsobem implementace vyhodnocovače výrazů. Informace o implementaci vyhodnocovače výrazů CLR, najdete v tématu [vyhodnocovače výrazů CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Toto rozhraní obsahuje další informace o objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugObject2 : IDebugObject  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Vyhodnocení výrazu implementuje toto rozhraní pro podporu pro aliasy a přístup k informacím o objektu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) rozhraní můžete získat pomocí tohoto rozhraní [QueryInterface](/cpp/atl/queryinterface). Navíc [GetObject](../../../extensibility/debugger/reference/idebugalias-getobject.md) vrátí toto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod na [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) rozhraní, `IDebugObject2` rozhraní implementuje následující:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetBackingFieldForProperty](../../../extensibility/debugger/reference/idebugobject2-getbackingfieldforproperty.md)|Získá pole nebo proměnná (pokud existuje), může být zálohování vlastnost představuje tento objekt.|  
|[GetICorDebugValue](../../../extensibility/debugger/reference/idebugobject2-geticordebugvalue.md)|Získá objekt spravovaný kód představující hodnotu tohoto objektu.|  
|[CreateAlias](../../../extensibility/debugger/reference/idebugobject2-createalias.md)|Vytvoří jedinečný ID pro tento objekt nebo vrátí existující alias.|  
|[GetAlias](../../../extensibility/debugger/reference/idebugobject2-getalias.md)|Získá alias přidružený k tomuto objektu, pokud existuje.|  
|[GetField](../../../extensibility/debugger/reference/idebugobject2-getfield.md)|Získá typ tohoto objektu.|  
|[IsUserData](../../../extensibility/debugger/reference/idebugobject2-isuserdata.md)|Určuje, zda tento objekt představuje data uživatele.|  
|[IsEncOutdated](../../../extensibility/debugger/reference/idebugobject2-isencoutdated.md)|Určuje, zda stavu upravit a pokračovat, je již neplatný.<br /><br /> Vlastní výraz vyhodnocování neimplementuje tuto metodu (vždy by měla vrátit `E_NOTIMPL`).|  
  
## <a name="remarks"></a>Poznámky  
 V tématu [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) podrobné informace o aliasy.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní vyhodnocení výrazu](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)   
 [Funkce GetObject](../../../extensibility/debugger/reference/idebugalias-getobject.md)