---
title: EXCEPTION_INFO | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- EXCEPTION_INFO
helpviewer_keywords:
- EXCEPTION_INFO structure
ms.assetid: d046957a-b97d-420b-b46b-c67cbaef709e
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 5c4fc29aee8d14e9c73dcf5665eff3ea611985d1
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66337797"
---
# <a name="exceptioninfo"></a>EXCEPTION_INFO
Popisuje výjimku nebo chyb za běhu vyvolané laděnému programu.

## <a name="syntax"></a>Syntaxe

```cpp
typedef struct tagEXCEPTION_INFO {
    IDebugProgram2* pProgram;
    BSTR            bstrProgramName;
    BSTR            bstrExceptionName;
    DWORD           dwCode;
    EXCEPTION_STATE dwState;
    GUID            guidType;
} EXCEPTION_INFO;
```

```csharp
public struct EXCEPTION_INFO {
    public IDebugProgram2 pProgram;
    public string         bstrProgramName;
    public string         bstrExceptionName;
    public uint           dwCode;
    public uint           dwState;
    public Guid           guidType;
};
```

## <a name="members"></a>Členové
`pProgram`\
[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekt, který reprezentuje program, ve kterém k výjimce došlo.

`bstrProgramName`\
Název programu, ve kterém k výjimce došlo.

`bstrExceptionName`\
Název výjimky.

`dwCode`\
Identifikační kód chyby výjimky nebo za běhu.

`dwState`\
Hodnota z [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md) výčet, který definuje stav výjimky.

`guidType`\
Identifikátor GUID jazyka, buď `guidLang` nebo `guidEng`.

## <a name="remarks"></a>Poznámky
Tato struktura je předán jako parametr [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) a [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md) metody. Tato struktura je také předat [GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md) metoda být vyplněna.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také:
- [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)
- [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)
- [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)
- [GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md)
