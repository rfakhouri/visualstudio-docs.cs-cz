---
title: IDebugReference2::EnumChildren | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugReference2::EnumChildren
helpviewer_keywords:
- IDebugReference2::EnumChildren
ms.assetid: 35b3c2f3-69f4-4013-b555-f847221f62e8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4c437d6b44777289abe6f079456ff2a8aba5e4a2
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458702"
---
# <a name="idebugreference2enumchildren"></a>IDebugReference2::EnumChildren
Získání seznamu vybrané podřízené objekty daného odkazu. Vyhrazeno pro budoucí použití.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT EnumChildren ( 
   DEBUGREF_INFO_FLAGS        dwFields,
   DWORD                      dwRadix,
   DBG_ATTRIB_FLAGS           dwAttribFilter,
   LPCOLESTR                  pszNameFilter,
   DWORD                      dwTimeout,
   IEnumDebugReferenceInfo2** ppEnum
);
```

```csharp
int EnumChildren ( 
   enum_DEBUGREF_INFO_FLAGS     dwFields,
   uint                         dwRadix,
   enum_DBG_ATTRIB_FLAGS        dwAttribFilter,
   string                       pszNameFilter,
   uint                         dwTimeout,
   out IEnumDebugReferenceInfo2 ppEnum
);
```

## <a name="parameters"></a>Parametry
 `dwFields`\

 [in] Kombinace příznaků z [DEBUGREF_INFO_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md) výčet, který určuje pole, která v výčtu [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktury mají být vyplněna.

 `dwRadix`\

 [in] Základ, který se má použít v jakékoli číselné informace o formátování.

 `dwAttribFilter`\

 [in] Kombinace příznaků z [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) výčet, který se používá jako filtr v kombinaci s `pszNameFilter` parametr vybrat, které struktury jsou pro provedení výčtu.

 `pszNameFilter`\

 [in] Řetězec určující filtr, jako je například "MyX" použijete v kombinaci s `dwAttribFilter` parametr vyberte struktury pro provedení výčtu.

 `dwTimeout`\

 [in] Maximální doba v milisekundách pro čekání před návratem z této metody. Použití `INFINITE` čekat po neomezenou dobu.

 `ppEnum`\

 [out] Vrátí [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md) objekt, který obsahuje seznam požadované podřízené vlastnosti.

## <a name="return-value"></a>Návratová hodnota
 Vždy vrátí `E_NOTIMPL`.

## <a name="see-also"></a>Viz také:
- [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
- [DEBUGREF_INFO_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md)
- [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)
- [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)