---
title: IDebugContainerField | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugContainerField
helpviewer_keywords: IDebugContainerField interface
ms.assetid: a8bbe061-c382-4fe9-a193-3f7d12216041
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8260266f43be7a6887aea45f5012a1924fd35c77
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugcontainerfield"></a>IDebugContainerField
Toto rozhraní představuje symbol nebo typ, který je kontejner pro další symboly nebo typy.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugContainerField : IDebugField  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní implementuje poskytovatele symbol pro stejný objekt, který implementuje [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní. Toto rozhraní je také základní třídu pro všechna rozhraní, které představují kontejnery.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Mnoho způsobů na mnoho rozhraní vrátí toto rozhraní. Vzhledem k tomu, že toto je základní třída pro všechny kontejnery, více specializované rozhraní můžete získat z tohoto rozhraní pomocí [QueryInterface](/cpp/atl/queryinterface). Taková rozhraní pro zahrnují [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md), [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md), [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md), a [IDebugPropertyField](../../../extensibility/debugger/reference/idebugpropertyfield.md).  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod na [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní, toto rozhraní implementuje následující metodu:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Enumfields –](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)|Vytvoří enumerátor pro pole kontejneru.|  
  
## <a name="remarks"></a>Poznámky  
 Pole (kontejnery pro proměnné), (kontejnery pro metody a proměnné) třídy a metody (kontejnery pro parametry a místní proměnné) jsou všechny příklady kontejnerů.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Zprostředkovatel rozhraní symbol](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)