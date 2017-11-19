---
title: IDebugStackFrame2::EnumProperties | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugStackFrame2::EnumProperties
helpviewer_keywords: IDebugStackFrame2::EnumProperties
ms.assetid: 334bb95e-c7e0-4008-9f06-8c3999e47ee8
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c2679317497568e9f844bcf9503fc0057ca6158c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugstackframe2enumproperties"></a>IDebugStackFrame2::EnumProperties
Vytvoří enumerátor pro vlastnosti související s rámce zásobníku, jako je například místní proměnné.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumProperties (   
   DEBUGPROP_INFO_FLAGS      dwFieldSpec,  
   UINT                      nRadix,  
   REFIID                    refiid,  
   DWORD                     dwTimeout,  
   ULONG*                    pcelt,  
   IEnumDebugPropertyInfo2** ppEnum  
);  
```  
  
```csharp  
int EnumProperties (   
   enum_DEBUGPROP_INFO_FLAGS   dwFieldSpec,  
   uint                        nRadix,  
   ref Guid                    refiid,  
   uint                        dwTimeout,  
   out uint                    pcelt,  
   out IEnumDebugPropertyInfo2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwFieldSpec`  
 [v] Kombinace příznaků z [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) výčet, který určuje pole, která výčtové [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury mají být vyplněna.  
  
 `nRadix`  
 [v] Základ – který se má použít při formátování všechny číselné informace.  
  
 `refiid`  
 [v] Identifikátor GUID filtr použít k výběru, která [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury mají být ve výčtu, například `guidFilterLocals`.  
  
 `dwTimeout`  
 [v] Maximální doba v milisekundách pro čekání před návratem od této metody. Použití `INFINITE` čekání po neomezenou dobu.  
  
 `pcelt`  
 [out] Vrátí počet vlastností ve výčtu. Je to stejné jako volání [GetCount](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-getcount.md) metoda.  
  
 `ppEnum`  
 [out] Vrátí [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) objekt obsahující seznam požadovaných vlastností.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Vzhledem k tomu, že tato metoda umožňuje všechny vybrané vlastnosti, které mají být načteny na základě jednoho volání, je rychlejší než postupně volání [GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md) a [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)   
 [GetCount –](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-getcount.md)   
 [GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)