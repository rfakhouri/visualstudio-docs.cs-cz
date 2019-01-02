---
title: IDebugProperty2::GetPropertyInfo | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProperty2::GetPropertyInfo
helpviewer_keywords:
- IDebugProperty2::GetPropertyInfo
ms.assetid: 39d6e942-df72-4c84-a5d9-a386d112714c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 773a08d4e49fab85c1d3f44e04f47038ed052b74
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53910672"
---
# <a name="idebugproperty2getpropertyinfo"></a>IDebugProperty2::GetPropertyInfo
Získá [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktura, která popisuje vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetPropertyInfo (   
   DEBUGPROP_INFO_FLAGS dwFields,  
   DWORD                nRadix,  
   DWORD                dwTimeout,  
   IDebugReference2**   rgpArgs,  
   DWORD                dwArgCount,  
   DEBUG_PROPERTY_INFO* pPropertyInfo  
);  
```  
  
```cpp  
int GetPropertyInfo (   
   enum_DEBUGPROP_INFO_FLAGS dwFields,  
   uint                      nRadix,  
   uint                      dwTimeout,  
   IDebugReference2[]        rgpArgs,  
   uint                      dwArgCount,  
   DEBUG_PROPERTY_INFO[]     pPropertyInfo  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwFields`  
 [in] Kombinací hodnot z [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) výčet, který určuje pole, která se mají doplnit `pPropertyInfo` struktury.  
  
 `nRadix`  
 [in] Základ, který se má použít v jakékoli číselné informace o formátování.  
  
 `dwTimeout`  
 [in] Určuje maximální dobu (v milisekundách) čekání před návratem z této metody. Použití `INFINITE` čekat po neomezenou dobu.  
  
 `rgpArgs`  
 [out v] Vyhrazeno pro budoucí použití; Nastavte na hodnotu null.  
  
 `dwArgCount`  
 [in] Vyhrazeno pro budoucí použití; Nastavte na nulu.  
  
 `pPropertyInfo`  
 [out] A [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktura, která se vyplní popis vlastnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)