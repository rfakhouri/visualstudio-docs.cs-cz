---
title: FRAMEINFO | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- FRAMEINFO
helpviewer_keywords:
- FRAMEINFO structure
ms.assetid: 95001b89-dddb-45bb-889d-8327994e38a5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 84e7329acb3cdbff5c2f84fbd035867791012b2e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56680500"
---
# <a name="frameinfo"></a>FRAMEINFO
Popisuje rámec zásobníku.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct tagFRAMEINFO {
    FRAMEINFO_FLAGS    m_dwValidFields;
    BSTR               m_bstrFuncName;
    BSTR               m_bstrReturnType;
    BSTR               m_bstrArgs;
    BSTR               m_bstrLanguage;
    BSTR               m_bstrModule;
    UINT64             m_addrMin;
    UINT64             m_addrMax;
    IDebugStackFrame2* m_pFrame;
    IDebugModule2*     m_pModule;
    BOOL               m_fHasDebugInfo;
    BOOL               m_fStaleCode;
    BOOL               m_fAnnotatedFrame;
} FRAMEINFO;
```

```csharp
public struct FRAMEINFO {
    public uint              m_dwValidFields;
    public string            m_bstrFuncName;
    public string            m_bstrReturnType;
    public string            m_bstrArgs;
    public string            m_bstrLanguage;
    public string            m_bstrModule;
    public ulong             m_addrMin;
    public ulong             m_addrMax;
    public IDebugStackFrame2 m_pFrame;
    public IDebugModule2     m_pModule;
    public int               m_fHasDebugInfo;
    public int               m_fStaleCode;
    public int               m_fAnnotatedFrame;
} FRAMEINFO;
```

## <a name="members"></a>Členové
m_dwValidFields A kombinace příznaků z [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md) výčet, který určuje, která pole jsou vyplněna.

m_bstrFuncName název funkce přidružené rámce zásobníku.

m_bstrReturnType návratový typ přidružený k rámce zásobníku.

m_bstrArgs argumenty funkce související s rámce zásobníku.

m_bstrLanguage jazyka ve kterém se funkce implementuje.

m_bstrModule název modulu přidružené rámce zásobníku.

m_addrMin adresy minimální fyzického zásobníku.

m_addrMAX adresy maximální fyzického zásobníku.

m_pFrame [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) objekt, který představuje tento rámec zásobníku.

m_pFrame [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) objekt, který představuje modul, který obsahuje tento rámec zásobníku.

m_fHasDebugInfo nenulová (`TRUE`) Pokud v daném rámci existuje ladicí informace.

m_fHasDebugInfo nenulová (`TRUE`) Pokud je spojen s kódem, který již není platný rámec zásobníku.

m_fHasDebugInfo nenulová (`TRUE`) Pokud rámec zásobníku je označena pomocí Správce ladění relace (SDM).

## <a name="remarks"></a>Poznámky
Tato struktura je předán [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md) metoda být vyplněna. Tato struktura je také obsažen v seznamu, který je součástí [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md) rozhraní, které je pak vrácen z volání [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) metody.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md)
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
- [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)
- [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)
- [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)
- [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)
