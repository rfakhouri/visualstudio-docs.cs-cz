---
title: IDebugProperty2::EnumChildren | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty2::EnumChildren
helpviewer_keywords:
- IDebugProperty2::EnumChildren
ms.assetid: cf79f666-65d1-417c-af7c-9271bac9a267
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: aed98522d98162c13d6cfbcbc61df2a989f35434
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66211634"
---
# <a name="idebugproperty2enumchildren"></a>IDebugProperty2::EnumChildren
Načte seznam podřízených prvků vlastnost.

## <a name="syntax"></a>Syntaxe

```cpp
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

## <a name="parameters"></a>Parametry
`dwFields`\
[in] Kombinace příznaků z [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) výčet, který určuje pole, která v výčtu [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury mají být vyplněna.

`dwRadix`\
[in] Určuje základ, který se má použít v jakékoli číselné informace o formátování.

`guidFilter`\
[in] Identifikátor GUID používá se filtr `dwAttribFilter` a `pszNameFilter` parametry se mají vybrat, na které `DEBUG_PROPERTY_INFO` podřízené objekty jsou pro provedení výčtu. Například `guidFilterLocals` filtry pro místní proměnné.

`dwAttribFilter`\
[in] Kombinace příznaků z [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) výčet, který určuje, jaký typ objektů, které chcete zobrazit výčet, například `DBG_ATTRIB_METHOD` pro všechny metody, které můžou být podřízené této vlastnosti. V kombinaci s `guidFilter` a `pszNameFilter` parametry.

`pszNameFilter`\
[in] Název filtru použít s `guidFilter` a `dwAttribFilter` parametry se mají vybrat, na které `DEBUG_PROPERTY_INFO` podřízené objekty jsou pro provedení výčtu. Příklad nastavení tohoto parametru na "MyX" filtry pro všechny podřízené objekty s názvem "MyX."

`dwTimeout`\
[in] Určuje maximální dobu (v milisekundách) čekání před návratem z této metody. Použití `INFINITE` čekat po neomezenou dobu.

`ppEnum`\
[out] Vrátí [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) objekt, který obsahuje seznam vlastností podřízené.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také:
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)
- [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)
- [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)