---
title: IDebugProperty2::EnumChildren | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProperty2::EnumChildren
helpviewer_keywords:
- IDebugProperty2::EnumChildren
ms.assetid: cf79f666-65d1-417c-af7c-9271bac9a267
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8996bf5cc5ed295bf7449e44f505fa0b87523f6b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677338"
---
# <a name="idebugproperty2enumchildren"></a>IDebugProperty2::EnumChildren
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugProperty2::EnumChildren](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugproperty2-enumchildren).  
  
Načte seznam podřízených prvků vlastnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT EnumChildren (   
   DEBUGPROP_INFO_FLAGS      dwFields,  
   DWORD                     dwRadix,  
   REFGUID                   guidFilter,  
   DBG_ATTRIB_FLAGS          dwAttribFilter,  
   LPCOLESTR                 pszNameFilter,  
   DWORD                     dwTimeout,  
   IEnumDebugPropertyInfo2** ppEnum  
);  
```  
  
```csharp  
int EnumChildren (   
   enum_DEBUGPROP_INFO_FLAGS   dwFields,  
   uint                        dwRadix,  
   ref Guid                    guidFilter,  
   uint                        dwAttribFilter,  
   string                      pszNameFilter,  
   uint                        dwTimeout,  
   out IEnumDebugPropertyInfo2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwFields`  
 [in] Kombinace příznaků z [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) výčet, který určuje pole, která v výčtu [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury mají být vyplněna.  
  
 `dwRadix`  
 [in] Určuje základ, který se má použít v jakékoli číselné informace o formátování.  
  
 `guidFilter`  
 [in] Identifikátor GUID používá se filtr `dwAttribFilter` a `pszNameFilter` parametry se mají vybrat, na které `DEBUG_PROPERTY_INFO` podřízené objekty jsou pro provedení výčtu. Například `guidFilterLocals` filtry pro místní proměnné.  
  
 `dwAttribFilter`  
 [in] Kombinace příznaků z [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) výčet, který určuje, jaký typ objektů, které chcete zobrazit výčet, například `DBG_ATTRIB_METHOD` pro všechny metody, které můžou být podřízené této vlastnosti. V kombinaci s `guidFilter` a `pszNameFilter` parametry.  
  
 `pszNameFilter`  
 [in] Název filtru použít s `guidFilter` a `dwAttribFilter` parametry se mají vybrat, na které `DEBUG_PROPERTY_INFO` podřízené objekty jsou pro provedení výčtu. Příklad nastavení tohoto parametru na "MyX" filtry pro všechny podřízené objekty s názvem "MyX."  
  
 `dwTimeout`  
 [in] Určuje maximální dobu (v milisekundách) čekání před návratem z této metody. Použití `INFINITE` čekat po neomezenou dobu.  
  
 `ppEnum`  
 [out] Vrátí [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) objekt, který obsahuje seznam vlastností podřízené.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)   
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)

