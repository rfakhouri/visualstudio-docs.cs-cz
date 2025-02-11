---
title: IDebugEngine2::CreatePendingBreakpoint | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine2::CreatePendingBreakpoint
helpviewer_keywords:
- IDebugEngine2::CreatePendingBreakpoint
ms.assetid: 92e85b90-a931-48d9-89a7-a6edcb83ae5a
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: fdd7fde0540754df3b152eb38d729576a7b9fe26
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66333308"
---
# <a name="idebugengine2creatependingbreakpoint"></a>IDebugEngine2::CreatePendingBreakpoint
Vytvoří čekající zarážka v ladicí stroj (DE).

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT CreatePendingBreakpoint(
    IDebugBreakpointRequest2*  pBPRequest,
    IDebugPendingBreakpoint2** ppPendingBP
);
```

```csharp
int CreatePendingBreakpoint(
    IDebugBreakpointRequest2     pBPRequest,
    out IDebugPendingBreakpoint2 ppPendingBP
);
```

## <a name="parameters"></a>Parametry
`pBPRequest`\
[in] [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md) objekt, který popisuje čekající zarážka k vytvoření.

`ppPendingBP`\
[out] Vrátí [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) objekt, který reprezentuje čekající zarážka.

## <a name="return-value"></a>Návratová hodnota
Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Obvykle vrací `E_FAIL` Pokud `pBPRequest` parametru se neshoduje s libovolný jazyk podporuje DE if `pBPRequest` parametru je neplatná nebo neúplná.

## <a name="remarks"></a>Poznámky
Čekající zarážkou je v podstatě kolekce všechny informace potřebné k vytvoření vazby zarážku do kódu. Čekající zarážka vrácené z této metody není vázán na kód, dokud [svázat](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) metoda je volána.

Pro každou čekající zarážka nastaví uživatele, Správce ladění relace (SDM) volá tuto metodu v každé připojené DE. Je až za ověření, že je platný pro programy spuštěné v této DE zarážku.

Pokud uživatel nastaví zarážku na řádek kódu, DE je bezplatné navázat zarážku na nejbližší řádek v dokumentu, který odpovídá tento kód. To umožňuje uživateli nastavit zarážku na první řádek příkazu více řádků, ale vytvořte jeho vazbu na posledním řádku (kde veškerý kód atributem v ladicích informací).

## <a name="example"></a>Příklad
Následující příklad ukazuje, jak implementovat tuto metodu pro jednoduchý `CProgram` objektu. Implementace je DE `IDebugEngine2::CreatePendingBreakpoint` může potom je předejte všechna volání této implementaci metody v každém programu.

```
HRESULT CProgram::CreatePendingBreakpoint(IDebugBreakpointRequest2* pBPRequest, IDebugPendingBreakpoint2** ppPendingBP)
{
    // Create and initialize the CPendingBreakpoint object.
    CComObject<CPendingBreakpoint> *pPending;
    CComObject<CPendingBreakpoint>::CreateInstance(&pPending);
    pPending->Initialize(pBPRequest, m_pInterp, m_pCallback, m_pEngine);
    return pPending->QueryInterface(ppPendingBP);
}
```

## <a name="see-also"></a>Viz také:
- [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
- [Bind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md)
- [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)
- [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)
