---
title: IDebugProgram2::GetProcess | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgram2::GetProcess
helpviewer_keywords:
- IDebugProgram2::GetProcess
ms.assetid: 1d602485-ebaf-451c-9165-f2e226f20a90
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b307fb7b4a25fc5a84b30eefd65e72b4f387a07d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66313764"
---
# <a name="idebugprogram2getprocess"></a>IDebugProgram2::GetProcess
Získáte, na kterém tento program běží v procesu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetProcess(
   IDebugProcess2** ppProcess
);
```

```csharp
int GetProcess(
   out IDebugProcess2 ppProcess
);
```

## <a name="parameters"></a>Parametry
`ppProcess`\
[out] Vrátí [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) rozhraní, které představuje proces.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Pokud ladicí stroj (DE) implementuje [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md) rozhraní, je DE implementace této metody by měla vždy vrátit `E_NOTIMPL` protože Zavedenými nedokáže určit, který proces běží v aplikaci a proto nelze splňovat implementace této metody.

 Implementace `IDebugEngineLaunch2` rozhraní znamená, že je DE musí vědět, jak vytvořit proces; proto, Německo provádění [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) je schopen vědět, jaký proces běží v rozhraní.

## <a name="see-also"></a>Viz také:
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
- [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)